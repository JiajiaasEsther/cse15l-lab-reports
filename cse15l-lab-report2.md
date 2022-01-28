# Lab Report2
## Fix the bugs of three different codes. 
It is common to come with the bug when we do coing. In this lab section, we can try to debug.\
Here are some example bugs with the progress and results during fixing.

## 1. First test
* **Code change**
<img width="1218" alt="螢幕截圖 2022-01-28 下午2 55 02" src="https://user-images.githubusercontent.com/97696711/151632967-4726e0f6-8dab-4d7a-9198-95d5f8b46a9c.png">

* **[Link](https://github.com/JiajiaasEsther/markdown-parse-main/blob/803e6146fe9ad230628f7aaee0d47ecf313039bc/test-file.md) of the test file for the failure-inducing input**

* **Symptom of the failure-inducing input**

<img width="705" alt="螢幕截圖 2022-01-28 下午2 58 50" src="https://user-images.githubusercontent.com/97696711/151633130-6d1f0237-57bc-4acd-8f21-9f64f3bb2749.png">

* **Descributions of the relationship between the bug, the symptom, and the failure-inducing input**


## 2. Second test
* **Code change**
<img width="1218" alt="螢幕截圖 2022-01-28 上午5 56 31" src="https://user-images.githubusercontent.com/97696711/151559119-b54b5d34-477c-4347-b482-8455f23be609.png">

* **[Link](https://github.com/JiajiaasEsther/markdown-parse-main/blob/b49450e78fdfff7a6c470f131d92b0e5525bf8b6/FirstDebug.md) of the test file for the failure-inducing input**

* **Symptom of the failure-inducing input**

<img width="600" alt="螢幕截圖 2022-01-28 上午5 49 15" src="https://user-images.githubusercontent.com/97696711/151558055-2393426a-6324-4286-883c-23561e85044e.png">

* **Descributions of the relationship between the bug, the symptom, and the failure-inducing input**



## 3. Third test

* **Code change**
<img width="1215" alt="螢幕截圖 2022-01-28 下午2 45 03" src="https://user-images.githubusercontent.com/97696711/151632016-06e7ece1-691e-48d7-a4bb-ce5cb1dc1001.png">

* **[Link](https://github.com/JiajiaasEsther/markdown-parse-main/blob/ce722b393a311502772407d672632d2988132d3c/SecondDebug.md) of the Test file for the failure-inducing input**


* **Symptom of the failure-inducing input**
<img width="605" alt="螢幕截圖 2022-01-28 下午2 39 59" src="https://user-images.githubusercontent.com/97696711/151631298-d2930f30-5546-43ff-91e0-a526d0b7da77.png">

* **Descributions of the relationship between the bug, the symptom, and the failure-inducing input**

The reason why this program fail is there is a "()" between the first open parantheses and last closed parantheses, it causes the extra letters shows after the last closed paranthese. Then, the nextOpenBraket keep coming out with integer -1, it causes the program witha infinite loop until out of the memory. In order to debug, we can similarly add a condition that when the interger nextOpenBraket equals -1, we are going to break this loop. and return. Then, the program won't be keep runing and not stop.

