# ARTS(week04)

## 算法题(Algorithm)

- 题目：[寻找两个有序数组的中位数](https://leetcode-cn.com/problems/median-of-two-sorted-arrays/)
- 解答：[median_of_two_sorted_arrays](https://github.com/SharonChiong/leetcode/blob/master/algorithms/python/median_of_two_sorted_arrays/median_of_two_sorted_arrays.py)


## 阅读点评(Review)

#### [Install/Deploy Instructions for Tez](http://tez.apache.org/install.html)

在部署`Hive`中，我遇到了一个问题，`Hive`启动时默认用的是`Hive on MR`, 即选用`MapReduce`计算引擎，
但是由于我下载的`Hive`包是`2.x`,`Hive on MR`已经废弃，所以官方建议使用另外两种计算引擎`Spark`或者`Tez`。

由于关于部署`Tez`的教程太少，所以我选择直接去清华大学的镜像网址下载`tez`包

部署成功之后，发现`Hive`启动报错了，经排查发现是`tez`有关`hadoop`的`jar`包基于`hadoop-2.7.2`编译生成。

然后决定下载`src`包，修改`pom.xml`配置文件，自行编译安装。

该文章讲述的是`Tez`的编译安装过程。

#### 步骤如下：

1. 修改`src`包根目录下的`pom.xml`，将`hadoop`版本改成你需要的版本，比如我现在用的`3.2.0`;
2. 安装`jdk1.8.0_*`、`Maven 3.*`、`Protocol Buffers 2.5.0`;
3. 编译`tez`
    ```bash
    $ mvn clean package -DskipTests=true -Dmaven.javadoc.skip=true
    ```

到这里编译安装就结束了，下面的是部署`tez`的步骤，较简单不赘述了。


## 技术技巧(Tip)

#### 修改容器中的时区

有的时候，创建的容器的时区是`UTC`，我们需要将它改成北京时间，但是容器已经运行，不想重新创建，可以将宿主机的时区复制给`docker`容器中。

当然，需要保证宿主机的时区是北京时间。步骤如下：

```bash
# 复制宿主机的时区到容器中，这里我未将非 root 用户加入 docker 用户组，所以前面要加 sudo
$ sudo docker cp /etc/localtime [容器id或name]:/etc/localtime

# 同样地，有时候文件的创建或修改时间也不正确，可以复制 /etc/timezone 到容器中
$ sudo docker cp /etc/timezone [容器id或name]:/etc/timezone

# 进入容器
$ sudo docker exec -it [容器id或name] bash

# 检查时区是否修改过来
$ date
```


## 分享(Share)

#### [打造高效的工作环境 - SHELL 篇](https://coolshell.cn/articles/19219.html)

这次分享的是耗子叔的文章。

作为`linux`小白，平时用的多的是`mkdir`, `ps`, `grep`, `tail`, `tar`, `mv`, `cp`, `find`, `rm`等等。

对于文中提到的`awk`和`sed`仅限于听过，没实际用过（汗颜），打算好好看看相关的教程。

有时候删除文件或文件夹，用的`rm -rf`更多，看到文中提到这是一个高危操作：强制性删除，不可修复。

`linux`编程是很好玩的事情，学的好可以给自己带来很多便捷，提高工作效率。

```log
Where is the Shell, there is a way.
```
