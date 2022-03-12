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
* **Output**

This is the test file with

<img width="127" alt="螢幕截圖 2022-03-11 下午4 46 28" src="https://user-images.githubusercontent.com/97696711/157996285-47cd64b5-5a5f-430d-babc-2c413f59c3c2.png">

And the week9's implementation printed out with `[]`, but my implentation printed out with 
```
\\*emphasis*
[]
```

According to [CommonMark](https://spec.commonmark.org/dingus/), it should print out with

<img width="135" alt="螢幕截圖 2022-03-11 下午4 42 03" src="https://user-images.githubusercontent.com/97696711/157996013-2e94d4ce-af2e-49b5-affd-3f7ce6dc604d.png">


Obviously, both our implementations are wrong.

* **Discuss the bug**



## Test file 17
* **Output**

This is the test file with

<img width="161" alt="螢幕截圖 2022-03-11 下午4 22 46" src="https://user-images.githubusercontent.com/97696711/157995080-e9c8f619-89f7-43da-b54c-5e48cad3c687.png">

And the week9's implementation printed out with `[/foo]`, but my implentation printed out with 
```
`` \[\` ``
[]
```

According to [CommonMark](https://spec.commonmark.org/dingus/), it should printedout with


<img width="174" alt="螢幕截圖 2022-03-11 下午4 38 57" src="https://user-images.githubusercontent.com/97696711/157995867-dc3e57aa-b049-490d-8674-5387251caaad.png">

Again, both our implementations are incorrect.

* **Discuss the bug**



