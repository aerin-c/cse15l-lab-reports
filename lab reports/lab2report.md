# Lab Report 2 - Servers and SSH Keys
This is the write-up for the second lab that was assigned during Week 3.

## StringServer
The code for the string server is below: <br> ![Image](https://raw.githubusercontent.com/aerin-c/cse15l-lab-reports/main/Screenshot%202023-10-22%20at%2022.39.21.png) 

<br> When adding the first phrase, `No test`, via `/add-message`, the only method in my code that is called is `handleRequest`. When running it for `No test`, the only argument to `handleRequest` is `URI url`, and the only field in the class is `List<String> lines`, which is currently just an empty list. When the method is run, the message `No test` is appended to the `lines` field, making it the first item in the list.
![Image](https://raw.githubusercontent.com/aerin-c/cse15l-lab-reports/main/Screenshot%202023-10-22%20at%2022.41.27.png) 

<br> When adding the second phrase `Stressed`, again the only method that is called is `handleRequest`. Again, the only argument is `URI url`, and the only field in the class is `List<String> lines`, which this time contains one element (the String `No test`). When the method is run, the message `Stressed` is appended to the `lines` field, making it the second item in the list.
![Image](https://raw.githubusercontent.com/aerin-c/cse15l-lab-reports/main/Screenshot%202023-10-22%20at%2022.41.57.png)


## SSH Keys
The private key (`id_rsa`) on my computer is located at: 
![Image]() 

My public key (`id_rsa.pub`) on `ieng6` is located at:
![Image]() 

Logging into `ieng6` without being asked for my password:
![Image](https://raw.githubusercontent.com/aerin-c/cse15l-lab-reports/main/Screenshot%202023-10-22%20at%2023.10.51.png)

## New Knowledge
What I learned from lab in Week 3 was how to set up an SSH key and make it so I did not have to remember a password to log in. I thought it was pretty neat that there was a way to autofill a password and log-in details via the terminal. Before learning how to do that, I never really knew how it worked since I only ever saw the UI and not the back-end.
