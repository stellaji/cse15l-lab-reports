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

*scp Screenshot:*
![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/scp%20Screenshot.png?raw=true)

*ssh keys Screenshot:*
![Image](https://github.com/stellaji/cse15l-lab-reports/blob/main/ssh%20keys%20Screenshot.png?raw=true)
