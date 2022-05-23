# Welcome to Lab Report 4!
> Written and Submitted by Stella Ji, Section B01

---

In this lab, we will test the implementation of `markdown-parse` for several given code snippets.

First off:

You can find the link to **my own markdown-parse repository** [here](https://github.com/stellaji/markdown-parser.git)

You can find the link to **the markdown-parse repository that my group and I reviewed in Week 7** [here](https://github.com/nquach1515/markdown-parser-cse15l)

**_Snippet 1_**

Using the [CommonMark Demo Site](https://spec.commonmark.org/dingus/), I can see that the expected output is:

```
[a link](url.com)

another link`

cod[e

code]
```
To show what should be a link and what should not, here is a screenshot of that: 

![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/expected%20output.png?raw=true)

Continuing on, this is a screenshot of this test that I wrote to test the new file:

![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/test.png?raw=true)

As for the outputs, **my repository** outputted this:

![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/s1%20my%20output.png?raw=true)

My program worked as expected for Snippet 1.

Meanwhile, **the other group's repository** outputted this:

![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/s1%20their%20output.png?raw=true)

Their program worked as expected for Snippet 1.

**My repository** works for Snippet 1 because my code does not even take backticks into consideration. The program only cares whether or not the 
parentheses or square brackets are completed and in pairs. 

---

**_Snippet 2_**

Using the [CommonMark Demo Site](https://spec.commonmark.org/dingus/), I can see that the expected output is:

```
[a nested link](b.com)

a nested parenthesized url

some escaped [ brackets ]
```

To show what should be a link and what should not, here is a screenshot of that: 

![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/s2%20expected%20output.png?raw=true)

Continuing on, this is a screenshot of this test that I wrote to test the new file:

![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/s2%20test.png?raw=true)

As for the outputs, **my repository** outputted this:

![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/s2%20my%20output.png?raw=true)

My program did not work as expected for Snippet 2. It failed to output the first link: `b.com`. However, it did successfully output both `a.com((`
and `example.com`.

Meanwhile, **the other group's repository** outputted this:

![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/s2%20their%20output.png?raw=true)

Their program did not work as expected for Snippet 2. For the first outputted link, instead of the expected `b.com`, their program outputted `a.com` 
instead.

**My repository** did not fully work for the first line in Snippet 2: `[a [nested link](a.com)](b.com)`. It seems that this line was just removed
during the parsing and it seems like the reason for this removal is that in my program, the last if statement in the while loop removes the first line 
if it assumes an image link and does not find an exclamation mark.

Therefore, the fix should be less than 10 lines, in that there just needs to be addition of code that checks if there is an exclamation mark first,
to identify a link as an image. Then, it should only remove the link if the exclamation mark is improperly placed.

---

**_Snippet 3_**

Using the [CommonMark Demo Site](https://spec.commonmark.org/dingus/), I can see that the expected output is:

```
this title text is really long and takes up more than one line

and has some line breaks]( https://www.twitter.com )

this title text is really long and takes up more than one line

[this link doesn't have a closing parenthesis](github.com

And there's still some more text after that.

[this link doesn't have a closing parenthesis for a while](https://cse.ucsd.edu/

)

And then there's more text
```

To show what should be a link and what should not, here is a screenshot of that: 

![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/s3%20expected%20output.png?raw=true)

Continuing on, this is a screenshot of this test that I wrote to test the new file:

![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/s3%20test.png?raw=true)

As for the outputs, **my repository** outputted this:

![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/s3%20my%20output.png?raw=true)

My program did not work as expected for Snippet 3. It failed to output the correct link for the first line, and outputs a line break instead. As for
the second link, my program wrongly outputs a line break after the correct link. Then it incorrectly output ` github.com` and reads the line for the 
`https://cse.ucsd.edu/` link in correctly. Lastly, what should have been the first link ends up being outputted as the last line with another line break
at the end.

Meanwhile, **the other group's repository** outputted this:

![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/s3%20their%20output.png?raw=true)

Their program also did not work as expected for Snippet 3. Along with every link being accompanied by an extra line break, their program seems to have
`https://twitter.com` in the correct position. Additionally, it also incorrectly outputs `github.com`, meaning that it misses the lack of an ending
parenthesis.

**My repository** did not work for any of the links in Snippet 3.

It seems that every link is outputted with an extra line break, which tells me that my 
program is unable to deal with the empty spaces that are present in `snippet3.md`. Additionally, it seems that the extra spaces before the first link:
`https://www.twitter.com`, causes the program to move the link to end of the line when it comes to outputting. One last issue is the output of 
`github.com` when it should not be outputted. This suggests the my program is unable to account for missing end parenthesis. 

I do not think that these bugs can be fixed with <10 lines of code. The first changes that I would make are to make my program account for empty spaces
in the form of extra line breaks, tabs, etc. 

---

And with that, this concludes this Lab Report! Thank you for reading! ૮˶ᵔᵕᵔ˶ა
