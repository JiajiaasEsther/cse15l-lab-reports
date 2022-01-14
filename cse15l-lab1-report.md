
# Lab1 Report
## Introduction of how to log into a course-specific account.


**What we are going to do:**

* Installing VScode
* Remotely Connecting
* Trying Some Commands
* Moving Files with scp
* Setting an SSH Key
* Optimizing Remote Running

---
**Install VSCode**

Visit [Visual Studio Code](https://code.visualstudio.com/) website. Follow the instructions to download and install it on your computer. And it looks like this.

<img width="1280" alt="install VSCode" src="https://user-images.githubusercontent.com/97696711/149471270-fed275b5-a1d5-413f-8ac2-808859adfda3.png">

**Remotely Connecting**

If you are on Windows: intall [OpenSSH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse). Then look up your [course-specific account for CSE15L](https://sdacs.ucsd.edu/~icc/index.php).

After getting your account, you can open a terminal in VSCode on the left top side.

<img width="533" alt="螢幕截圖 2022-01-14 上午12 16 50" src="https://user-images.githubusercontent.com/97696711/149474448-2da5783b-e8cb-4cc1-b5c8-001a06daa606.png">

Tpye in your account as command. It may looks like this.

`$ ssh cs15lwi22akl@ieng6.ucsd.edu`

Then it might get a message like this:

`⤇ ssh cs15lwi22akl@ieng6.ucsd.edu
The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])?`

Then type `yes`, press enter and type your password. It will show something like this.

<img width="619" alt="螢幕截圖 2022-01-06 上午11 50 21" src="https://user-images.githubusercontent.com/97696711/149476052-9d98e5aa-7611-4b44-b221-2d37764fd3ba.png">

Now, your terminal is connected to the computer in the CSE basement. 

**Trying Some Commands**

You can try to run some commands like `cd`, `cd ~`, `ls -lat`, `pwd`, `mkdir`, `cp` and so on.

<img width="609" alt="螢幕截圖 2022-01-06 上午11 56 55" src="https://user-images.githubusercontent.com/97696711/149479749-15f33365-ebcd-4848-9b66-e9c755196f28.png">

Ls -a: list all files in current directory 

Ls -lat: list the details of all files  in current directory 

When you want to log out of the remote server, you can `Ctrl-D` and Run the command `exit`.

**Moving Files with scp**


