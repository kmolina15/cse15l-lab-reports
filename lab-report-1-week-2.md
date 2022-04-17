# **Lab Report 1 Week 2**

Hello! This is my first CSE15L lab report. This will cover the instructions for Lab 1.

## **1) Installing VSCode**

Visual Studio Code (VSCode) is a programming interface that helps increase efficiency. You can download it for free from their [website](https://code.visualstudio.com/). Once you have installed VScode, you should open it and receive a window like this:

![Image](https://kmolina15.github.io/cse15l-lab-reports/vscinterface.png)

## **2) Remotely Connecting**

If you are on a Windows device (like me), you first need to install [OpenSSH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse) to connect remotely. Open up a new terminal (can be done from VSCode via Terminal on the taskbar -> New Terminal, or using Ctrl + ') and enter this command to log in remotely:

$ ssh user@hostname 

* (the login used for this course is cs15lsp22zz@ieng6.ucsd.edu with zz representing a user-specific combination of letters)

After doing this, answer 'yes' to the prompt and enter your password. If your login is successful, your terminal should contain a message like this:

![Image](https://kmolina15.github.io/cse15l-lab-reports/login.png)

## **3) Trying Some Commands**

Once you have successfully connected to the UCSD databases, try out some ssh commands in your terminal! Examples of some commands include cd (to change directories), ls (to list files in a directory), or cp (to copy a directory). Here is an example of using the cd command to navigate throughout folders within the server, then using exit to logout:

![Image](https://kmolina15.github.io/cse15l-lab-reports/commandtest.png)

## **4) Moving Files with scp**

We can use the scp command to move files from a personal computer to the remote server. In this lab, I took a java file called WhereAmI.java and moved it with this command:

$ scp WhereAmI.java(filename) cs15lsp22zz@ieng6.ucsd.edu(address)

After moving files to the server one can access it from the server, as shown in this image where WhereAmI.java is compiled and run:

![Image](https://kmolina15.github.io/cse15l-lab-reports/runjava.png)

## **5) Setting an SSH Key**

To maximize efficiency, we can set up an SSH key on our personal computer that allows us to skip inputting our password when accessing or copying files over to the remote server. These are the commands to input in your terminal to create and send over your key:

![Image](https://kmolina15.github.io/cse15l-lab-reports/keyinstructions.png)

The private key stored in your computer paired with the public key in the remote server allow for you to use ssh and scp without a password, like so:

![Image](https://kmolina15.github.io/cse15l-lab-reports/keylogin.png)

## **6) Optimizing Remote Running**

Now that we don't have to input our password to use scp and ssh, we can make the transition of local edits to remote copying much more efficient. Some other optimizations to minimize the amount of command lines needed to run include:
* adding commands in "" quotations after ssh, which will prompt the terminal to login, run the commands and logout
* running multiple commands in one line by separating them with semicolons ;

For example, we can use this single command line to copy the edits made to WhereAmI.java over to and run them from the remote server:
* $ scp WhereAmI.java [Account Name]; ssh [Account Name] "javac WhereAmI.java; java WhereAmI;"; 

Here is an example of this in action (note that after WhereAmI runs, the terminal has logged out of the server):

![Image]()