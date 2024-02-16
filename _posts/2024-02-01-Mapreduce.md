---
layout: post
title: " JAVA"
date:   2024-02-01
tags: [BIG DATA]
comments: true
author: zhang
---
## hadoop 实现 Join 的几种方法

### reduce side join 是一种最简单的 join 方式

其主要思想如下： 在 map 阶段，map 函数同时读取两个文件 File1 和 File2，为了区分两种来源的 key/value 数 据对，对每条数据打一个标签（tag）,比如：tag=0 表示来自文件 File1，tag=2 表示来自文件 File2。即：map 阶段的主要任务是对不同文件中的数据打标签。 在 reduce 阶段，reduce 函数获取 key 相同的来自 File1 和 File2 文件的 value list， 然后对于 同一个 key，对 File1 和 File2 中的数据进行 join（笛卡尔乘积）。即：reduce 阶段进行实际的 连接操作。
2) map side join

之所以存在 reduce side join，是因为在 map 阶段不能获取所有需要的 join 字段，即：同一个 key 对应的字段可能位于不同 map 中。Reduce side join 是非常低效的，因为 shuffle 阶段要进 行大量的数据传输。
3) SemiJoin SemiJoin

也叫半连接，是从分布式数据库中借鉴过来的方法。它的产生动机是：对于 reduce side join，跨机器的数据传输量非常大，这成了 join 操作的一个瓶颈，如果能够在 map 端过 滤掉不会参加 join 操作的数据，则可以大大节省网络 IO。


(1)map task 会从本地文件系统读取数据，转换成 key-value 形式的键值对集合。使用的是 hadoop 内置的数据类型，比如 longwritable、text 等。
(2)将键值对集合输入 mapper 进行业务处理过程，将其转换成需要的 key-value 在输出之后 会进行一个 partition 分区操作，默认使用的是 hashpartitioner，可以通过重写 hashpartitioner 的 getpartition 方法来自定义分区规则。
(3)会对 key 进行进行 sort 排序，grouping 分组操作将相同 key 的 value 合并分组输出，在这 里可以使用自定义的数据类型，重写 WritableComparator 的 Comparator 方法来自定义排序 规则，重写 RawComparator 的 compara 方法来自定义分组规则

每个 map task 都有一个内存缓冲区，
存 储着 map 的输出结果 当缓冲区快满的时候需要将缓冲区的数据以一个临时文件的方式存放到磁盘，当整个 map task 结束后再对磁盘中这个 map task 产生的所有临时文件做合并，生成最终的正式输 出文件，然后等待 reduce task 来拉数据。
