# Welcome again!
In this post I will be talking about the changes of a small program as debugging practices made together in my group in the CSE 15L lab session.

# Code Change 1
![Code Change 1](https://github.com/HaoyuFu2/cse15l-lab-reports/blob/main/Images-lab-report-2/Code-Change-1.png?raw=true)

1. Failure-inducing input: [Failure-inducing input 1](https://github.com/HaoyuFu2/markdown-parse/blob/5170cd7532d0aea068ed4f707ccca582d0204da7/breaking-test.md)

2. Symptom of the failure-inducing input:

    `$ java MarkdownParse breaking-test.md`

    `[www.goog(]`

3. This bug is caused by inputs with an extra pair of parenthesis nested inside another pair of parenthesis, for example, (www.goog()le.com). The symptom of this bug looks like an imcomplete link ends with a close parenthesis. The code doesn't check this condition, so when there exists another pair of parenthesis, the substring method just ends at the first occured close parenthesis and return a half of the link.


# Code Change 2
![Code Change 2](https://github.com/HaoyuFu2/cse15l-lab-reports/blob/main/Images-lab-report-2/Code-Change-2.png?raw=true)

1. Failure-inducing input: [Failure-inducing input 2](https://github.com/HaoyuFu2/markdown-parse/blob/09e1d5097d3d74dd8234660392f670105444c1f1/test-file-image.md)

2. Symptom of the failure-inducing input:

    `$ java MarkdownParse test-file-image.md`

    `[www.aLink.com, www.someImage.com]`


3. This bug doesn't have an obvious symptom, because it works perfectly at the first glance. However, when we check the output and the input file, we would find that the program also extract the image links from the file, which it should not do so. Any file containing an image link could be an failure-inducing input causing this bug, because the code doesn't check whether there is an exclaimation mark before the open bracket.

# Code Change 3
![Code Change 3]()

1. Failure-inducing input: [Failure-inducing input 3](https://github.com/HaoyuFu2/markdown-parse/blob/1c64c7e44031f2331f610086bfe31693d6e2066f/no-parenthesis.md)

2. Symptom of the failure-inducing input:

    `$ java MarkdownParse no-parenthesis.md `

        Exception in thread "main" java.lang.StringIndexOutOfBoundsException: begin -2, end -1, length 42
            at java.base/java.lang.String.checkBoundsBeginEnd(String.java:4601)
            at java.base/java.lang.String.substring(String.java:2704)
            at MarkdownParse.getLinks(MarkdownParse.java:21)
            at MarkdownParse.main(MarkdownParse.java:39)

3. 


