# ARTS(week07)

## 算法题(Algorithm)

- 题目：[整数反转](https://leetcode-cn.com/problems/reverse-integer/)
- 解答：[reverse_integer](https://github.com/SharonChiong/leetcode/blob/master/algorithms/python/reverse_integer/reverse_integer.py)


## 阅读点评(Review)

#### [What does Stack Overflow want to be when it grows up?](https://blog.codinghorror.com/)

博主是 `Stack Overflow` 的创始人之一 `Jeff Atwood`, 这篇博客主要讲述了博主对 Stack Overflow 的看法。

以下是博主的见解。

1. 首先，Stack Overflow 是一个 `wiki`，比起说是论坛，更像是维基百科；

    - Stack Overflow 上的问题和回答主要不是对特定个人的有用性判断，而是随着时间的推移给其他很多提问或回答的程序员提供帮助。

2. 其次，随着时间的推移，重复成了一个巨大的地雷；

    - Stack Overflow 不能对完全相同的编程问题允许重复的问题。就好比维基百科，你不可以在维基百科上发表关于 `Italy` 的不同的 5 篇文章。
    
    - 一般在 Stack Overflow 上发表问题之前，会提示建议说搜索看是否已有类似的问题。
    
3. Stack Overflow 是一个同行评审的竞争系统；

    - 激励一个程序员最好的办法就是巧妙地暗示另一个程序员可以做得更好。**"There's always more than one way to do it."**
    
4. Stack Overflow 是专为练习程序员而设计。

    - 主要是专业和发烧友程序员的问答。
    
博主发这篇博客主要是庆祝 Stack Overflow 十周年庆，以及讲述了自己对 Stack Overflow 的见解和 Stack Overflow 以后要成为的样子。


## 技术技巧(Tip)

#### linux grep 用法之 `wc -l`

最近查看日志的时候，需要检查自己写的多线程和多进程任务是否都执行成功，

比如搜索关键字 `future`,

```bash
# grep 查询
$ cat info.log | grep future
```

但是过滤出的内容非常得多，根本没法查看和计算任务是否都执行成功了，

这个时候 `wc -l` 就非常有用了，它是用来统计过滤出的日志数量的，如下

```bash
# wc -l 统计
$ cat info.log | grep future | wc -l
```


## 分享(Share)

#### [Python 字符编码](https://s7.zzs7.top/character-encoding.html)

分享我自己写的一篇博客，关于 `Python 字符编码`，主要包括字符串在 Python 2 和 Python 3 中的不同、Unicode 和 UTF-8 的简单介绍、Python 中的字符编码与解码。

欢迎围观，批评指正！
