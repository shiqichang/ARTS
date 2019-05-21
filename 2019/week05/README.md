# ARTS(week05)

## 算法题(Algorithm)

- 题目：[最长回文子串](https://leetcode-cn.com/problems/longest-palindromic-substring/)
- 解答：[longest_palindromic_substring](https://github.com/SharonChiong/leetcode/blob/master/algorithms/python/longest_palindromic_substring/longest_palindromic_substring.py)

## 阅读点评(Review)

#### [Quickstart tutorial](https://www.numpy.org/devdocs/user/quickstart.html)

最近忙于做数据统计的项目，英文文档看的比较多的也是 `Numpy` 和 `Pandas`，这里主要介绍 `Numpy` 的快速入门。

当然，Prerequisites(先决条件)是，需要懂 `Python` 的使用。

`Numpy` 的主要对象是 `ndarray(多维数组)`，它的属性包括 `ndim(维数)`、`shape(多维数组有几行几列)`、`size(元素的个数)`、`dtype(元素的类型)`等等。

对 `ndarray` 的操作可以是索引、切片、迭代、数值运算、花式索引。

这里简单地介绍 `ndarray` 的 `花式索引(Fancy indexing)`：

```python
>>> import numpy as np
>>> a = np.arange(12)**2
>>> i = np.array([1, 1, 3, 8, 5])
>>> a[i]
array([ 1,  1,  9, 64, 25])
>>> j = np.array([[3, 4], [9, 7]])
>>> a[j]
array([[ 9, 16],
       [81, 49]])
```

`Numpy` 是 `Python` 数值计算的基础包，提供了基于数组的算术操作，还有矩阵运算。


## 技术技巧(Tip)

### nohup 的日志

`nohup` 如果没有指定日志，默认是在当前目录下创建一个 `nohup.out` 文件，然后将日志写入该文件中，有的时候，我们不需要有 nohup 的输出信息，会由一个日志模块管理。那么我们可以将日志写入 `/dev/null`

```bash
#!/bin/bash
# 进入虚拟环境
source '/usr/bin/virtualenvwrapper.sh'
workon demo

# 日志写入 `/dev/null`
nohup python -u test.py > /dev/null 2>&1 &
```

写入 `/dev/null` 的内容被自动被清理，不占用磁盘空间


## 分享(Share)

[如何在Archlinux系统中安装MongoDB](https://zz.zzs7.top/archlinux-install-mongodb.html#more)

我用的系统是 `Manjaro`, 因为 `MongoDB` 修改了软件授权协议，所以在 `Archilinux` 的官方源中已经删除了 `MongoDB`，在 `Archlinux` 的 官方 `wiki` 中建议安装 `AUR` 中的 `mongodb-bin`，或者编译安装，考虑到电脑的性能，就不采取编译安装的方式了。

知道了要下载 `mongodb-bin` 包，那么就简单了。

根据文章的安装步骤，成功安装并启动。

`Manjaro` 的源一般是很全很多的，而且支持滚动更新，用起来比较舒服，像 `MongoDB` 这种不支持 `pacman` 安装的比较少，这里也分享一下。
