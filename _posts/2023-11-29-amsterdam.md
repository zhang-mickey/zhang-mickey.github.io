---
layout: post
title: "Performance models of network"
date:   2023-11-29
tags: [network]
comments: true
author: zhang
---



<!-- more -->
[TOC]
## GSM  --(Erlang-B model)


## HSCSD --(multi-rate.knapsack model)

## GPRS --(combined blocking/PS model)

## WLAN 802.11 --(Bianchi model)
The general step:  
A station with a new packet to transmit monitors the channel activity. If the channel is idle for a period of time equal to a distributed interframe space(DIFS),the station transmits.  
At this point, the station generates a `random` backoff interval before transmitting. At each packet transmission,the backoff time is uniformly chosen in the range $(0,w-1)$. The value $w$ is called **contention 
windows**.   
The ACk is immediately transmitted at the end of the packet,after a period of time called short interframe space(SIFS). As the SIFS(plus the propagation delay) is shorter than a DIFS, no other station is able to detect the channel idle for a DIFS until the end of the ACK. 
- contention windows
At the first attempt,$w$ is set equal to value $CW_min$. After each unsuccessful transmission, $ w $ is doubled,up to a maximum value$ CW_{max}=x^m{CW}_min $

### distributed coordination function (DCF)
the fundamental mechanism to access the medium is called distributed coordination function. This is a random access scheme,based on the carrier sense multiple access with collided avoidance(CSMA/CA).

DCF describes two techniques to employ for packet transmission.  

- two-way handshaking

- RTS/CTS
Before transmitting a packet, a station operating in RTS/CTS mode`reserves` the channel by sending a special Request-To-Sent short frame. The destination station acknowledges the receipt of an RTS frame by sending back a Clear-To-Send frame,after which normal packet transmission and ACK response ouucrs.
Since collision may occur only on the RTS frame, and it is detected by the lack of CTS response
`benefit`:Increase the system performance by reducing the duration of a collision when long messages are transmitted. 

 


