# **Lab Report 1 Week 2**

Hello! This is my first CSE15L lab report. This will cover the instructions for Lab 1.

## **1) Installing VSCode**

Visual Studio Code (VSCode) is a programming interface that helps increase efficiency. You can download it for free from their [website](https://code.visualstudio.com/). Once you have installed VScode, you should open it and receive a window like this:

![Image](https://kmolina15.github.io/cse15l-lab-reports/vscinterface.png)

## **2) Remotely Connecting**

If you are on a Windows device (like me), you first need to install [OpenSSH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse) to connect remotely. Open up a new terminal (can be done from VSCode via Terminal on the taskbar -> New Terminal, or using Ctrl + ') and enter this command to log in remotely:

ssh user@hostname 

* (the login used for this course is cs15lsp22zz@ieng6.ucsd.edu with zz representing a user-specific combination of letters)

After doing this, answer 'yes' to the prompt and enter your password. If your login is successful, your terminal should contain a message like this:

![Image](https://kmolina15.github.io/cse15l-lab-reports/login.png)