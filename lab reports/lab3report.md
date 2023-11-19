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

Symptom (output of running the tests):
![Image](https://raw.githubusercontent.com/aerin-c/cse15l-lab-reports/main/Screenshot%202023-11-05%20at%2021.57.51.png)

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
For this section I decided to research the `grep` command.
1. `-F` (source: [https://man7.org/linux/man-pages/man1/grep.1.html](https://man7.org/linux/man-pages/man1/grep.1.html))
   
Example 1:
The `-F` option allows us to interpret the string in the quotes as a literal string instead of a regex. If we wanted to match `[` and used regular grep, then it would throw an error because `[` is not a valid regex, but it works fine with `-F`:
```
(base) carinachiu@meowlkor technical % grep -F '[' plos/pmed.0020099.txt
        HIV/AIDS pandemic now kills more than 8,300 people each day [1]. New drugs are being
        even though these account for over 10% of the global disease burden [2]. Both within and
        of possible approaches toward ensuring free and open access to the world's literature [3],
        developing countries [4]. Bringing the entire world of learners into a global conversation
        refuse to advertise medical drugs or devices [5]. We hope that other major journals will
```

Example 2:
Similarly, `.` is a special regex character, so just calling regular grep prints the entire file, but calling with `-F` only prints the lines with periods.
```
(base) carinachiu@meowlkor technical % grep -F '.' plos/pmed.0020099.txt
        ... lots of lines with only periods in them...
```

   
3. `-i` (source: [https://man7.org/linux/man-pages/man1/grep.1.html](https://man7.org/linux/man-pages/man1/grep.1.html))
   
Example 1:
The `-i` option allows us to ignore the case when matching. Here, we want to match `nairobi`, and using `-i` allows us to match cases even when the `n` is capitalized:
```
(base) carinachiu@meowlkor technical % grep -i 'nairobi' 911report/chapter-2.txt
                in Nairobi as a cover for operatives there.)
            Al Qaeda leaders set up a Nairobi cell and used it to send weapons and trainers to
                begun casing targets in Nairobi for future attacks. It was led by Ali Mohamed, a
                in an apartment in Nairobi where the various al Qaeda operatives and leaders based
                embassy in Nairobi was an easy target because a car bomb could be parked close by,
                in Nairobi, and that Hage's telephone was being tapped. Hage was a U.S.citizen who
                being pulled together in Nairobi and Dar es Salaam. The timing and content of their
            The next four months were spent setting up the teams in Nairobi and Dar es Salaam.
                assist in putting the weapons together. In Nairobi, a hotel room was rented to put
                run at the embassy in Nairobi. By the evening of August 6, all but the delivery
                five minutes apart-about 10:35 A.M. in Nairobi and 10:39 A.M. in Dar es Salaam.
            The attack on the U.S. embassy in Nairobi destroyed the embassy and killed 12
```

Example 2:
Similarly, we can match even an all-caps `TANZANIA` using the query `tanzania`:
```
(base) carinachiu@meowlkor technical % grep -i 'tanzania' 911report/chapter-3.txt
            BEFORE THE BOMBINGS IN KENYA AND TANZANIA
                embassies in Nairobi, Kenya, and Dar es Salaam, Tanzania. Suspicion quickly focused
```
   
5. `-o` (source: [https://man7.org/linux/man-pages/man1/grep.1.html](https://man7.org/linux/man-pages/man1/grep.1.html))
   
Example 1:
The `-o` option only prints the actual part of the file that was matched, and not the entire line. For example, if I search for `cell` with the `-o` option, I will only get the word `cell` back and not the whole lines:
```
(base) carinachiu@meowlkor technical % grep -o 'cell' biomed/1475-2867-3-4.txt
cell
cell
cell
cell
... continues
```

Example 2:
This is more useful when we use a regex, for example if I want to find all the numbers in a file I use `-o` to print only the numbers themselves:
```
(base) carinachiu@meowlkor technical % grep -o '[0-9]*' biomed/1475-2867-3-4.txt
4
4
1
2
2
8
4
3
4
4
4
5
6
4
7
8
8
9
10
9
11
... continues
```
   
7. `-n` (source: [https://man7.org/linux/man-pages/man1/grep.1.html](https://man7.org/linux/man-pages/man1/grep.1.html))
   
Example 1:
The `-n` option prints the line number along with the matched line, in case I want to find the original line in the file. Here, I print all the lines numbers where Sirabella is mentioned:
```
(base) carinachiu@meowlkor technical % grep -n 'Sirabella' government/Media/residents_sue_city.txt
41:Yesterday, Deputy Mayor Sal Sirabella said he had not seen the
47:Sirabella.
49:Sirabella said, adding that no closing date has been set
```

Example 2:
I can also use this option to find the line number of a query that matches a single line, in case I want to look for a very specific line. For example,
```
(base) carinachiu@meowlkor technical % grep -n 'Welling' government/Media/residents_sue_city.txt
30:Welling, Community Justice Project attorney, contend that the city
```
