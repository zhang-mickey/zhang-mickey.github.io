---
layout: post
title: " Coding and Cryptography"
date:   2024-02-01
tags: [Cryptography]
comments: true
author: zhang
---
"Coding theory and cryptography, the essentials" 
covering most of Chapters 1 through 6 as well as some parts of Chapters 11 and 12. 
#### 定义
![image](https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/d810c155-8374-4a3a-ab92-4198955d0920)


#### parity matrix 
根据parity matrix 解码

1 column is not enough unless their is a column of all 0.
2 columns are not enough unless their is a repeated column
##### 标准型
![image](https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/8acf2b6e-c0f1-4188-b769-86aca27f1bd5)

Reed-Solomon codes

BCH-codes
#### 汉明码
![image](https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/d83d1e14-2ab8-45d0-ae6d-0a71657b41e9)
也就是说
![image](https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/644ee4d1-1fc7-4e0b-8162-ddf15aaefb3b)

汉明码(7,4)
只能纠错一位，多了会confuse
![image](https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/ae49009e-034c-4a01-a335-91824aec8799)

linear codes

A linear code C must contain the zero word.

the distance of a linear code is the weight of the nonzero code- word of least weight.
