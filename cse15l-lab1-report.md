
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
## Install VSCode

Visit [Visual Studio Code](https://code.visualstudio.com/) website. Follow the instructions to download and install it on your computer. And it looks like this.

*Note:*\
<img width="1280" alt="install VSCode" src="https://user-images.githubusercontent.com/97696711/149471270-fed275b5-a1d5-413f-8ac2-808859adfda3.png">

## Remotely Connecting

If you are on Windows: intall [OpenSSH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse). Then look up your [course-specific account for CSE15L](https://sdacs.ucsd.edu/~icc/index.php).

After getting your account, you can open a terminal in VSCode on the left top side.

<img width="533" alt="螢幕截圖 2022-01-14 上午12 16 50" src="https://user-images.githubusercontent.com/97696711/149474448-2da5783b-e8cb-4cc1-b5c8-001a06daa606.png">

Tpye in your account as command. It may looks like this.


`$ ssh cs15lwi22akl@ieng6.ucsd.edu`

Then it might get a message like this:

```
⤇ ssh cs15lwi22akl@ieng6.ucsd.edu<img width="947" alt="螢幕截圖 2022-01-14 上午1 10 11" src="https://user-images.githubusercontent.com/97696711/149489472-598cb9c1-1a6f-4462-bedb-cc1fd5a3793f.png">

The authenticity of host 'ieng6.ucsd.edu (128.54.70.227)' can't be established.
RSA key fingerprint is SHA256:ksruYwhnYH+sySHnHAtLUHngrPEyZTDl/1x99wUQcec.
Are you sure you want to continue connecting (yes/no/[fingerprint])?
```

Then type `yes`, press enter and type your password. It will show something like this.

<img width="619" alt="螢幕截圖 2022-01-06 上午11 50 21" src="https://user-images.githubusercontent.com/97696711/149476052-9d98e5aa-7611-4b44-b221-2d37764fd3ba.png">

*Note:*\
When I logged in my account, I could see the history of last login time. Though the lab course with sharing, actually I found that the `Hostname` is same for everyone, but the `Time`, `#Users`, `Load`, `Averages` are different from everyone. I think that is because the number of people that connect the server is real-time changes.

Now, your terminal is connected to the computer in the CSE basement. 

## Trying Some Commands

You can try to run some commands like `cd`, `cd ~`, `ls -lat`, `pwd`, `mkdir`, `cp` and so on.

<img width="609" alt="螢幕截圖 2022-01-06 上午11 56 55" src="https://user-images.githubusercontent.com/97696711/149479749-15f33365-ebcd-4848-9b66-e9c755196f28.png">

*Note:*\
Ls -a: list all files in current directory\
Ls -lat: list the details of all files  in current directory 

When you want to log out of the remote server, you can `Ctrl-D` and Run the command `exit`.

## Moving Files with scp

Right now we will try to copy a file from your computer to a remote computer. The command is called `scp`.\ 
Frist we creat a file on your computer called `WhereAmI.java` and put the following contents into it:

```
class WhereAmI {
  public static void main(String[] args) {
    System.out.println(System.getProperty("os.name"));
    System.out.println(System.getProperty("user.name"));
    System.out.println(System.getProperty("user.home"));
    System.out.println(System.getProperty("user.dir"));
  }
}
```


Run it using `javac` and `java` on your computer. And you may see something like this.

<img width="367" alt="螢幕截圖 2022-01-14 上午12 52 25" src="https://user-images.githubusercontent.com/97696711/149486795-ed8f48fb-5ddf-43b4-a251-04201209f021.png">

Then in the terminal run this command. (with your username）

```
scp WhereAmI.java cs15lwi22akl@ieng6.ucsd.edu:~/
```
and

```
ssh cs15lwi22akl@ieng6.ucsd.edu
```

It will show something like this.

*Note:*\
<img width="947" alt="螢幕截圖 2022-01-14 上午1 10 11" src="https://user-images.githubusercontent.com/97696711/149489528-03a69b03-1c4d-40cf-ba99-018910b69c7d.png">

*Note:*\
It is differently based on the OS you're using. The second thime we are running on the remote server. This means that the
getproperty get the value mapped to the specified key passed as its argument. Changing and copying the file took me around 2 minutes, so it will take me around 200 minutes to do it 100 times.

## Setting an SSH Key

Now, we can try to use `ssh` key. We can use a program called `ssh-keygen` to creates a pair of files called the *public key* and *private key*. It can save a lot of time by use the `ssh` command to copy the keya and use the pair of files in place of your password.

You should run to set this up first:

```
# on client (your computer)
$ ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/joe/.ssh/id_rsa): /Users/joe/.ssh/id_rsa
Enter passphrase (empty for no passphrase): 
Enter same passphrase again: 
Your identification has been saved in /Users/joe/.ssh/id_rsa.
Your public key has been saved in /Users/joe/.ssh/id_rsa.pub.
The key fingerprint is:
SHA256:jZaZH6fI8E2I1D35hnvGeBePQ4ELOf2Ge+G0XknoXp0 joe@Joes-Mac-mini.local
The key's randomart image is:
+---[RSA 3072]----+
|                 |
|       . . + .   |
|      . . B o .  |
|     . . B * +.. |
|      o S = *.B. |
|       = = O.*.*+|
|        + * *.BE+|
|           +.+.o |
|             ..  |
+----[SHA256]-----+
```
If you’re on Windows, follow the [extra ssh-add steps](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_keymanagement#user-key-generation).

This created two new files on your system; the private key (in a file `id_rsa`) and the public key (in a file `id_rsa.pub`), stored in the `.ssh` directory on your computer.

Now we need to copy the public (not the private) key to the `.ssh` directory of your user account on the server.

```
#use your username and the path you saw in the command above
$ ssh cs15lwi22akl@ieng6.ucsd.edu
<Enter Password>
# now on server
$ mkdir .ssh
$ <logout>
# back on client
$ scp /Users/lijiajia/.ssh/id_rsa.pub cs15lwi22akl@ieng6.ucsd.edu:~/.ssh/authorized_keys
```
You should be able to `ssh` or `scp` from this client to the server without entering your password.\
You will see something similar like this.

*Note:*\
<img width="965" alt="螢幕截圖 2022-01-14 上午2 22 10" src="https://user-images.githubusercontent.com/97696711/149499994-97e86b2d-5581-44de-9317-47e2a8c241f6.png">
<img width="971" alt="螢幕截圖 2022-01-14 上午2 22 26" src="https://user-images.githubusercontent.com/97696711/149500017-d0951d25-5135-4883-9712-67c99f0d099e.png">

*Note:*\
This time I used around a minute to editing and running WhereAmI.java, so it is about a minute is saved each time.

## Optimizing Remote Running


