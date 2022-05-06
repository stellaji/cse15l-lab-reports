# Welcome to Lab Report 3!
> Written and Submitted by Stella Ji, Section B01

---
In this lab, we will go over the three Group Choice Options from Lab 5.

First off, **_Streamlining ssh Configuration_**

This is a screenshot of my 'config' file, shown in VSCode:

![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/config%20file%20in%20vscode.png?raw=true)

This 'config' file was not initially present in my '~/.ssh' directory, so I first had to create the file using the 'touch' terminal command, which looked like 'touch config'. 

After creating the 'config' file, I did 'cat >config' to edit the file. I then added these lines of code:
...
Host ieng6
  HostName ieng6.ucsd.edu
  User cs15lsp22aqh
...

This edited 'config' file allows me to log into my course-specific account much faster using the command: 'ssh ieng6' as shown by this screenshot:

