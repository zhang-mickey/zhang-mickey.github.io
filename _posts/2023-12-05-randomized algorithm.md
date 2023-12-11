---
layout: post
title: " randomized algorithm"
date:   2023-12-05
tags: [algorithm]
comments: true
author: zhang
---
two types: 
- Las Vegas: Time complexity is probabilistic, correctness is deterministic
example: randomized Quicksort  
- Monte Carlo:Time complexity is deterministic, correctness is probabilistic
  
<img width="419" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/10afb216-d775-4440-bc6d-1decb6fa7a1f">
  
<img width="269" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/e823687d-877e-4a5c-ac16-333b413a6796">

Efficient deterministic algorithms that always yield the correct answer are a special case of efficient randomized algorithms that oly need to yield the correct answer with high probability.   
证明存在某种情况或性质  
<img width="443" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/4da99b76-0aee-4cdc-8ac3-bd2552a8bdbc">

#### 
<img width="436" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/a5c8d882-656a-45eb-9edc-88245b9bdd2e">

#### probabilistic method
use the fact that a random algorithm produces them with probability p>0 to prove the existence of certain solutions.  
## expected approximation ratio


## weighted Max Sat
## 4/3-approximative LP-based algorithm

## Global Minimun Cut
there is a polynomial time algorithm to find a global min-cut in an undirected graph G

### contraction algorithm(Karger)(Monte Carlo)
In the following figure, contracting the edges in the specified order, will find the min-cut. Note that in this
case, we were lucky and did not contract the edges that were in the min-cut  
<img width="653" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/eac9451f-ad74-46cb-89e5-9540453ef666">   
this may not always give the minimum cut  if the algorithm picks an edge from the actual minimum 
cut  
The contraction algorithm returns a min cut with prob >=2/$n^2$  
IF we repeat the contraction algorithm $n^2$ln$n$ times,then the probability of failing to find the global min-cut is <1/$n^2$

### max 3-SAT

Given a 3-SAT formula with k clauses, the expected number of clauses satisfied by a random assignment is 7k/8    
<img width="417" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/1258f39e-2bd6-4cc2-b496-0815713f3a00">


### max-cut
<img width="433" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/b60a813f-862f-4cad-9f99-ca06e496eeaa">

### quick sort

![image](https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/aa5652a0-8e05-49d1-b677-540f83839cb7)  

we can only guarantee to have the pivot in its correct location because we don’t sort the other elements. Instead, we move them to the left or right of the pivot. Finally, we perform two recursive calls. The first call sorts the elements before the pivot, while the other sorts the ones after.
#### Best-Case Scenario
![image](https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/f703f509-2e89-454e-99b8-ab52e6a8bf9f)  
if we keep dividing the array in half, we’ll end up with the minimum number of recursion levels, which is {O(log(n))}   
Since in each level, we perform O(n) comparisons to put the pivot in its correct location, then the overall complexity in the best-case scenario is O(nlog(n)).  
#### Worst-Case Scenario
![image](https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/9fcaaa56-d03a-440f-93e5-e054b3d145b9)   
the overall time complexity will be{O(n^2)}.

#### randomized QuickSort
O(nlog(n))<=complexity<=O(n^2)} This difference depends on the chosen pivot elements  
<img width="341" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/39ea4fc4-fedb-4666-8341-25c285725f58">  
#### prove that the expected running time is O(nlogn)
<img width="422" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/6505264a-e804-4c20-9c7a-b1bdcbad96a7">
<img width="413" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/34536c97-fdb8-4326-b9a4-fd2dbd5280d7">
<img width="428" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/9a5cd6dc-a239-4eba-bbfe-3ef7764541f0">

### universal hashing  

## derandomization
<img width="463" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/c3917f59-7e57-4583-846f-4f623aaeeb71">
