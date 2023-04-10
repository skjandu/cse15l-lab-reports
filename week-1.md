# Lab 1 - Remote Access and File System

## Step 1: Install VScode
The first step is to install VScode by going to the following [link](https://code.visualstudio.com/). Follow the instructions that are listed to download and install this tool on your computer. After VScode has been installed, open up a new window. It should look like this (note that I have chosen dark mode so this might vary based on your default settings): 

![Image](vscode-tutorial.png) 

## Step 2: Remotely Connecting
Find your course-specific username at the following [link](https://sdacs.ucsd.edu/~icc/index.php). Use this [tutorial](https://drive.google.com/file/d/17IDZn8Qq7Q0RkYMxdiIR0o6HJ3B5YqSW/view?usp=share_link) to reset your password to the account. Every username has the same format: cs15lsp23zz@ieng6.ucsd.edu. The letters that replace 'zz' is unique to each person enrolled in the course, so make sure to remember those two letters. You will use this to log in to the remote server.

Open a terminal in VSCode. This can be done using Ctrl or Command + `, or selecting the Terminal → New Terminal option in the menu. You will be using the ssh command to gain remote access to a computer in the CSE basement. To log on to the server, you must verify your identity using your unique course specific account. Replace the 'zz' below with the letters in your username:

```
$ ssh cs15lsp23zz@ieng6.ucsd.edu
```

Because this is probably the first time you are logging into this server, your terminal will ask you "Are you sure if you want to continue connecting (yes/no/[fingerprint])?" Type "yes" and press enter to continue logging in. Then, it will prompt you to type in your password, which you just created when resetting your password. Although it will not look like anything is being typed on your terminal, the keys that you press are considered part of your password. 

Once you are logged in, it should display a message similar to the one shown in the image below: 

![Image](ssh-login.png)

Congrats, you're in! 

## Step 3: Try Some Commands
In order to get familiar with commands, you can try them out on the remote computer that you are logged into. Try going into different directories using "cd" or list the files and folders in different directories using "ls." Below are some of these commands (and more) tried out in the remote server along with their results: 

![Image](terminal-commands.png)

