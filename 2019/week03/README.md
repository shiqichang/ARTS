# ARTS(week03)

## 算法题(Algorithm)

- 题目：[无重复字符的最长子串](https://leetcode-cn.com/problems/longest-substring-without-repeating-characters/)
- 解答：[longest_substring_without_repeating_characters](https://github.com/SharonChiong/leetcode/blob/master/algorithms/python/longest_substring_without_repeating_characters/longest_substring_without_repeating_characters.py)

## 阅读点评(Review)

#### [The Simple Yet Practical Data Cleaning Codes](https://towardsdatascience.com/the-simple-yet-practical-data-cleaning-codes-ad27c4ce0a38)

这一篇是我逛论坛时找到的文章，讲的是数据清洗。

    The world is imperfect, so is data.
    
真正的数据不是完整，精确的，里面会有“脏数据”，比如测试数据，缺失值，价值含量不高的数据，所以我们对数据进行分析统计之前，需要对数据进行清洗。

作者在文中分享了几种数据清洗的方法，总结如下，具体代码可见原文：

1. 删除多列的数据，只专注于自己需要的列数据；
2. 改变 `dtypes`, 对于很大的数据集，可以通过转换 `dtypes` 来节省内存；
3. 将分类变量转换成数值变量，有些机器学习模型需要数值形式的变量，但为了便于分析和理解，可以保留分类变量；
4. 检查缺失的数据；
5. 删除列中的字符串；
6. 删除列中的空格；
7. 特定情况下，可以拼接两列字符串；
8. 将字符串类型转换成时间格式。

## 技术技巧(Tip)

最近接触了 `m3u8`, 这是什么呢？

m3u8 是一种可扩展的播放列表文件格式，存放真正的视频链接，它是一种视频列表;

我发现网上的在线视频，是一节一节加载的，之前以为是一个完整的视频加载，不了解具体的流程，看了 `m3u8` 的资料，才知道，其实就是 m38u 记录的多个子视频文件。

自己尝试在本地切割生成了一个 `m3u8` 这样的视频文件

- 以下是文件内容

```bash
#EXTM3U
#EXT-X-VERSION:3
#EXT-X-TARGETDURATION:29
#EXT-X-MEDIA-SEQUENCE:0
#EXT-X-KEY:METHOD=AES-128,URI="http://127.0.0.1:8000/get_key/b5fa03d673a15ebb363bcef2e9dd048b.key",IV=0x3225786da555f2e0fd9be9effaadf813
#EXTINF:20,
000.ts
#EXTINF:20,
001.ts
#EXTINF:29,
002.ts
#EXTINF:12,
003.ts
#EXTINF:22,
004.ts
#EXTINF:17,
005.ts
#EXTINF:20,
006.ts
#EXTINF:26,
007.ts
#EXTINF:15,
008.ts
#EXTINF:20,
009.ts
#EXTINF:20,
010.ts
#EXTINF:20,
011.ts
#EXTINF:1,
012.ts
#EXT-X-ENDLIST
```

- 目录结构如下

```bash
$ tree
.
├── 000.ts
├── 001.ts
├── 002.ts
├── 003.ts
├── 004.ts
├── 005.ts
├── 006.ts
├── 007.ts
├── 008.ts
├── 009.ts
├── 010.ts
├── 011.ts
├── 012.ts
└── index.m3u8

0 directories, 14 files
```

## 分享(Share)

这次分享的是我自己写的两篇关于 `Docker` 的学习笔记。

- [Docker 的学习笔记(一)](https://s7.zzs7.top/docker.html)
- [Docker 的学习笔记(二)](https://s7.zzs7.top/docker-2.html)
