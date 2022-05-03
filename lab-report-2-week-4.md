# **Lab Report 2 Week 4**

This is the second lab report. I'll be describing 3 changes done to MarkdownParse.java.

## Change 1

![Change 1]()

For this first change, an if statement was added to check if a potential link was an image.  

This [test](https://github.com/kmolina15/markdown-parser/blob/b30d1be0a6eb6c2f576c0051f46490487526a4e1/my-test.md) demonstrates the issue: MarkdownParse would take the links for images as well as websites.

![Symptom 1]()

In Markdown, the notation for creating a link is very similar to that for an image, with only an exclamation mark in front of the brackets separating the two. To make sure markdownParse doesn't parse the image links, an if statement was used to check whether there is an exclamation mark before the brackets.


## Change 2

![Change 2]()

For the second change, another if statement was added to check that the closed bracket is next to the open parentheses.

This [test]() demonstrates that MarkdownParse would return values within parentheses even if they do not immediately follow a set of brackets. In other words, it would return values that are not formatted as website links.

![Symptom 2]()

To make sure markdownParse doesn't parse these links, an if statement adds a new condition that checks whether the index of openParen is one greater than closeBracket.


## Change 3

![Change 3]()

The third change was actually made in response to an issue that occured because of our first change: in order to separate an image and a link, the index before the open bracket is checked. This produces an issue if a website link is at the beginning of a markdown file.

Running this [test]() demonstrates this issue: when a link is at the beginning, it checks the index before the bracket which causes an exception.

![Symptom 3]()

To solve this, we add another if statement that checks if the open bracket is at the first index, then an else-if to make sure the link isn't an image.