# ARTS(week06)

## 算法题(Algorithm)

- 题目：[Z 字形变换](https://leetcode-cn.com/problems/zigzag-conversion/)
- 解答：[zigzag_conversion](https://github.com/SharonChiong/leetcode/blob/master/algorithms/python/zigzag_conversion/zigzag_conversion.py)


## 阅读点评(Review)

#### [Data science with Python: Turn your conditional loops to Numpy vectors](https://towardsdatascience.com/data-science-with-python-turn-your-conditional-loops-to-numpy-vectors-9484ff9c622e)

作者一开始提出了 `Vectorization trick(失量化技巧)` 的概念，对于数据分析家来说是很常见的技巧，常用于编程。

在编码中，数据转换其实是对可迭代对象进行数值转换。

`Numpy` 是 Python 里高性能科学计算和数据分析的基础包。我们用的 `Pandas` 也是建立在它基础上的包，可以说它几乎是所有高级工具的基础包。

作者还利用代码来展示了对条件循环进行失量化的性能测试，分别测试了 `列表推导式`，`Map()函数`，`Numpy.vectorize方法`，结果显示 `Numpy.vectorize方法` 耗时最少，性能最高。

这也说明了，对于数据分析家来说，使用 `Numpy` 的失量化方法比传统的 Python 方法可以节约更多的时间成本，是非常值得推荐使用的工具。


## 技术技巧(Tip)

#### 使用 sqlalchemy 连接 mysql 遇到的坑

最近在 mysql 数据库中查询并统计某字段，使用了 `ORM 框架 sqlalchemy` 连接 `mysql`的时候，碰到了一个很奇葩的问题，报错信息如下：

```log
sqlalchemy.exc.OperationalError: (pymysql.err.OperationalError) (2013, 'Lost connection to MySQL server during query')
```

经过上网一番搜索，说是 `mysql` 的配置问题（很坑的回答。。），因为我用 `pymysql` 连接是没有报错的，能正常查询。显然是 `sqlalchemy` 的方法的处理方式问题了。

经过一番检查，发现有个很可疑的地方，数据库的配置信息里有特殊符号，是不是编码问题？

果然，使用 `quote_plus()方法` 对配置信息进行 `URL编码` 后，就能连接了，示例代码如下。

```python
from urllib import parse

text_before = '&%12'
text_after = parse.quote_plus(text_before)
```


## 分享(Share)

#### [关于同源策略](https://zz.zzs7.top/same-origin-policy.html)

同源策略是一种著名的安全策略，也是浏览器最核心、最基本的安全功能。

如果两个页面的协议、端口、主机都相同，那么这两个页面具有相同的源。

此外，作者详细讲述了跨域和如何跨域的方法。

同源策略是浏览器的行为，主要是保护本地数据不被 `Javascript` 代码获取到的数据污染。
