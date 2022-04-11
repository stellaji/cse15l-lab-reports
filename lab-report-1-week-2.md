Hello, everyone! Today, we will be learning how to log into a course-specific account on ieng6 for CSE 15L.

Firstly, you will need to **install VSCode:**

To do so, you will need to install [VSCode](https://code.visualstudio.com/) on your laptop. 

Once you have it downloaded, make sure that it is running correctly. Your screen should look something like this:

*VSCode Screenshot*
![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/VS%20Code%20Screenshot.png?raw=true)

The next step is to **connect remotely:**

If you are using a Windows laptop, make sure to download [this](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse)

Next, use the UCSD ETS Account Look-Up Tool [here](https://sdacs.ucsd.edu/~icc/index.php) to find the account you want to connect to.

Then, open up the terminal in VSCode and type in this command, replacing the letters "zz" with that of your own account: `$ ssh cs15lsp22zz@ieng6.ucsd.edu`

You will probably be prompted to input yes/no/fingerprint, and yet again for your password. Go ahead and type yes and your password when asked.

You then should see something like this, which means you are now connected to a computer in the CSE basement!

*ssh Screenshot:*
![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/ssh%20Output%20Screenshot.png?raw=true)

Then, you can start **trying some commands:**

To help you out, here is a list of commands that you could try:
* cd~
* cd
* ls -a
* ls -lat
* ls <directory> , make sure to replace <directory> with the directory you want to be in
* cp 
* cat 
  
Here is an example of some of the commands being used:
 
*commands Screenshot:*
![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/commands%20Screenshot.png?raw=true)

Another useful skill to learn is to **move files with `scp`**

To do so, first if you are in the remote connection, enter `exit` to return to your own client.
  
Then, create a .java file that you will later move to the CSE server. Add a print statement and compile to make sure that it works correctly.
  
Next, use this command: `scp WhereAmI.java cs15lsp22zz@ieng6.ucsd.edu:~/` (make sure to substitute zz for your own account's letters)
  
You will again be prompted to input yes/no/fingerprint as well as your password. Go ahead an input yes and your password.
  
If everything works correctly, then your terminal should look something like this:
  
*scp Screenshot:*
![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/scp%20Screenshot.png?raw=true)

By now, you may be frustrated by the repetitive asking of yes/no/fingerprint and your password. Don't worry, there is a way around it!

This is called **ssh Keys**

To do this, first make sure that you are on the client. If not, make sure to input `exit` to exit out of the server.
  
Then, input `ssh-keygen` to which you will see something like

```
Generating public/private rsa key pair.
Enter file in which to save the key
(/Users/<user-name>/.ssh/id_rsa): /Users/<user-name>/.ssh/id_rsa
Enter passphrase (empty for no passphrase):
```
  
You do not need to type anything, simply press the enter key on your keyboard, as you want there to be no passphrase.
  
Then, a randomart image will be generated.
  
The next step is to copy the public (*not* the private) key to your server.
  
To do so, you will first need to ssh into the server and create an .ssh directory. This will be the location that the public key will be copied into.

You should input `mkdir .ssh` to create this directory. After doing so, exit the server.
  
Then, you will use the scp command to copy the public key over, which should look something like this: 
`scp /Users/<user-name>/.ssh/id_rsa.pub cs15lsp22zz@ieng6.ucsd.edu:~/.ssh/authorized_keys`
  
The whole process should look something like this:
  
*ssh keys Screenshot:*
![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/ssh%20keys%20Screenshot.png?raw=true)

Lastly, we will try to **optimize remote running:**
  
There are many ways to make remote running a little simpler, with less lines. Here are some examples:
 
* Use semicolons to run multiple commmands in one single line. Try: `cp demo.java copyOfDemo.java; javac copyOfDemo.java; java demo`
* Write a command in quotes at the end of an ssh command to run it from your remote client server. Try: `ssh cs15lsp22zz@ieng6.ucsd.edu "ls"`

Here is an example screenshot of those commands being run: 
  
*Optimizing Remote Running Screenshot*
![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/Optimizing%20Remote%20Running.png?raw=true)
  
**Congratulations! You just finished Lab 1!**
