# ARTS(week08)

## 算法题(Algorithm)

- 题目：[字符串转换整数(atoi)](https://leetcode-cn.com/problems/string-to-integer-atoi/)
- 解答： [string_to_integer_atoi](https://github.com/SharonChiong/leetcode/blob/master/algorithms/python/string_to_integer_atoi/string_to_integer_atoi.py)


## 阅读点评(Review)

#### [To Revive the Mac, Apple Wants to Kill Electron](https://onezero.medium.com/to-revive-the-mac-apple-wants-to-kill-electron-154873336e78)

如今，桌面应用十分常见，开发一套 `desktop apps` 需要花费巨大和人力和时间，而且开发人员和设计人员需要为多个平台搭建，
如 `Windowns`, `macOS`, `Linux`.

此时，一个名叫 `Electron` 的框架出现了，她彻底改变了这种商业模式，破坏了现代应用程序的开发方式。

`Electron` 允许基于 `Web` 的编程语言和工具编写在每个操作系统上运行的单组代码。

如今，我们使用的许多工具都是基于 `Electron` 或者类似的框架。Apple 希望改变这种 macOS 应用程序基于 Web 技术的现状。

因为如果开发人员可以使用基于 Web 的框架进行构建，那么他们就不太可能使用 Apple 的工具，服务，以及最终的 Apple Store.

上周一在 AWDC 上宣布的 `Project Catalyst` 是一项旨在将开发人员带回公司生态系统的 `Hail Mary` 计划。

它的目的是使构建本机应用程序和使用 `Electron` 构建一样简单。`Catalyst` 使得使用 iPad 应用程序的开发人员可以轻松地将它们移植到 Mac, 减少代码库的修改。

但是 Apple 以最难以想象的方式展示了其前瞻性技术：通过展示项目跟踪软件 `Jira`, 和一些其他可忘记的产品。`Jira` 是开发人员不得不使用的最厌恶的项目管理工具之一。

`Catalyst` 可能会为 Mac 带来一些应用程序，但它不是 Apple 需要的赢家。


## 技术技巧(Tip)

#### MarkDown `hard-tabs` or `soft-tabs`

- Hard tabs use the tab character. 硬件 tabs 就是按一个 `tab` 键；

- Soft tabs are just spaces. Soft tabs are usually either 2 or 4 spaces, depending on convention.
软件 tabs 就是通过按 2 或 4 个 space 键来实现。

在编辑 Markdown 文件时，需要避免使用直接按一个 `tab` 键来实现缩进，不符合规范。


## 分享(Share)

#### [AWK 简明教程](https://coolshell.cn/articles/9070.html)

分享一篇耗子叔的文章，以示例为主，向读者介绍 `awk`.

```bash
# 输出指定例的信息，单引号中被大括号括着的就是 awk 语句
$ awk '{print $1, $4}' netstat.txt

# 过滤：内建变量 NR 表示加入表头
$ awk '$3==0 && $6=="LISTEN" || NR==1' netstat.txt

# 指定分隔符
$ awk 'BEGIN{FS=":"} {print $1,$3,$6}' /etc/passwd
# -F 表示该文件以 : 分隔，OFS表示以 \t 作为分隔符输出
$ awk -F: '{print $1,$3,$6}' OFS="\t" /etc/passwd

# 字符串匹配：~ 表示模式开始，// 中的是模式，一个正则表达式的匹配
$ awk '$6 ~ /FIN/ || NR==1 {print NR,$4,$5,$6}' OFS="\t" netstat.txt

# 拆分文件：使用重定向，如下是按照第 6 例分隔文件，NR!=1 表示不处理表头
$ awk 'NR!=1{print > $6}' netstat.txt

# 统计
$ ls -l *.py | awk '{sum+=$5} END {print sum}'
```

除去命令行，还有一种用法：awk 脚本。

- BEGIN{执行前的语句}

- END{处理完所有的行后要执行的语句}

- {处理每一行时要执行的语句}
