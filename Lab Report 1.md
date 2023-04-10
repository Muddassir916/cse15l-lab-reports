# **Greetings!**
Today we will show you how to successfully log into a course-specific account on `ieng6` using Visual Studio Code! After confirming you have your school account set up and working, there are three main steps you must follow to make sure you are connected remotely! These steps include: 

-Installing Visual Studio Code
-Remotely Connecting
-Trying Some Commands

---
## Step 1: Installing Visual Studio Code
Visit the VScode website https://visualstudio.microsoft.com/downloads/ and follow the instructions to download the software on your computer. After installing it fully and opening it, you should see a screen similar to: 

## Step 2: Remotely Connecting
Once VScode is up and running, now we must connect to the remote server. To do so, we need to first install git, which will be very useful for connecting:

[git](https://gitforwindows.org/)

After downloading and going through the full installation, return to VScode and open a new terminal. This can be done by going: Terminal → New Terminal menu option, or using the shortcut Ctrl or Command + `. This is where you will connect to the server using your login information. After opening the git bash terminal copy and paste this command (not including the $ sign!). Before inputting the command, make sure to replace ‘zz’ with your course-specific account letters:

`$ ssh cs15lsp23zz@ieng6.ucsd.edu`

This is your first time connecting to a new server, so you will get a message similar to:

```⤇ ssh cs15lsp23zz@ieng6.ucsd.edu

The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.

RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.

Are you sure you want to continue connecting (yes/no/[fingerprint])?```


## Step 3: Trying Some Commands
Visit the VScode website https://visualstudio.microsoft.com/downloads/ and follow the instructions to download the software on your computer. After installing it fully and opening it, you should see a screen similar to:
