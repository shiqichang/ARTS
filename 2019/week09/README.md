## ARTS(week09)

## 算法题(Algorithm)

- 题目：[回文数](https://leetcode-cn.com/problems/palindrome-number/)
- 解答：[palindrome_number](https://github.com/SharonChiong/leetcode/blob/master/algorithms/python/palindrome_number/palindrome_number.py)


## 阅读点评(Review)

#### [Installation](https://docs.mongodb.com/charts/onprem/installation/?_ga=2.205610139.923838046.1560741006-1769519089.1559815196)

在使用数据分析可视化工具 `Superset` 的时候，遇到了一个瓶颈。`Superset` 只支持 `sql` 查询，所以只能连接关系型数据库，
如 `PostgreSQL`, `MySQL`, `Oracle`, `Microsoft SQL Server`, `SQLite`, etc.

因为在技术选型上，我们选择了 `MongoDB`, 一种非关系型数据库，所以无法通过 `Superset` 连接 `MongoDB`.

通过调研，看到一款 `MongoDB` 可视化工具，`MongoDB Charts`. 目前处于测试阶段，可以先了解。

##### System Requirements(系统要求)

- Metadata database(元数据库)

  - 需要运行 3.4 或更高版本的 `MongoDB` 部署来存储 `Charts` 元数据；

  - 图表元数据数据库可以是在 `MongoDB Atlas` 上运行的集群，`MongoDB Atlas` 是用于运行、监视和维护 `MongoDB` 部署的云托管服务。

- Charts Server(图表数据库)

  - `MongoDB Charts` 必须安装在运行 Docker CE 或 EE(v17.06 或更高版本) 的单个服务器上。

- Supported Browsers(支持的浏览器)

  - Chrome, Firefox, Safari.
  
##### Install `MongoDB Charts`(安装 `MongoDB Charts`)

1. 新建一个目录，存储 `Charts` 配置文件；

    ```bash
    # 新建目录并进入该目录
    $ mkdir mongodb-charts
    $ cd mongodb-charts 
    ```

2. 下载 `MongoDB Charts Docker Compose` 文件；

3. 启动 `Docker Swarm mode`;

    ```bash
    # 启动 Docker Swarm 模式
    $ docker swarm init
    ```
    
4. 拉取 `Charts` 镜像

    ```bash
    # 拉取 `Charts` 镜像
    $ docker pull quay.io/mongodb/charts:19.06
    ```
    
5. 测试与 `Charts 元数据库` 的连接

    ```bash
    # 测试
    $ docker run --rm quay.io/mongodb/charts:19.06 charts-cli test-connection mongodb://<username>:<password>@myhost/
    ```
    
6. 创建 `Charts 元数据库` 的密钥

    ```bash
    # 生成密钥
    $ echo "<Verified connection string URI from step 5>" | docker secret creat charts-mongodb-uri -
    ```
    
7. 运行 `Charts` 容器

    ```bash
    # 运行容器
    $ docker stack deploy -c charts-docker-swarm-19.06.yml mongodb-charts
    # 验证是否启动
    $ docker service ls
    ```
   

## 技术技巧(Tip)

#### MongoDB explain

当 MongoDB 中存储的数据量特别大的时候，优化查询速度是提供系统性能的重点。
MongoDB 提供了一个非常方便的诊断工具 - `explain()`.

通过查看 `explain()` 的输出文档，我们可以知道使用的查询语句使用了什么索引，以及如何使用的。
最常见的输出有两种类型：使用索引的查询和没有使用索引的查询。

- cursor.explain(verbosity): 提供 query plan(查询计划)

    ```shell
    > db.collection.find().explain()
    > db.collection.find().explain('executionStats')
    ```

    其中，参数 `verbose` 有三种模式：`queryPlanner`, `executionStats`, `allPlansExectuion`, 
    可以理解为概要模式，执行状态模式，所有信息模式。
    
    默认模式是 `queryPlanner`.
    一般我们需要查看详细的信息，会选择第二种模式 `executionStats`.


## 分享(Share)

#### [Python 日期和时间的基本使用(一)](https://s7.zzs7.top/python-date.html)

#### [Python 日期和时间的基本使用(二)](https://s7.zzs7.top/python-date-2.html)

这次分享的是自己写的两篇关于 Python 日期和时间的博客。

- 上篇主要介绍的是通过官方文档，讲述 `date`, `time`, `datetime`, `timedelta` 的基本使用；

- 下篇主要介绍 Python datetime 模块的常见使用和关系转换，
以及第三方库 `python-dateutil` 的学习，主要包括 `parse`, `rrule`, `relativedelta`.
