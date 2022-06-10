# **Lab Report 5 Week 10**

For this lab report, I will go over two different tests from lab 9 which showed differences between my implementation and the provided one.

## **First Test: Test [194.md](https://github.com/kmolina15/markdown-parser/blob/main/test-files/194.md)**

Upon comparing the two outputs with vimdiff (my implementation on the left, provided one on the right), we get this result:

![vimdiff1](https://raw.githubusercontent.com/kmolina15/cse15l-lab-reports/main/vimdiff1.png)

According to CommonMark, the expected result should have a link within it:

![cmark1](https://raw.githubusercontent.com/kmolina15/cse15l-lab-reports/main/cmark1.png)

As shown, my implementation of markdownParse does not correctly display this test as a link. The issue appears to be in this block of code:

![code1](https://raw.githubusercontent.com/kmolina15/cse15l-lab-reports/main/code1.png)

The bug in this case appears to be that this is a link formatted differently than the typical [title-in-brackets]\(url-in-parentheses) link formatting the program currently handles. As such, since the closed bracket is not immediately followed by the open parentheses in this link format, the link is not correctly returned by markdownParse. To fix this issue, markdownParse should check for a formatting similar to this, with a colon followed by the title, and the URL in single quotation marks.

## **Second Test: Test [32.md](https://github.com/kmolina15/markdown-parser/blob/main/test-files/32.md)**

Upon comparing the two outputs with vimdiff (my implementation on the left, provided one on the right), we get this result:

![vimdiff2](https://raw.githubusercontent.com/kmolina15/cse15l-lab-reports/main/vimdiff2.png)

According to CommonMark, the expected result should have a link within it:

![cmark2](https://raw.githubusercontent.com/kmolina15/cse15l-lab-reports/main/cmark2.png)

As shown, the markdownParse implementation provided in lab 9 does not correctly display a link after this test is run. The issue in lab 9's implementation appears to be in this block of code:

![code2](https://raw.githubusercontent.com/kmolina15/cse15l-lab-reports/main/code2.png)

The bug in this case appears to be that because of the space within the parentheses, the program does not execute what is within this if statement and fails to add the link. However, commonMark does recognize this as a specially formatted link. To fix this issue, the contents of the link (from the open parentheses to the closed parentheses) should be checked to see if it follows this sort of formatting.