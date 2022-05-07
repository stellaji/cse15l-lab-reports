# Welcome to Lab Report 3!
> Written and Submitted by Stella Ji, Section B01

---
In this lab, we will go over the three Group Choice Options from Lab 5.

First off, **_Streamlining ssh Configuration_**

This is a screenshot of my `config` file, shown in VSCode:

![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/config%20file%20in%20vscode.png?raw=true)

This `config` file was not initially present in my `~/.ssh` directory, so I first had to create the file using the `touch` terminal command, which looked like `touch config`. 

After creating the `config` file, I did `cat >config` to edit the file. I then added these lines of code:
```
Host ieng6
  HostName ieng6.ucsd.edu
  User cs15lsp22aqh
```

This edited `config` file allows me to log into my course-specific account much faster using the command: `ssh ieng6` as shown by this screenshot:

![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/Streamline%20ssh%20Configuration.png?raw=true)

This `ssh ieng6` command works because in the code block that I had added to the `config` file, I used the alias `ieng6` in the first line: `Host ieng6`

To show an instance of this alias working, I created a new file in my own computer called `fileToBeCopiedOver.txt`. 

I then used the `scp` command coupled with the alias name to copy this file over to my course-specific account. This was done by using the command: 
`scp fileToBeCopiedOver.txt ieng6:~/`

In this screenshot, you can see that the `fileToBeCopiedOver.txt` file can now be found in my course-specific account:

![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/scp%20after%20streamlined%20ssh.png?raw=true)


The next Group Choice was to **_Setup Github Access from ieng6_**

Lastly, we will **_Copy Whole Directories with `scp -r`_**

In this Group Choice, we use the `scp -r` to recursively copy an entire directory over to another location. Specifically, in this following screenshot, I copy the entire `markdown-parser` directory and use `scp -r` to copy it over to my `ieng6` account:

![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/scp%20-r.png?raw=true)

You can see that in my course-specific account, there is now a directory named `markdown-parser` that contains all the files and folders that the original directory (located on my own computer) had contained.

Furthermore, I can use `ssh ieng6` to log on to my course-specific account and compile/run the tests for my `markdown-parser` repository. Because all the necessary files and folders are copied over and present, all of the tests should run without issue. You can see in this following screenshot that all my tests run fine:

![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/running%20tests%20on%20ieng6.png?raw=true)

We can also combine `scp`, `;`, and `ssh` to do the same thing and copy the whole directory, but all in one line!

The command would look something like this: 
