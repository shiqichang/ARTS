# ARTS(week02)

## 算法题(Algorithm)

- 题目：[两数相加](https://leetcode-cn.com/problems/add-two-numbers/)
- 解答：[add_two_numbers](https://github.com/SharonChiong/leetcode/blob/master/algorithms/python/add_two_numbers/add_two_numbers.py)


## 阅读点评(Review)

#### [Technical Concepts](http://kylin.apache.org/docs23/gettingstarted/concepts.html)

今天看的是`Apache Kylin`的官方文档，想深入知道有关`Kyin`的概念。在这篇文档中，我学会了很多`术语(Terminology)`, 主要讨论`Cube`, 因为我最近也在研究`Cube设计及构建`

- `CUBE`: 多维数组集
    1. `Table`: `Hive tables` 是`cubes`的数据源，在构建 cube 之前需要先同步`Hive tables`;
    2. `Data Model`: `STAR SCHEME(星型架构)`的数据模型，在这里定义了`fact table(事实表)`, `lookup table(查找表)`;
    3. `Cube Descriptor`: 定义了`cube实例`的设置、数据模型的使用、需要哪些`dimensions(维度)`和`measures(度量)`;
    4. 还有`Cube Instance(实例)`, `Partition(分区)`, `Cube Segment`, 就不一一介绍了。


## 技术技巧(Tip)

#### 最近在看`HBase`的书，也是和工作相关吧，主要是`HBase`的命令行使用。

- 创建表

        create 'student','id','info'

- 插入表数据

        put 'student','1001','info:name','Lucy'
        put 'student','1001','info:age','18'
        
- 查看表

        scan 'student'
        
`HBase`的查询和我们常见的`SQL`查询不一样，所以为了方便，工程师们推出了`Hive`, 对表的操作类似于`SQL`操作。

 
## 分享(Share)

#### [一个历时五天的 Bug](https://mp.weixin.qq.com/s?__biz=Mzg4NjAwMTQzNA==&mid=2247484143&idx=1&sn=567c20d103827dbf13c0d2aa3506a8cd&chksm=cfa1189af8d6918c9db4d3e03f864b0e8fd46ab63864e0e15047ca22e8a932b4504680341612&mpshare=1&scene=1&srcid=&pass_ticket=lItOKyDIrtagtC2l4Tc4WduOnMHEYVRjxsvZU7TtCs13w4Mv6gpMHzu%2FmDOBIfcZ#rd)

分享的是公众号`大飞码字`的文章。

- 我之前看过一句话，所出一位IT界的大牛，`If debugging is the process of removing software bugs, the proggramming must be the process of putting them in.`，深有体会；
- 只要是搞开发，那么几乎每天都避免不了和`Bug`打交道，有些容易复现的多打几个日志，就找出问题所在了；有些很难复现的就需要另寻他法，我觉得，在期间最重要的是调整心态，不要急躁。