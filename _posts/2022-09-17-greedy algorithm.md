---
layout: post
title: " greedy algorithm"
date:   2022-09-17
tags: [network]
comments: true
author: zhang
---

## Dijkstra algorithm

## Minimum spanning Tree



### 坏了的计算器
<img width="405" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/ed743ebe-fb0c-406f-af57-a4d5781316bb">  

```
除了对 X 执行乘 2 或 减 1 操作之外，我们也可以对 Y 执行除 2（当 Y 是偶数时）或者加 1 操作。  

这样做的动机是我们可以总是贪心地执行除 2 操作：  
当 Y 是偶数，如果先执行 2 次加法操作，再执行 1 次除法操作，我们可以通过先执行 1 次除法操作，再执行 1 次加法操作以使用更少的操作次数得到相同的结果 [(Y+2) / 2 vs Y/2 + 1]。  
当 Y 是奇数，如果先执行 3 次加法操作，再执行 1 次除法操作，我们可以将其替代为顺次执行加法、除法、加法操作以使用更少的操作次数得到相同的结果 [(Y+3) / 2 vs (Y+1) / 2 + 1]。  
当 Y 大于 X 时，如果它是奇数，我们执行加法操作，否则执行除法操作。之后，我们需要执行 X - Y 次加法操作以得到 X。
class Solution:
    def brokenCalc(self, X: int, Y: int) -> int:
        #Y只能除以2或者+1
        res = 0
        while X < Y:            #贪心
            if Y % 2 == 1:
                Y += 1
            else:
                Y //= 2
            res += 1
        return res + (X - Y)    #其余的差距，只能一个一个来

```

### 不同整数的最少数目
<img width="424" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/9d289a74-241b-4c73-86a3-2792b9b1897f">

### 灌溉花园的最少水龙头数目
将水龙头的覆盖区域看做为一个小区间，本题即转换为求选择最少的区间数目可以覆盖连续区间  
<img width="427" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/3e26244c-ceeb-420e-832e-3724948460ab">

### 视频拼接

<img width="418" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/32212849-6eb0-4816-bb1e-ebdf58815bd6">

