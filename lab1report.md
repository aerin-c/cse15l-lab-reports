# Lab Report 1 - Remote Access and FileSystem
This is the write-up for the first lab that was assigned during Week 1. Below are examples for each command using the workspace created on EdStem.

## cd
1. Using only `cd`, nothing is returned as can be seen in the image below. Nothing changes because there is no new path to change the directory to. The working directory is `/home` which is to be expected since there is no new directory being used. The output is not an error since should not return anything if you are not changing your directory. ![Image](https://raw.githubusercontent.com/aerin-c/cse15l-lab-reports/main/Screenshot%202023-10-02%20at%2011.17.57.png)
2. Using `cd` with a directory modifies the path within the brackets when the new line in the terminal appears, showing that the transition to the given path has been occurred. The working directory when the command was run is `/home/lecture1` which is expected since the directory was changed to the path noted in the command. This is a transition from the inital working directory which was `/home` since that is the default directory. The output is not an error because it has successfully carried out the change from `/home` to `/home/lecture1` and also throws no errors in the following line. ![Image](https://raw.githubusercontent.com/aerin-c/cse15l-lab-reports/main/Screenshot%202023-10-02%20at%2011.39.20.png)
3. Using `cd` with a path to a file does not work because the file is not considered a directory. A directory needs to be a folder that can be opened and changed to. Using `cd` on the path to a file will throw up an error as a result of being a file and not a directory. The working directory when the command was run is `/home` because it is not a valid directory to change to. ![Image](https://raw.githubusercontent.com/aerin-c/cse15l-lab-reports/main/Screenshot%202023-10-09%20at%2013.56.25.png)

## ls
1. Using 

