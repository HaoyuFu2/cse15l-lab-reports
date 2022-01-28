# Welcome again!
In this post I will be talking about the changes of a small program as debugging practices made together in my group in the CSE 15L lab session.

# Code Change 1
![Code Change 1]()

1. Failure-inducing input: https://github.com/HaoyuFu2/markdown-parse/blob/3bc9100f45ffb5192bc4915c770163f06c580b26/breaking-test.md

2. Symptom of the failure-inducing input:

    `$ java MarkdownParse breaking-test.md`

    `[www.goog(]`

3. This bug is caused by an extra pair of parenthesis nested inside another pair of parenthesis, for example, (www.goog())le.com). The symptom of this bug 


# Code Change 2


# Code Change 3

