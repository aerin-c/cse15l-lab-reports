# Lab Report 5 - Putting it All Together
This is a write-up for the fifth lab assigned during Week 9.

## Debugging Scenario
This is the made-up scenario for the problem.
### Original Post
It looks like I am having an error related to a test timing out when it is run based upon the error message. This error shows up in the `TestListExamples` file and 
![Image](https://raw.githubusercontent.com/aerin-c/cse15l-lab-reports/main/Screenshot%202023-12-03%20at%2023.24.54.png)
### Tutor Response
It looks like the error you are seeing is coming from the test timing out. Have you looked at the merge function to see if there are any mistakes?
### Student Response
I looked at the `merge` part of the `ListExamples.java` file and I have noticed something odd.
![Image](https://raw.githubusercontent.com/aerin-c/cse15l-lab-reports/main/Screenshot%202023-12-03%20at%2023.33.54.png)
I discovered that `index1` is present where it should be `index2` for:
```
 while(index2 < list2.size()) {
      result.add(list2.get(index2));
      // change index1 below to index2 to fix test
      index1 += 1;
```
I corrected it and the code runs fine now.
![Image](https://raw.githubusercontent.com/aerin-c/cse15l-lab-reports/main/Screenshot%202023-12-03%20at%2023.37.37.png)
### All the Information Needed for Set Up
Directory:
![Image](https://raw.githubusercontent.com/aerin-c/cse15l-lab-reports/main/Screenshot%202023-12-03%20at%2023.43.36.png)

Files Before the Fix:
ListExamples.java
![Image](https://raw.githubusercontent.com/aerin-c/cse15l-lab-reports/main/Screenshot%202023-12-03%20at%2023.53.46.png)
TestListExamples.java
![Image](https://raw.githubusercontent.com/aerin-c/cse15l-lab-reports/main/Screenshot%202023-12-03%20at%2023.45.37.png)
GradeServer.java
![Image](https://raw.githubusercontent.com/aerin-c/cse15l-lab-reports/main/Screenshot%202023-12-03%20at%2023.46.04.png)
![Image](https://raw.githubusercontent.com/aerin-c/cse15l-lab-reports/main/Screenshot%202023-12-03%20at%2023.46.14.png)
Grade.sh
![Image](https://raw.githubusercontent.com/aerin-c/cse15l-lab-reports/main/Screenshot%202023-12-03%20at%2023.47.21.png)

Files After the Fix
ListExamples.java
![Image](https://raw.githubusercontent.com/aerin-c/cse15l-lab-reports/main/Screenshot%202023-12-03%20at%2023.45.09.png)
TestListExamples.java
![Image](https://raw.githubusercontent.com/aerin-c/cse15l-lab-reports/main/Screenshot%202023-12-03%20at%2023.45.37.png)
GradeServer.java
![Image](https://raw.githubusercontent.com/aerin-c/cse15l-lab-reports/main/Screenshot%202023-12-03%20at%2023.46.04.png)
![Image](https://raw.githubusercontent.com/aerin-c/cse15l-lab-reports/main/Screenshot%202023-12-03%20at%2023.46.14.png)
Grade.sh
![Image](https://raw.githubusercontent.com/aerin-c/cse15l-lab-reports/main/Screenshot%202023-12-03%20at%2023.47.21.png)

Command to Create Bug:
![Image](https://raw.githubusercontent.com/aerin-c/cse15l-lab-reports/main/Screenshot%202023-12-03%20at%2023.24.54.png)

Fixing the Bug:
```
 while(index2 < list2.size()) {
      result.add(list2.get(index2));
      // change index1 below to index2 to fix test
      index1 += 1;
```
replace index1 with index2, which makes:
```
 while(index2 < list2.size()) {
      result.add(list2.get(index2));
      // change index1 below to index2 to fix test
      index2 += 1;
```

## Reflection
Something I have learned in this class during the lab was how to edit bugs using vim. Before this, I had never used vim to edit files and I would always struggle with editing files remotely. Learning vim has helped me learn to access files and edit them without having to have the file physically on my device and it has made my life easier too.
