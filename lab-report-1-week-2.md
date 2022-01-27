# Welcome!
In this post I will be talking about the steps to log into a course-specific account on **ieng6**.

# Installing VScode
The first thing you need to do is to install a code editor so that you can run the code on your own computer. Visual Studio Code is recommended by this course, and everything I write below is based on VScode. You can download VScode here: [Official VScode Website](https://code.visualstudio.com/).

Once you have download and install the VScode, it should looks similar to this (I have made some customizations on VScode, so the colors may look different):![Installing VScode](https://github.com/HaoyuFu2/cse15l-lab-reports/blob/main/Images/Installing%20VScode.png?raw=true) If you see something like this, you are all set.

# Remotely Connecting
Before you can connect to the course server, you need to look up your username here: [https://sdacs.ucsd.edu/~icc/index.php](https://sdacs.ucsd.edu/~icc/index.php), you should also asked to change the passwords before using it. 

![Remotely Connecting](https://github.com/HaoyuFu2/cse15l-lab-reports/blob/main/Images/Remotely%20Connecting.png?raw=true)

Then, in the terminal of the VScode, type 

`ssh cs15lwi22[your username]@ieng6.ucsd.edu`

and enter your password. You should be successfully connect to the server, like the screenshot shows! (If something like `(yes/no)` appears, just type `yes`.)

# Trying Some Commands
![Trying Some Commands](https://github.com/HaoyuFu2/cse15l-lab-reports/blob/main/Images/Trying%20Some%20Commands.png?raw=true)

Once you have connect to the server, you can try some commands
The screenshot shows what I tried in the first time I connect to the server. Commands that I tried: `ls`, `ls -a`, `ls -lat`, `cd`, `cd ~`, `pwd`, `logout`, `exit`.

# Moving Files with scp
![Moving Files with scp](https://github.com/HaoyuFu2/cse15l-lab-reports/blob/main/Images/Moving%20Files%20with%20scp.png?raw=true)

You can upload files from your computer to the server. First you should log out using the command `logout` to return to the terminal on your computer, then use the command `scp [File Name] cs15lwi22[your username]@ieng6.ucsd.edu: [any directory on the server]`. The screenshot shows an example of uploading and running a java file to the server.

# Setting an SSH Key
![Setting an SSH Key](https://github.com/HaoyuFu2/cse15l-lab-reports/blob/main/Images/Setting%20an%20SSH%20Key.png?raw=true)

It is annoying that you need to enter your password over and over again whenever you log in to the server. Fortunately you can set up an SSH Key on your computer so you get rid of it. 

Steps you need to set an SSH Key:
1. enter ssh-keygen in your terminal
2. just press enter when you are asked a file to save the key
3. type your password twice
4. log in to the server
5. enter the command `mkdir .ssh` and log out
6. enter `scp [/Users/[your username on your computer]/.ssh/id_rsa.pub] cs15lwi[your user name on the server]@ieng6.ucsd.edu:~/.ssh/authorized_keys`
You can now connect to the server without typing password, like the screenshot shows.

# Optimizing Remote Running
![Optimizing Remote Running](https://github.com/HaoyuFu2/cse15l-lab-reports/blob/main/Images/Optimizing%20Remote%20Running.png?raw=true)

The screenshot shows other things you can try to improve the efficiency of remote working on a server:
 - quote the commands you want to run on the server after you type `ssh uername` to run it without log in to the server
 - use semicolons to separate commands, so you can run multiple commands within a single line
 - copy your username, and just paste it whenever you need it
 - use shortcuts (command c and command v for examples) to save time
 - use tab key to automatically fill some file names or commands

Example of how using these techniques to save time:

Let's say we want to copy a java file to the server and run it on the server.
Without using the techniques, we need to type the following codes:
 - 
    