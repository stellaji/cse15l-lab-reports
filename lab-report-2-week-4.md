# Lab Report 2, Week 4

> Written by Stella Ji

For this lab, I will detail 3 code changes that my lab group worked on in Lab 3 to fix a bug.

## Code Change 1

*Screenshot*

![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/code%20change%201%20ss.png?raw=true)

*Link to Failure-inducing Test*

See why this change needed to be made [here](https://github.com/stellaji/markdown-parser/blob/main/breaking1.md)

*Symptom Output*

See what the program outputed before this change was made (symptom):
![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/symptom%201%20ss.png?raw=true)

*Description*

Before the change was made, the program would return an IndexOutOfBoundsException. This is because the code would have the value of `closeParen` be `-1`, since it could not be found. Therefore, when the `add()` method is called, an exception is thrown, since `-1` is not a valid argument. In other words, the bug is that there is no code to deal with a case where the closing parenthesis is missing, while the symptom is the IndexOutOfBoundsException that was thrown in the screenshot above. Therefore, this code change is necessary when testing `MarkdownParse.java` with any `.md` files that have links that are missing their closing parentheses.

## Code Change 2

*Screenshot*
