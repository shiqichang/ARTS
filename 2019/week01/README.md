# ARTS(week01)

## 算法题(Algorithm)

- 题目：[两数之和](https://leetcode-cn.com/problems/two-sum/)
- 解答：[two_num](https://github.com/SharonChiong/leetcode/blob/master/algorithms/python/two_sum/two_sum.py)

## 阅读点评(Review)

#### [Investing In Big Data: Apache HBase](https://engineering.salesforce.com/investing-in-big-data-apache-hbase-b9d98661a66b)

为了更加了解关于 HBase 的知识，我在 Medium 上看了一篇文章，略有些感悟。
1. 介绍了什么是 HBase: HBase 是一种开源的分布式数据库，特点包含分布式、持续性、查询快、占用资源少、多维的；
2. 解释了为什么要使用一个 NoSQL 存储，以及在所有的 NoSQL 存储中，选择 HBase 的原因。

## 技术技巧(Tip)

最近搭建了一个 HBase 集群的环境，当时启动 HBase 时，发现 HMaster 启动之后又自动断开了，找了很久的原因，后来想想是不是磁盘空间快满了，然后上网查了如何看服务器的磁盘使用情况。

    df -hl
    
其中，df 列出了文件系统的整体磁盘使用量。

## 分享(Share)

[“努力就会成功”](https://coolshell.cn/articles/19271.html)

最近的 996 话题很火，我觉得加班和 996 要是能给自己带来成就感和幸福感，那也挺好的。如果是拼命地加班干活，输出的更多的是体力，效率愈来愈低。参加 ARTS 挑战，也是我想通过提升自身技能，花更少的时间，解决更多的问题。
