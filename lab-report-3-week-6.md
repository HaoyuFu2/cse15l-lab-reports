# Welcome!
This time we will be going through one of the three options for lab report #3. I choose to do [Copy whole directories with scp -r](https://ucsd-cse15l-w22.github.io/week/week5/#group-choice-3-copy-whole-directories-with-scp--r).

# Copying the whole markdown-parse directory
We can secure copy a directory and all files inside recursively to a server using the command:

`scp -r . cs15lwi22@ieng6.ucsd.edu:~/markdown-parse`

Here is an example copying the markdown-parse directory into the ieng6 server:

![Copying whole directory]()

# Checking the results of `scp -r`
Let's log in to the ieng6 server and try compiling and running the tests:

![Check result of scp -r]()

# Combining `scp`, `;`, and `ssh `
Now let's try to copy the whole directory and run the tests in one line by combining commands using `;`.

Commands I used:

`scp -r . ieng6:~/markdown-parse/; ssh ieng6 "cd markdown-parse/; /software/CSE/oracle-java-se-14/jdk-14.0.2/bin/javac -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar MarkdownParseTest.java; /software/CSE/oracle-java-se-14/jdk-14.0.2/bin/java -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar org.junit.runner.JUnitCore MarkdownParseTest"`

Results I got:

![Combining commands 1]()
![Combining commands 2]()