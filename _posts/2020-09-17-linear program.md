---
layout: post
title: " linear algorithm Simplex method"
date:   2020-09-17
tags: [network]
comments: true
author: zhang
---
# ILP
ILP is NP-hard, therefore we can reduce any NP-complete optimization problem to ILP.  

the optimal solution of the LP is only better than the optimal of ILP:every feasible point from the ILP is still feasible in the LP  
# LP
linear programs are solvable in polynomial time  
<img width="521" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/9abaccf3-8718-457b-ac49-87e256ae066b">
## standard form
<img width="538" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/4327ded7-082c-4aaa-9bb1-b376cd1a8391">

## Maximum Flow
<img width="379" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/0f60fffc-b9b2-40c3-971f-ef4334c90ae2">

## Vertex Cover
<img width="557" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/296871a2-dd32-4fa4-bb52-ba66aa3bf57b">

## ILP for vertex cover
<img width="568" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/9cd218a5-9b60-411a-8a41-64b75708955f">

## LP relaxation
<img width="567" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/b8a33d9c-f443-4cca-b3db-0a03154df990">

## Simplex method

### 转轴操作
理解为从一个顶点走向另一个顶点  


## knapsack problem
<img width="571" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/e2aa6da7-7387-4c16-9981-8eb28153b2a5">


## LP duality
The dual of the dual of a linear program is the linear program itself  

### Weak Duality 
<img width="452" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/8498ea5a-dfca-4221-81fa-db437ab2741e">

### Strong Duality
<img width="463" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/bde10e90-3e6a-4544-ac60-00aa2f6e124e">



https://tcs.nju.edu.cn/wiki/index.php?title=%E9%AB%98%E7%BA%A7%E7%AE%97%E6%B3%95_(Fall_2022)  
http://tcs.nju.edu.cn/slides/aa2022/DP.pdf
