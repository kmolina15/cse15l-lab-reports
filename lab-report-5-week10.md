# **Lab Report 5 Week 10**

For this lab report, I will go over two different tests from lab 9 which showed differences between my implementation and the provided one.

## **First Test: Test [194.md](https://github.com/kmolina15/markdown-parser/blob/main/test-files/194.md)**

Upon comparing the two outputs with vimdiff (my implementation on the left, provided one on the right), we get this result:

![vimdiff1]()

According to CommonMark, the expected result should have a link within it:

![cmark1]()

As shown, both implementations of markdownParse do not correctly display this test as a link.  

## **Second Test: Test [32.md](https://github.com/kmolina15/markdown-parser/blob/main/test-files/32.md)**

Upon comparing the two outputs with vimdiff, we get this result:

![vimdiff2]()

According to CommonMark, the expected result should have a link within it:

![cmark2]()

[foo*bar\]]:my_(url) 'google.com'

[foo*bar\]]

[link]((https://github.com/kmolina15/markdown-parser/blob/main/test-files/32.md
