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

## Turn them into tests, and run
To turn it into a test, we can do it like this 

<img width="545" alt="螢幕截圖 2022-02-24 下午10 12 29" src="https://user-images.githubusercontent.com/97696711/155664007-97a763b3-4d54-4884-9cff-6fff6fe6e46e.png">

Or we can also do it like this

<img width="535" alt="螢幕截圖 2022-02-24 下午10 15 34" src="https://user-images.githubusercontent.com/97696711/155664315-0ab16e6d-783b-4c1b-9086-07dd95f0f908.png">