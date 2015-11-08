# 权限
当为某一文件或目录设置权限时，我们可以为不同的角色设置不同的权限。其中，“不同的角色”是指**owner、group、others**；“不同的权限”是指我们可以为三种角色分别设置**RWX**三种权限。

但在深入探讨权限这个话题之前，我们先来看看文件的属性。因为文件的权限其实是文件属性的一种，了解文件的属性是有必要的。

## 文件的属性
```
[ian@Jarvis-C Documents]$ ls -l
total 12
-rw-rw-r--. 1 ian ian 137 Nov  7 00:51 exam2.sh
-rw-rw-r--. 1 ian ian  53 Nov  7 00:13 example.sh
-rw-rw-r--. 1 ian ian  21 Nov  6 23:38 practice.txt
```

设置权限的方式有两种：
1. 数字法设置权限
2. 符号法设置权限
