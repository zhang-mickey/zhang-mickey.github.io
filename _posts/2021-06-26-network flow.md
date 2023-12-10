---
layout: post
title: "network flow"
date:   2021-06-26
tags: [Algorithm]
comments: true
author: zhang
---

## Maximal Flow Problem

### max-flow min-cut theorem
the maximum amount of flow passing from the source to the sink is equal to the total weight of the edges in a minimum cut  
This is a special case of the duality theorem for linear programs   

### Ford-Fulkerson 
 Main idea: find valid flow paths until there is none left, and
add them up  
#### Flow Decomposition  
Any valid flow can be decomposed into flow paths and circulations  
#### correctness
<img width="499" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/c30cf010-6568-45fa-8aab-c579b4fc0d76">   

#### Analysis
Assumption: capacities are integer-valued.  
<img width="615" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/fc3f9dd7-e63e-4837-a309-0c95ae8539c1">  
#### how do we find the min-cut?(use residual graph)
<img width="622" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/9d2c2500-c498-4b0b-85ad-864af18b8e34">  
<img width="575" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/58c8a7b9-dc50-47c5-862f-b549965ba819">

## bipartite matching 
<img width="500" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/a6fe0160-9351-47be-aba7-dd1270a354bb">  
<img width="399" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/be1215fb-b0dc-4097-a065-4c021e4ce2ef">  

### example 
<img width="607" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/5a2424ef-8e6e-4f0f-ad4f-4c90e9af801b">
<img width="588" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/7752fdb4-a852-4dac-980d-b4123f4e066e">
<img width="638" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/65cd4fe4-0ac5-4c0b-b7fd-bdd241603775">
<img width="589" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/0ecb3d1a-6d6d-407a-8489-c1cda9078435">


### bipartite matching is in P
There are a variety of polynomial-time algorithms for finding an optimal bipartite matching.   
**A common algorithm is one that reduces the matching problem into an equivalent max-flow instance**  

#### For any bipartitie graph, the maximum size of a matching is equal to the minimum size of a vertex cover.(konig)  
duality

### dominating set
a dominating set for a graph G is a subset D of its vertices, such that any vertex of G is either in D, or has a neighbor in D.   
<img width="108" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/d78b23d8-460b-40b6-8aa9-fd3ed5a0320f">

#### 2-SAT
can be solved in polynomial time   

<img width="385" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/c75ee471-6d73-4a98-921a-e647975a149e">  



 https://web.stanford.edu/class/cs97si/  
 
