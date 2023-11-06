# Lab Report 3 - Bugs and Commands
This is the write-up for the third lab assigned during Week 5.

## Bugs
Failure-inducing input:
```
@Test
  public void testReverseInPlace2() {
    int[] input2 = { 1, 2, 3 };
    ArrayExamples.reverseInPlace(input2);
    assertArrayEquals(new int[]{ 3, 2, 1 }, input2);
  }
```

Input that doesn't induce a failure:
```
@Test 
	public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}
```

Symptom (output of runnng the tests):
!Image[] screenshot at 21.57

The bug (before and after):
Before:
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```

After:
```
tatic void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2; ++i) {
      int temp = arr[i];
      arr[i] = arr[arr.length - 1 - i];
      arr[arr.length-1-i] = temp;
    
    }
  }
```

The issue was that after the first half of the list had been traversed, `arr[arr.length - i - 1]` would start referencing elements of the list that had already been put in reverse order, messing up the process. The fix addresses this issue by only traversing half the list, and swapping elements instead of just setting one element equal to another.

## Researching Commands

