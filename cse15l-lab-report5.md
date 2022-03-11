# lab report5
## Find different bugs and discuss

Different tests always comes with different bugs as results.\
Today we are going to learn how to find the diffferent results in the tests and analyze them.

* **Find the tests with different results**
First I get my implementation. I didn't use the `diff` on the result of running a bash. I found there is getLinks method with other helper methods that I can use in implementation. So I just simply compare two tests by running each `getLinks` method in Markdown-Parse. Here is my code.


```
java MarkdownParse ./test-files/test name.md
```
Then I ran it for each test, and it printed out the results differently.

<img width="619" alt="螢幕截圖 2022-03-11 下午2 16 13" src="https://user-images.githubusercontent.com/97696711/157979946-d4583259-e656-45e0-838a-fdfa0f00a7c8.png">
