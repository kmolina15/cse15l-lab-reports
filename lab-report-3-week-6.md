# **Lab Report 3 Week 6**

This is the lab report on the three tasks given in Week 5's lab.

## **1) Streamlining ssh Configuration**

The first task in this lab was streamlining ssh configuration in order to make logging in to the remote computer faster and easier. To do this, a config file was added within the .ssh directory, created in VSCode.

![streamline1](https://github.com/kmolina15/cse15l-lab-reports/blob/main/streamline1.png?raw=true)

By streamlining this process, it becomes easier to use ssh to access the remote computer and scp to move files from my personal computer.

![streamline2](https://github.com/kmolina15/cse15l-lab-reports/blob/main/streamline2.png?raw=true)

![streamline3](https://github.com/kmolina15/cse15l-lab-reports/blob/main/streamline3.png?raw=true)

## **2) Setup Github Access from ieng6**

The second task was setting up GitHub access from the remote computer. A new key was created via ssh-keygen, with the public key being added to my personal github account:

![gitkey1](https://github.com/kmolina15/cse15l-lab-reports/blob/main/gitkey1.png?raw=true)

This is the location of the public and private keys within the remote computer:

![gitkey2](https://github.com/kmolina15/cse15l-lab-reports/blob/main/gitkey2.png?raw=true)

With this access, it becomes possible to push and commit changes within the repository in the remote server to the online repository.

![gitkey3](https://github.com/kmolina15/cse15l-lab-reports/blob/main/gitkey3.png?raw=true)

[Here is the commit reflected in the online repository.](https://github.com/kmolina15/markdown-parser/commit/0505a4d63a136d53c0f8ef5558a543180c9b95b9)

## **3) Copy Whole Directories with scp -r**

The final task was using scp -r to copy an entire directory to the remote computer. This allows us to transfer the entire markdown-parse directory to the ieng6 account:

![scp-r2](https://github.com/kmolina15/cse15l-lab-reports/blob/main/scp-r2.png?raw=true)

![scp-r1](https://github.com/kmolina15/cse15l-lab-reports/blob/main/scp-r1.png?raw=true)

From there we can log on and run the JUnit tests on the MarkdownParseTester file.

![scp-r3](https://github.com/kmolina15/cse15l-lab-reports/blob/main/scp-r3.png?raw=true)

Combining this with what we have done in lab 1, we can streamline the entire process to be done in a single line:

![scp-r4](https://github.com/kmolina15/cse15l-lab-reports/blob/main/scp-r4.png?raw=true)

![scp-r5](https://github.com/kmolina15/cse15l-lab-reports/blob/main/scp-r5.png?raw=true)


