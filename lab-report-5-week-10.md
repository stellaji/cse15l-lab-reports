# Welcome to Lab Report 5!
> Written and Submitted by Stella Ji, Section B01

---

In this lab, we will discuss two different test files in which my implementation had different answers than the implementation that was provided for Lab 9.

Firstly, I ran into a problem in that my build keeps failing for my own `markdown-parser` repository. 

Specifically, this is the error in GitHub: [make error](https://github.com/stellaji/markdown-parser/runs/6841433958?check_suite_focus=true)

If that link does not work, here is an image: 

![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/build%20error.png?raw=true)\

When I try to run `bash script.sh > results.txt` from the command line in the Terminal, I get outputted this error message after a couple minutes:\

![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/out%20of%20heap%20error.png?raw=true)

My testing did run successfully on the other repository; in fact, I created a file called `results.txt` with the results that the program outputted after
I did all of the tests.

It looks something like this: 

![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/ss%20of%20results.png?raw=true)

If the build for my repository worked, then I would run the command `vimdiff /home/linux/ieng6/cs15lsp22/cs15lspe22aqh/my-markdown-parser/results.txt /home/linux/ieng6/cs15lsp22/cs15lspe22aqh/markdown-parser/results.txt`

That command should return numerous lines, to which i could pick two tests to base my lab report on.

For each test, I would first determine what the difference in outputs is, followed by an establishment of what the expected output is. I would then note 
down if either test outputted what was expected or if both of them failed. 

Depending on the above, I would possibly see what lines in my code caused this implementation test to go wrong. If I am able to, I would also correct the
error to fix the bug and wee if I could the test to work correctly. From there, hopefully the two repositories would both output the same and correct 
output. 

I will link both repositories here:

[My Repository](https://github.com/stellaji/markdown-parser.git)

[Other Repository](https://github.com/nidhidhamnani/markdown-parser.git)

I wish that the implementation testing of my own repository had worked, but I hope that this lab report that I have written shows that I would have known 
what to do.

Thank you for reading and enjny your summer :3
