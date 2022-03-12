# lab report5
## Find different bugs and discuss

Different tests always comes with different bugs as results.\
Today we are going to learn how to find the diffferent results in the tests and analyze the results of them.

## Find the tests with different results

First I get my implementation and week9's lab one. I chose two files (`15.md` and `17.md`) to make this comparation. To run 'MarkdownParse.java` of both implements, we can use
```
script.sh > results.txt
```
then save the result in file `results.txt`. Then, we can use the `diff` to compare the differences. 
```
diff markdown-parse-my/results.txt markdown-parse/results.txt 
```
And it will shows us the differences between them.


## Disscuss ecah test

## Test file 15

This is the test file with

<img width="127" alt="螢幕截圖 2022-03-11 下午4 46 28" src="https://user-images.githubusercontent.com/97696711/157996285-47cd64b5-5a5f-430d-babc-2c413f59c3c2.png">

And the week9's implementation printed out with 

```
[]
```

and my implentation printed out with 

```
\\*emphasis*
[]
```

According to [CommonMark](https://spec.commonmark.org/dingus/), it should print out with

<img width="135" alt="螢幕截圖 2022-03-11 下午4 42 03" src="https://user-images.githubusercontent.com/97696711/157996013-2e94d4ce-af2e-49b5-affd-3f7ce6dc604d.png">


Obviously, both our implementations are wrong.


For my implementation, it came out with a extra `[]` and two asterisks. I think it not only because the close parenthesis get the wrong spot, but also it might have some problems at the open bracket. So that it came out with extra an `\`. And it may went the for loop again to, then got an extra parenthesis mistakely after that.

<img width="600" alt="螢幕截圖 2022-03-11 下午5 02 21" src="https://user-images.githubusercontent.com/97696711/157997062-d0d194a4-1db4-40eb-9b2a-7c02673b94a1.png">

I think to deal with this bug, it needs to fix the open bracket spot. And to the extra parenthesis, I think it should add a line of code (`if`) to make sure the spots of `open parenthesis` and `cloase parenthesis` and return it correctly.


## Test file 17

This is the test file with

<img width="161" alt="螢幕截圖 2022-03-11 下午4 22 46" src="https://user-images.githubusercontent.com/97696711/157995080-e9c8f619-89f7-43da-b54c-5e48cad3c687.png">

The week9's implementation printed out with 

```
[]
```

and my implentation printed out with 

```
`` \[\` ``
[]
```

According to [CommonMark](https://spec.commonmark.org/dingus/), it should printedout with


<img width="174" alt="螢幕截圖 2022-03-11 下午4 38 57" src="https://user-images.githubusercontent.com/97696711/157995867-dc3e57aa-b049-490d-8674-5387251caaad.png">

Again, both our implementations are incorrect.


For week9's implementation, it printed out different spots and miss `\`. This will skip the following character after the slash. So when a backslash comes before the open bracket, it will skip the following contents. So I think here has the bug

<img width="464" alt="螢幕截圖 2022-03-11 下午5 26 49" src="https://user-images.githubusercontent.com/97696711/157998138-e0ab71a6-2d96-47b7-a413-64e0d895676c.png">

It should add some lines of program to find where the `open parenthesis` is, and if it came out with `\`, we should also check if we found all the open parenthesis and close parenthesis before and after the `\`, so that we can get all contents.

and also it came out with the extra `close parenthesis`, so I think here about the spot of close parenthesis, can change to `for loop` and `if` to add extra condition to deal with it.

<img width="600" alt="螢幕截圖 2022-03-11 下午5 02 21" src="https://user-images.githubusercontent.com/97696711/157998412-b7dfe9e6-a4df-40cf-8c0a-26430c62ebb2.png">

