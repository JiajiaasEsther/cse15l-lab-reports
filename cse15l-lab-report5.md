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

**1. Test file 15**
This is the test file with

<img width="399" alt="螢幕截圖 2022-03-11 下午3 04 21" src="https://user-images.githubusercontent.com/97696711/157986147-c8cbe72d-d557-4bdd-88bd-fc4599cc2e09.png">

And the week9's implementation printed out with `[]`, but my implentation printed out with `\\*emphasis*
[]`


**2. Test file 17**
This is the test file with

<img width="161" alt="螢幕截圖 2022-03-11 下午4 22 46" src="https://user-images.githubusercontent.com/97696711/157995080-e9c8f619-89f7-43da-b54c-5e48cad3c687.png">

And the week9's implementation printed out with `[/foo]`, but my implentation printed out with 
`
`` \[\` ``
[]
`
