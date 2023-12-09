---
layout: post
title: " NP-reduction"
date:   2020-08-23
tags: [algorithm]
comments: true
author: zhang
---

reduction (a technique usually used to show some problem is NP-hard).   
it's useful to know a good number of different NP-complete problems:When you encounter a new problem X and want to try proving it's NP-complete,you want to show Y<=(p)X for some known NP-complete problem Y.  
##### NP-hard
problem P is NP-hard if it can be reduced from all NP problems.   
- Dominating Set: reduction form **Vertex Cover**
Subset sum problem  
Maximum 3-SAT  
- k-center problem: reduction from **dominating set** or **vertex cover**  
Maximum Coverage problem  
##### NP-complete 

#### decision problem
if the output is yes or no
#### optimization problem
if the output is maximum or minimum of the problem instance.  
### P
A problem Q is in
P if given a decision instance (e.g. bound B in K-center problem), we can answer whether there
exists a solution satisfying this instance (e.g. some solution with objective value ≤ B in K-center
problem) in polynomial time of the input size. 
#### NP
if given a decision instance and a solution, we can check whether this solution
satisfies the instance in polynomial time of input size.

### APX
A problem is APX-hard if every problem in APX can be PTAS reduced to it.  
## 
at least as hard as the hardest problems in NP  
a problem H is NP-hard when every problem L in NP can be reduced in polynomial time to H  
### dominating set
Given an undirected graph G = (V, E) and
bound K, we want to decide whether there exists a subset S of V of size K such that every vertex
v ∈ V is either in S or a neighbor of some s ∈ S.  
<img width="549" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/71421ca5-6026-44fe-b040-ef65da5f193e">
#### reduction 

### k-center problem
The k-center problem aims to place at most k-centers that service
all clients, trying to minimize the service cost, which is the maximum over all
clients of the minimum work required for the client to be serviced by one of the
centers (this is usually just the minimum distance from a client to one of the
centers.)
#### approximate
this problem cannot be solved within a ρ <=2 approximation factor, unless P = NP .   
use **dominating set**  
### Maximum coverage problem  
<img width="641" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/200b02a3-d0aa-474e-ab23-cf16bcf99c25">  

#### greedy algorithm approximation ratio 1 − 1/e.

