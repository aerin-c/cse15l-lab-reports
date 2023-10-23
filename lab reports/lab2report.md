# Lab Report 2 - Servers and SSH Keys
This is the write-up for the second lab that was assigned during Week 3.

## StringServer
The code for the string server is below: <br> ![Image](https://raw.githubusercontent.com/aerin-c/cse15l-lab-reports/main/Screenshot%202023-10-22%20at%2022.39.21.png) <br> It appears that when adding the first phrase via `/add-message` the methods used are `handleRequest`, `url.getQuery`, `query.startsWith`, and `StringAdder()`. When running it for ```No test```, the relevant arguments are `URI url`, `lines`, and `toAdd`. The value of statement is `(this.lines.size()+1)`. ![Image](https://raw.githubusercontent.com/aerin-c/cse15l-lab-reports/main/Screenshot%202023-10-22%20at%2022.41.27.png) <br> As for running it for ```Stressed```, the methods are `handleRequest`,  `url.getQuery`, `query.startsWith`, `String.join` and `StringAdder()`. When running it, the relevant arguments are `URI url`, `lines`, `toAdd`, `"s="`, and `"/add-message"`. The value of statement adds 1 to to the count which makes it print it as the second item in the list. ![Image](https://raw.githubusercontent.com/aerin-c/cse15l-lab-reports/main/Screenshot%202023-10-22%20at%2022.41.57.png)


## SSH Keys


## New Knowledge
What I learned from lab in Week 3 was how to set up an SSH key and make it so I did not have to remember a password to log in. I thought it was pretty neat that there was a way to autofill a password and log-in details via the terminal. Before learning how to do that, I never really knew how it worked since I only ever saw the UI and not the back-end.
