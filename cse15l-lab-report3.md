# lab report3
## Copy Whole Directories with `scp -r`

What should we do when we want to copy our whole directory to the server?\
To fulfill this requirement, we can command `scp -r`. 

## *Copy whole markdown-parse directory to ieng account*
1. Find that the working directory is our checkout of markdown-parse

```
⤇ pwd
```
<img width="342" alt="螢幕截圖 2022-02-11 下午2 14 21" src="https://user-images.githubusercontent.com/97696711/153677795-96749903-f191-4f71-b9c3-c0f59610a271.png"><img width="554" alt="螢幕截圖 2022-02-11 下午3 06 32" src="https://user-images.githubusercontent.com/97696711/153682585-532706f5-d9cc-4a6f-acd6-f23d761b74be.png">

```
⤇ ls
```
<img width="431" alt="螢幕截圖 2022-02-11 下午2 14 33" src="https://user-images.githubusercontent.com/97696711/153677809-47c904de-b249-48d7-a560-5e1ebe2364f2.png">


2. Use `scp` to copy the directory(represented by `.`) to the remote server
```
$ scp -r . cs15lwi22@ieng6.ucsd.edu:~/markdown-parse
```
Here, `-r` option tells `scp` to work recursively.\
The `.` is the source, and is the current directory.\
The `~/markdown-parse` tells `scp` to create the `markdown-parse` directory on the remote server (if it doesn’t exist), and then copy the contents of this directory recursively there.

<img width="575" alt="螢幕截圖 2022-02-11 下午2 19 55" src="https://user-images.githubusercontent.com/97696711/153678397-dddca543-3d8b-4ead-9458-aac0facb2de2.png">


3. Then we can log into the server with `ssh` and see all of our files there in a directory called `markdown-parse`

```
⤇ ssh cs15lwi22@ieng6.ucsd.edu
```
```
[cs15lwi22@ieng6-201]:~:99$ ls markdown-parse
```
<img width="535" alt="螢幕截圖 2022-02-11 下午2 29 47" src="https://user-images.githubusercontent.com/97696711/153679433-30b4fba1-0cd5-47f1-b8c5-17838038ef9b.png">

Note that when we do this it copies not just the files we see with `ls`, but all of the files in `.git` as well.


3.5. Addition, you can have more control over what gets copied. 

Try this command:
```
⤇ scp -r *.java *.md lib/ cs15lwi22@ieng6.ucsd.edu:markdown-parse
```
<img width="551" alt="螢幕截圖 2022-02-11 下午2 34 22" src="https://user-images.githubusercontent.com/97696711/153679850-d3e87c98-95eb-430c-9a5e-053984b72e30.png">

The different is, this command is to copy the specific file in your directory, instead of copying the whole directory.

That's it, we finish copying.


## *Log into the ieng6 account after copying, then compile and run*
As above we logged in the ieng6 account, then we are going to compile and run the test.\
Remind:
log in with the following code.
```
ssh cs15lwi22@ieng6.ucsd.edu
```
<img width="529" alt="螢幕截圖 2022-02-11 下午3 07 03" src="https://user-images.githubusercontent.com/97696711/153682629-14c873c9-f882-4f0e-83ee-89d94cabd7eb.png">

Compile using the following code.
```
javac -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar MarkdownParseTest.java

java -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar org.junit.runner.JUnitCore MarkdownParseTest
```
Then, it should comes with success.\
<img width="552" alt="螢幕截圖 2022-02-11 下午3 08 05" src="https://user-images.githubusercontent.com/97696711/153682722-b789c713-08fa-4e8d-b1c8-a8ee8b21b35a.png">

## *Combine `scp`, `;`, and `ssh` to copy the whole directory and run the tests in one line*
We can use semicolons to run multiple commands on the same line in most terminals.\
We can try command like this:
```
$ scp -r . cs15lwi22akl@ieng6.ucsd.edu:~/markdown-parse; javac -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar MarkdownParseTest.java; java -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar org.junit.runner.JUnitCore MarkdownParseTest
```
<img width="550" alt="螢幕截圖 2022-02-11 下午3 17 46" src="https://user-images.githubusercontent.com/97696711/153683469-862bdb4f-fc4e-4c78-8e47-3988d70fba64.png">
...

<img width="510" alt="螢幕截圖 2022-02-11 下午3 17 25" src="https://user-images.githubusercontent.com/97696711/153683433-2215bc5b-490b-48d7-8123-71d0de3e0753.png">

In this way, we can run mutiple commands once, and we also save some times.

## Hope you enjoy.:)
In this section, we learn and report how to copy whole directories with `scp -r` and check if coping is successful. When we do coding, it is really useful and important to know how to copy file between remote and command server, and this knowledge must be used in your future life.
