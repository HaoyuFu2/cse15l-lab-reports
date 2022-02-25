# Welcome!
Today we will be running three tests on my and another group's ```MarkdownParse.java```, and see how does each of them return as output.

Links to the used repositories:

 - [My MarkdownParse repository](https://github.com/HaoyuFu2/markdown-parse-1)

 - [MarkdownParse repository from another group](https://github.com/CatherineGu16/CSE15L-RoseateSpoonbill)

# Snippet 1
![Snippet 1](/Images-lab-report-4/snippet1.png)
 - What it should produce:
  ![Snippet One Preview](/Images-lab-report-4/snippetOnePreview.png)
  Three links: ```google.com```, ```google.com```, and ```ucsd.edu```.

 - How did I test it:
  ![Snippet One Test](/Images-lab-report-4/snippetTestOne.png)

 - Output from my implementation:
  ![Snippet One My Output](/Images-lab-report-4/myOutputOne.png)
  Failed!

 - Output from the implementation I reviewed:
  ![Snippet One Other Output](/Images-lab-report-4/otherOuputOne.png)
  Failed!

# Snippet 2
![Snippet 2](/Images-lab-report-4/snippet2.png)
 - What it should produce:
  ![Snippet Two Preview](/Images-lab-report-4/snippetTwoPreview.png)
  Three links: ```a.com```, ```a.com(())```, and ```example.com```.

 - How did I test it:
  ![Snippet Two Test](/Images-lab-report-4/snippetTestTwo.png)

 - Output from my implementation:
  ![Snippet Two My Output](/Images-lab-report-4/myOutputTwo.png)
  Failed!

 - Output from the implementation I reviewed:
  ![Snippet Two Other Output](/Images-lab-report-4/otherOuputTwo.png)
  Failed!

# Snippet 3
![Snippet 3](/Images-lab-report-4/snippet3.png)
 - What it should produce:
  ![Snippet Three Preview](/Images-lab-report-4/snippetThreePreview.png)
  Only one link: ```https://ucsd-cse15l-w22.github.io/```.

 - How did I test it:
  ![Snippet Three Test](/Images-lab-report-4/snippetTestThree.png)

 - Output from my implementation:
  ![Snippet Three My Output](/Images-lab-report-4/myOutputThree.png)
  Failed!

 - Output from the implementation I reviewed:
  ![Snippet Three Other Output](/Images-lab-report-4/otherOuputThree.png)
  Failed!

# Questions
 - Do you think there is a small (<10 lines) code change that will make your program work for snippet 1 and all related cases that use inline code with backticks? 
 
   Yes, I think the only problem my MarkdownParse has is that it recognizes `` `[a link`](url.com) `` as a link, while it should not because Markdown identifies the first ``[`` as a part of code block inside the backticks pair so this is an invalid link. To solve this I just need to add a variable keeping track of the position of backtick, and put an if-statement before checking the position of `[` to prevent it becoming a link.


 - Do you think there is a small (<10 lines) code change that will make your program work for snippet 2 and all related cases that nest parentheses, brackets, and escaped brackets?

   No, I think the nest parentheses, brackets, and escaped brackets has too many different cases to be covered by a few if-statements. In my opinion to entirely solve this problem it needs another set of loops to traverse the whole file and find each coresponding pair before taking the links, which is definitely more than 10 lines of code can do.


 - Do you think there is a small (<10 lines) code change that will make your program work for snippet 3 and all related cases that have newlines in brackets and parentheses? 

   Yes, I think the problem here is that my MarkdownParse identify the newline inside brackets and parentheses as a valid statement, while Markdown does not (unless there are a pair of newlines at the beginning and end). This can be solved by adding some if-statements to determine if there are ``\n`` inside brackets and parentheses, and break the loop if it does, which can be done in ten lines.
