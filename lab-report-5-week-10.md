# Welcome!
This time I will be comparing my implimentation of MarkdownParse.java with the implementation provided by lab 9. I will find two tests that my implimentation and the provided implementation produce different results, and research about them.

# Different results
Test One: `182.md`

![Test_One](/Images-lab-report-5/Test_One.png)

Test Two: `32.md`

![Test_Two](/Images-lab-report-5/Test_Two.png)

I found these two different results by adding a line of code to echo the file name, using `command + F` inside the results.txt to find the file names, and manually compare the differences. 

# Test One
Output from my implementation:

![T1_My_Impl](/Images-lab-report-5/T1_My_Impl.png)

Output from provided implementation:

![T1_Provided_Impl](/Images-lab-report-5/T1_Provided_Impl.png)

Expected output:

![T1_Expected](/Images-lab-report-5/T1_Expected.png)
There should not be any link inside this md file.

 - By comparing the expected output and the outputs from the two implementations, we can find that the output from the provided implementation is correct, while mine is wrong.
 - The problem in my implementation is that it substrings the stuff in the file even if openParen is -1.
![T1_Problem](/Images-lab-report-5/T1_Problem.png)
 - It is easy to solve this problem, by just adding an if statement to check if openParen is -1. If so, just break the loop.
 ![T1_Solution](/Images-lab-report-5/T1_Solution.png)

# Test Two
Output from my implementation:

![T2_My_Impl](/Images-lab-report-5/T2_My_Impl.png)

Output from provided implementation:

![T2_Provided_Impl](/Images-lab-report-5/T2_Provided_Impl.png)

Expected output:

![T2_Expected](/Images-lab-report-5/T2_Expected.png)
The String inside the parenthesis should be recognized as a url link. (After reseach I found that it actually should be looking like `föö`, where `ö` is expressed by `&ouml`)

 - By comparing the expected output and the outputs from the two implementations, we can find that my implementation is somewhat wrong(detects the link, but the link is wrong), and the provided output is wrong(does not detect the link).
 - The problem this time is that there is a space inside the parentheses. After some research, I found out that while it should normally not be considered to be a link, this string contains some `&ouml` which represents the special character `ö`. The string seems to follow some special pattern(but unfortunately I did not find exactly how) that contains space, and this pattern makes the `&ouml` being able to be recognized as a special character. 
 - So what my implementation and the provided implementation both do not take into account is this special code pattern which represents some special characters. I think to fix this I need some further information about this pattern which I did not find on the Internet, and write some code accordingly to this pattern to let it be recognized as a valid url link.

 - Related part in the provided implementation:
 ![T2_Problem](/Images-lab-report-5/T2_Problem.png)

 - There is no code snippet I can show and fix in my implementation that is related to this bug, since I totally did not take this situation into account and just need some new snippet to treat with this situation :(
