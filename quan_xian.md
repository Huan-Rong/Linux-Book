# 权限
当为某一文件或目录设置权限时，我们可以为不同的角色设置不同的权限。其中，“不同的角色”是指**owner、group、others**；“不同的权限”是指我们可以为三种角色分别设置**RWX**三种权限。

但在深入探讨权限这个话题之前，我们先来看看文件的属性。因为文件的权限其实是文件属性的一种，了解文件的属性是有必要的。

## 文件的属性
```
[ian@Jarvis-C Documents]$ ls -l
total 12
-rw-rw-r--. 1 ian ian 137 Nov  7 00:51 exam2.sh
-rw-rw-r--. 1 ian ian  53 Nov  7 00:13 example.sh
drwxrwxr-x. 2 ian ian   6 Nov  8 13:51 pics
-rw-rw-r--. 1 ian ian  21 Nov  6 23:38 practice.txt


-----------------------------------------------------
权限 连接数 owner group size createdTime|lastModifiedTime fileName
```
说明：
* 执行```ls -l```命令可以查看当前工作目录下的文件及其相关属性。
* 权限部分一共有10个字符组成，第一个表示文件的类型。-表示是文件，d表示是目录


设置权限的方式有两种：
1. 数字法设置权限
2. 符号法设置权限
