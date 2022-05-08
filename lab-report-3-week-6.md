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

---

The next Group Choice was to **_Setup Github Access from ieng6_**

Using the tutorial given in Lab 5, I generated and added new SSH keys so that I could use the git commands: `git commit` and `git push` from the `ieng6` server. 

Below is a screenshot of my public key on my GitHub account after adding the new SSH key:

![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/public%20key%20on%20github.png?raw=true)

Additionally, the public and private keys are also present in the hidden `.ssh` folder in my user account. See this screenshot:

![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/keys%20on%20user.png?raw=true)

I have the public key, `id_rsa.pub` opened, while the private key, `id_rsa.pub` is in the `.ssh` directory, but remains unopened.

Next, I cloned my `cse15l-lab-reports` repository to my `ieng6` account and made a change. I then committed the change and used the command: `git push origin main` to ensure that the new SSH keys are working properly. See the following screenshot to see it working correctly:

![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/running%20tests%20on%20ieng6.png?raw=true)

You can see that after I use `git clone` to clone the repository, it shows up as a new directory on my `ieng6` account. I then enter `touch justForFun.txt` to create a new txt file. This is a new change, so when I enter `git status`, it will state that there has been a change that needs to be added/committed. Therefore, I enter `git add justForFun.txt` to add the change in the working directory to the staging area. Then, I enter `git commit -m "Added justForFun.txt"`, which commits the change with an additional descriptive message. Finally, because of the SSH keys I had created, I am able to push the changes directly from the command line by using `git push origin main`. 

Finally, [here](https://github.com/stellaji/cse15l-lab-reports/commit/3c3ac8ebe550850a57e098398adcc91fcd101bca) is a link to the commit that is shown in the above screenshot.

---

Lastly, we will **_Copy Whole Directories with `scp -r`_**

In this Group Choice, we use the `scp -r` to recursively copy an entire directory over to another location. Specifically, in this following screenshot, I copy the entire `markdown-parser` directory and use `scp -r` to copy it over to my `ieng6` account:

![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/scp%20-r.png?raw=true)

You can see that in my course-specific account, there is now a directory named `markdown-parser` that contains all the files and folders that the original directory (located on my own computer) had contained.

Furthermore, I can use `ssh ieng6` to log on to my course-specific account and compile/run the tests for my `markdown-parser` repository. Because all the necessary files and folders are copied over and present, all of the tests should run without issue. You can see in this following screenshot that all my tests run fine:

![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/running%20tests%20on%20ieng6.png?raw=true)

We can also combine `scp`, `;`, and `ssh` to do the same thing and copy the whole directory, but all in one line!

The command would look something like this: 
