---
layout: post
title: " queue theory "
date:   2023-12-07
tags: [queue theory]
comments: true
author: zhang
---

##### Little's Law
Regardless of the distribution of arriving items and how the system chooses to process them, it always holds that L = λW if there exists a steady state!
<img width="766" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/42acd19e-b152-43fb-a70d-c9e40412a6ad">
<img width="260" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/439aea76-9fec-4b43-b5ac-9e52d15d94eb">
####### example 
<img width="702" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/89429dd4-216d-4033-bc0a-7d878ecb9a7f">

为什么发明指数分布  
### exponential distribution
<img width="458" alt="image" src="https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/bd29ca4b-c634-4001-8c8c-65f842956768">  

#### minimum property
if X,Y independent exponential with parameters r1 and r2, then min{X,Y} exponential with parameter r1+r2.  

### poisson process

#### Superposition property

#### Thinning-out property  

### discrete-time Bernoulli process

### continuous-time Poisson process
the inter-arrival times are independent and exponentially distributed with mean 1/r.

### Processor sharing
Flow-level behavior of TCP data transfers is often be modeled by PS model  
**key performance metric**  
mean sojourn time
### Jackson Network
In queueing networks,the output of one queue may be the input of another.  
In stready-state,the output process if M/M/1,M/M/k queue follows a Poisson process, because no traffic is lost in such queues,the arrival rate must be equal to the departure rate.   
