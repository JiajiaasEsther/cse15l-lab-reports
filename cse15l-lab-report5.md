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

## Test file 567

* **Output**

The week9's implementation printed out with empty bracket `[]`, and my implentation printed out with `[not a Link]`, which is not suppose to printed.

According to visual studio preview, the only valid link shoule be

`/url1`.<img width="705" alt="螢幕截圖 2022-03-18 下午4 11 51" src="https://user-images.githubusercontent.com/97696711/159095804-a83b7d3d-906e-4222-a6d9-343138cf9d1d.png">

So, both our implementations are wrong.

* **Discussion**

For my implementation, it came out with `[not a link]`, instead of `[/url]`. I think it is because there is not any program checking if there is any space between the parentese, and it doesn't check for colon in the md file. So these might cause the program print the invalid link or ignore the link.

<img width="702" alt="螢幕截圖 2022-03-18 下午4 31 29" src="https://user-images.githubusercontent.com/97696711/159096787-5198c635-6fb4-4bc5-816b-8d260314e698.png">

To deal with this bug, I think we can add two instance variables, as 'Indicator' of `space` and `colon`, then we can use 'indexOf` to find the index of space after the open parentheses in the while loop. We can check if the index of space appear between the open parentheses and close parentheses, then we can ignore the content and treat as a invalid link. Also, we can find the index of colon using `indexOf`. Then use `if` to see if the colon with no space in the link is after the close bracket and open parentheses. If so, then we can treat the link after the colon as a valid link.

## Test file 573

* **Output**

The week9's implementation printed out with `[/url]`, and my implentation printed out with empty bracket`[]`.

According to visual studio preview, there is no valid link, so it should printed out nothing.  

<img width="627" alt="螢幕截圖 2022-03-18 下午4 11 09" src="https://user-images.githubusercontent.com/97696711/159095762-518d1265-7d97-4d8e-8996-37aafd658d0f.png">

So, lab9's implementations is incorrect.

* **Discussion**

For week9's implementation, it printed out different spots and miss `\`. This will skip the following character after the slash. So when a backslash comes before the open bracket, it will skip the following contents. So I think here has the bug

<img width="464" alt="螢幕截圖 2022-03-11 下午5 26 49" src="https://user-images.githubusercontent.com/97696711/157998138-e0ab71a6-2d96-47b7-a413-64e0d895676c.png">

It should add some lines of program to find where the `open parenthesis` is, and if it came out with `\`, we should also check if we found all the open parenthesis and close parenthesis before and after the `\`, so that we can get all contents.

and also it came out with the extra `close parenthesis`, so I think here about the spot of close parenthesis, can change to `for loop` and `if` to add extra condition to deal with it.

<img width="600" alt="螢幕截圖 2022-03-11 下午5 02 21" src="https://user-images.githubusercontent.com/97696711/157998412-b7dfe9e6-a4df-40cf-8c0a-26430c62ebb2.png">

