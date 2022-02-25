# Lab Report4
## Test snippet
It is unknown if the test works in different codes.\
In this lab, we have three different snippets and two different codes to test each of them and see how it work. Also, we can see if we can find a way to debug and make it work.

**Repository**

Here are the link of [my implement](https://github.com/JiajiaasEsther/markdown-parse3) and [the implemention I reviewed](https://github.com/JiajiaasEsther/markdown-parse4).

**Snippet 1**
```
[a link`](url.com)

[another link](`google.com)`

[`cod[e`](google.com)

[`code]`](ucsd.edu)`

```

**Snippet 2**
```
[a [nested link](a.com)](b.com)

[a nested parenthesized url](a.com(()))

[some escaped \[ brackets \]](example.com)
```

**Snippet 3**
```
[this title text is really long and takes up more than 
one line

and has some line breaks](
    https://www.twitter.com
)

[this title text is really long and takes up more than 
one line](
    https://ucsd-cse15l-w22.github.io/
)


[this link doesn't have a closing parenthesis](github.com

And there's still some more text after that.

[this link doesn't have a closing parenthesis for a while](https://cse.ucsd.edu/



)

And then there's more text
```

## Decide on what it should produce
We can do this by VScode preview or [the ComminMark demo site](https://spec.commonmark.org/dingus/).\
Here, I am going to use the ComminMark demo site to achieve this goal.

Snippet 1:
<img width="1013" alt="螢幕截圖 2022-02-24 下午9 37 37" src="https://user-images.githubusercontent.com/97696711/155660329-b2629164-f98a-4ae7-9380-0cd317f399be.png">
Snippet 2:
<img width="1028" alt="螢幕截圖 2022-02-24 下午9 38 27" src="https://user-images.githubusercontent.com/97696711/155660437-952d182f-cbd5-4bfa-a42f-78d046e3e072.png">
Snippet 3:
<img width="993" alt="螢幕截圖 2022-02-24 下午9 39 29" src="https://user-images.githubusercontent.com/97696711/155660530-47710e40-ef44-4257-aac1-26a09db1068d.png">

## Turn them into tests
To turn it into a test, we can do it like this 

<img width="1161" alt="螢幕截圖 2022-02-25 下午2 20 09" src="https://user-images.githubusercontent.com/97696711/155810888-65c0de65-ee9e-4422-b1e6-eb31849bf091.png">

Or we can also do it like this

<img width="1091" alt="螢幕截圖 2022-02-25 下午2 17 47" src="https://user-images.githubusercontent.com/97696711/155810657-11e0d00d-eaee-4d2f-b631-4ae10f6d6ae6.png">

## Run the code
Then, run this code at the command line using these two commands:
```
javac -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar MarkdownParseTest.java

java -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar org.junit.runner.JUnitCore MarkdownParseTest
```

* For **[my implement](https://github.com/JiajiaasEsther/markdown-parse3)**, sadly, all three snippets failed.
 
 <img width="784" alt="螢幕截圖 2022-02-25 下午2 22 09" src="https://user-images.githubusercontent.com/97696711/155811087-a457c9af-cc13-4ef4-9347-4715073e1a63.png">

* For **[the implemention I reviewed](https://github.com/JiajiaasEsther/markdown-parse4)**, it is deeply sad that none of the snippets passed.

<img width="779" alt="螢幕截圖 2022-02-25 下午2 24 29" src="https://user-images.githubusercontent.com/97696711/155811307-03ad126d-549c-457c-8a12-f84513d774e3.png">

## Answer questions
* For snippet 1, I don't think I can make a small (<10 lines) code change that will make your program work for snippet 1 and all related cases that use inline code with backticks. As we saw, compare the output and expect, my `openParen` and `CloseBracket` are all in the different positions. The code of mine actually get the strings in the parentheses, but the expect output actually print more of the string in the brackets. So if we want to make the program works, we need to first change the position that we need to print out, then, we can see that there is backticks and extra bracket between the string, we need to find way to change the code to determine what to print when we see backticks or extra bracket. And, we can see there is an extra `(url.com)` shows up, so we need extra change to make this happen. All of these problems together, I don't think it can finish code change in 10 lines, it probably will be a huge project for chaning it.

* For snippet 2, I don't think I can meke it success in 10 lines of codes. In the Junit test, it said what I printed was actually an empty list. But what I expected is actually `[a nested link](b.com)", "a nested parenthesized url", "some escaped [ brackets ]`. So what I should print is everything between brackets. But my code mess up when there is brackets contain parentheses or parentheses contain brackets this kind of problem. So to fix it, I need to change most of code to tell them that the what I should print when face the nest parentheses. I actually need to change all the index of my `openParen`, `CloseParen`, `openBracket` and `CloseBracket`. So it must be a huge work to do that and can't finish using less then 10 lines of codes.

* For snippet 3, I don't think make it success in 10 lines of codes.\
The reason why it would be more involved change is because the strings are too long, so I need to seprate the long string, so that it won't happen *outofbounds*. So actually I need to make a quite huge change for the current code. I need to add for loop and if, and change all the `markdown.` to `line` becuase I break a long string into two, so the name of the string also changed. So if we need to change all the `markdown.`, that makes the changes can't be small.
So here is what I try:

<img width="938" alt="螢幕截圖 2022-02-25 上午1 14 13" src="https://user-images.githubusercontent.com/97696711/155694329-97e2e6a3-66a0-48b8-8693-b34b591488be.png">

And I used more than 10 lines of code just make my program work.\

## Hope you enjoy.:)
In this section, we turn snippets into tests and run tests. We learn and discuss what will happen and how to change the codes to make the tests work. When we do coding, it is really useful and important to know how many change we approxiately need to make to make the program work. I believe it is a good skill for us to master.
