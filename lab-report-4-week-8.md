# **Lab Report 4 Week 8**

For this lab report, I will be going through three different inputs for markdownParse and fix any issues that each input may produce.

[This](https://github.com/kmolina15/markdown-parser) is the repository from my group that I cloned.

[This](https://github.com/Steven-Hsu1/markdown-parser) is the repository from the other group that I cloned.

## **Snippet 1**

The first snippet should produce an array with three links: ['google.com, google.com, ucsd.edu].

Here it is as a test markdown file and the resulting links produced in the VSCode preview:

![snip1a](https://raw.githubusercontent.com/kmolina15/cse15l-lab-reports/main/snip1a.png)

Here is the JUnit test that takes this snippet as an input:

![snip1d](https://raw.githubusercontent.com/kmolina15/cse15l-lab-reports/main/snip1d.png)

When ran with my version of markdownParse, it failed:

![snip1b](https://raw.githubusercontent.com/kmolina15/cse15l-lab-reports/main/snip1b.png)

When ran with the other group's version, it also failed:

![snip1c](https://raw.githubusercontent.com/kmolina15/cse15l-lab-reports/main/snip1c.png)

I believe that to make the program work for this snippet, a small code change can be implemented. This change would come after the first open bracket is found and uses indexOf to find the number of backticks from currentIndex to openBracket, as well as the number from openBracket to the next closed braccket. If there is an odd number of backticks in both regions, the region enclosed by backticks includes either the open or closed brackets, which means the link should not be added.


## **Snippet 2**

The second snippet should produce an array with 3 links: [a.com, a.com(()), example.com].

Here is the test markdown file and the resulting links produced:

![snip2a](https://raw.githubusercontent.com/kmolina15/cse15l-lab-reports/main/snip2a.png)

Here is the JUnit test that uses this snippet:

![snip2b](https://raw.githubusercontent.com/kmolina15/cse15l-lab-reports/main/snip2b.png)

When ran with my version of markdownParse, it failed:

![snip2c](https://raw.githubusercontent.com/kmolina15/cse15l-lab-reports/main/snip2c.png)

When ran with the other group's version, it also failed:

![snip2d](https://raw.githubusercontent.com/kmolina15/cse15l-lab-reports/main/snip2d.png)

To make the program work for this snippet would probably not be doable via a simple code change. It would require several lines of code to address each problem here: nested brackets/links inside brackets, nested parentheses inside a link's parentheses, and backslashes appearing before a bracket. These problems are all somewhat unique and cannot be easily resolved with a single fix of 10 lines of code.


## **Snippet 3**

The third snippet should produce an array with one link: [https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule].

Here is the test markdown file and the resulting links produced:

![snip3e](https://raw.githubusercontent.com/kmolina15/cse15l-lab-reports/main/snip3e.png)

Note that the twitter link and cse.ucsd link are highlighted as links even though unproperly formatted on MarkDown. Using the CommonMark Demo site, only the correctly formatted link is highlighted:

![snip3a](https://raw.githubusercontent.com/kmolina15/cse15l-lab-reports/main/snip3a.png)

Here is the JUnit test that uses this snippet:

![snip3b](https://raw.githubusercontent.com/kmolina15/cse15l-lab-reports/main/snip3b.png)

When ran with my version of markdownParse, it failed:

![snip3c](https://raw.githubusercontent.com/kmolina15/cse15l-lab-reports/main/snip3c.png)

When ran with the other group's version, it also failed:

![snip3d](https://raw.githubusercontent.com/kmolina15/cse15l-lab-reports/main/snip3d.png)

To make the program work for this snippet, there is a small code change that can be implemented. The issue this snippet presents is whether a new line occurs within the link format (anywhere from the open bracket to the closed parentheses). To fix this issue, the easiest solution is to add an indexOf statement that checks if the formatting for a new line, \n, occurs anywhere in this region, and if it does, do not add the link to the array to be returned.