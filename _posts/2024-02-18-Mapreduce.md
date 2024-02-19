---
layout: post
title: "Mapreduce"
date:   2024-02-18
tags: [BIG DATA]
comments: true
author: zhang
---


## mapper
In a MapReduce program, the output key-value pairs from the Mapper are automatically sorted by keys


### Comparator
Users can control the grouping by specifying a Comparator 
### partitioner
A partitioner function will determine where the pairs of a key are sent.


## reduce
The reduce tasks will receive the output of the mapper tasks, which are already sorted
lists. 

## hadoop 实现 Join 的几种方法

What is a Join?
The join operation is used to combine two or more database tables based on foreign keys. In general, companies maintain separate tables for the customer and the transaction records in their database. And, many times these companies need to generate analytic reports using the data present in such separate tables. Therefore, they perform a join operation on these separate tables using a common column (foreign key), like customer id, etc., to generate a combined table. Then, they analyze this combined table to get the desired analytic reports.
流程图如下
![image](https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/7f66dca5-9966-4b7c-9c9b-9b26eae13b92)

### reduce side join 是一种最简单的 join 方式
![image](https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/e26302f2-c0d7-42ad-b5ca-585bb607dcfc)
连接效率比较低，因为所有数据都必须经过shuffle过程
the reducer is responsible for performing the join operation. It is comparatively simple and easier to implement than the map side join as the sorting and shuffling phase sends the values having identical keys to the same reducer and therefore, by default, the data is organized for us.

Basically, the reduce side join takes place in the following manner:

Mapper reads the input data which are to be combined based on common column or join key.
The mapper processes the input and adds a tag to the input to distinguish the input belonging from different sources or data sets or databases.
The mapper outputs the intermediate key-value pair where the key is nothing but the join key.
After the sorting and shuffling phase, a key and the list of values is generated for the reducer. 
Now, the reducer joins the values present in the list with the key to give the final aggregated output.


![image](https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/44a26303-1250-4dd3-93b7-fc58e5f68301)
**authorID** **authorname**

![image](https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/4d768783-1447-41c9-9170-3c3afe90f12d)

**authorID** **year**   **bookname**  

![image](https://github.com/zhang-mickey/zhang-mickey.github.io/assets/145342600/9f2f0a43-2fc1-455f-9bad-dcd56f6b1dfe)

 
其主要思想如下： 在 map 阶段，map 函数同时读取两个文件 File1 和 File2，为了区分两种来源的 key/value 数 据对，对每条数据打一个标签（tag）,比如：tag=0 表示来自文件 File1，tag=2 表示来自文件 File2。即：map 阶段的主要任务是对不同文件中的数据打标签。 在 reduce 阶段，reduce 函数获取 key 相同的来自 File1 和 File2 文件的 value list， 然后对于 同一个 key，对 File1 和 File2 中的数据进行 join（笛卡尔乘积）。即：reduce 阶段进行实际的 连接操作。
### map side join
在mapper端执行join
之所以存在 reduce side join，是因为在 map 阶段不能获取所有需要的 join 字段，即：同一个 key 对应的字段可能位于不同 map 中。Reduce side join 是非常低效的，因为 shuffle 阶段要进 行大量的数据传输。
3) SemiJoin SemiJoin

也叫半连接，是从分布式数据库中借鉴过来的方法。它的产生动机是：对于 reduce side join，跨机器的数据传输量非常大，这成了 join 操作的一个瓶颈，如果能够在 map 端过 滤掉不会参加 join 操作的数据，则可以大大节省网络 IO。


(1)map task 会从本地文件系统读取数据，转换成 key-value 形式的键值对集合。使用的是 hadoop 内置的数据类型，比如 longwritable、text 等。
(2)将键值对集合输入 mapper 进行业务处理过程，将其转换成需要的 key-value 在输出之后 会进行一个 partition 分区操作，默认使用的是 hashpartitioner，可以通过重写 hashpartitioner 的 getpartition 方法来自定义分区规则。
(3)会对 key 进行进行 sort 排序，grouping 分组操作将相同 key 的 value 合并分组输出，在这 里可以使用自定义的数据类型，重写 WritableComparator 的 Comparator 方法来自定义排序 规则，重写 RawComparator 的 compara 方法来自定义分组规则

每个 map task 都有一个内存缓冲区，
存 储着 map 的输出结果 当缓冲区快满的时候需要将缓冲区的数据以一个临时文件的方式存放到磁盘，当整个 map task 结束后再对磁盘中这个 map task 产生的所有临时文件做合并，生成最终的正式输 出文件，然后等待 reduce task 来拉数据。


#### 
adoop Sequence File is a flat file structure which consists of serialized key-value pairs. 
