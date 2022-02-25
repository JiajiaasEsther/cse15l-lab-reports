# Lab Report4
## Test snippet
It is unknown if the test works in different codes.\
In this lab, we have three different snippets and two different codes to test each of them and see how it work. Also, we can see if we can find a way to debug and make it work.


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

<img width="618" alt="螢幕截圖 2022-02-25 上午3 07 39" src="https://user-images.githubusercontent.com/97696711/155705352-e418ef5e-9877-4063-98ae-432faba13169.png">

Or we can also do it like this


## Run the code
Then, run this code at the command line using these two commands:
```
javac -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar MarkdownParseTest.java

java -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar org.junit.runner.JUnitCore MarkdownParseTest
```

* For **my implement**, the snippet 1 and snippet 3 failed, and the snippet 2 success.
<img width="715" alt="螢幕截圖 2022-02-25 上午3 12 25" src="https://user-images.githubusercontent.com/97696711/155705693-9bb6fc37-527a-4163-8e4f-22efff6a505a.png">

* For **the implemention I reviewed**, the snippet 1 and snippet 2 failed, and the snippet 3 success.

<img width="704" alt="螢幕截圖 2022-02-25 上午3 17 01" src="https://user-images.githubusercontent.com/97696711/155706333-5c25b83d-6f1e-45a5-8430-06b56bf213c4.png">

## Answer questions
* 
* 
* For snippet 3, I used more than 10 lines of code change to make my program work.\

So actually in snippet 3, my failure is because of the string is too long that out of bounds. What I did here is I use a for loop and if to split the line. After spliting them seprately, I checked if there are any bracket or parantheses exist in the line. Then check if exists to determine the program will continue running or print out the line. After all these, the program won’t have bug becuase of the string index out of bounds, also it can print out the context successfully.\

The reason why it would be more involved change is because I seprate the string. So actually I didn't make a super huge change for the current code, I just add for loop and if, and change all the 'markdown.' to 'line' becuase I break a long string into two, so the name of the string also changed. So if we need to change all the 'markdown.', that makes the change can't be small.

<img width="938" alt="螢幕截圖 2022-02-25 上午1 14 13" src="https://user-images.githubusercontent.com/97696711/155694329-97e2e6a3-66a0-48b8-8693-b34b591488be.png">
