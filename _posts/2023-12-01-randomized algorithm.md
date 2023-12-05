---
layout: post
title: " randomized algorithm"
date:   2023-12-01
tags: [network]
comments: true
author: zhang
---
Efficient deterministic algorithms that always yield the correct answer are a special case of efficient randomized algorithms that oly need to yield the correct answer with high probability.  

## Global Minimun Cut
there is a polynomial time algorithm to find a global min-cut in an undirected graph G

### contraction algorithm(Karger)
In the following figure, contracting the edges in the specified order, will find the min-cut. Note that in this
case, we were lucky and did not contract the edges that were in the min-cut  
<img width="653" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/eac9451f-ad74-46cb-89e5-9540453ef666">   

The contraction algorithm returns a min cut with prob >=2/$n^2$  
IF we repeat the contraction algorithm $n^2$ln$n$ times,then the probability of failing to find the global min-cut is <1/$n^2$




