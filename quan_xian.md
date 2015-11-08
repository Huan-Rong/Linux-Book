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
* 权限部分一共由10个字符组成。第一位表示文件的类型，-表示是文件，d表示是目录；2~4位表示owner权限；5~7位表示group权限；8~10位表示others权限。

## 设置文件属性

这里的文件属性设置指的是对文件的owner/group/permission属性进行修改。

### chgrp
使用chgrp命令修改文件所属的用户组。  
**示例：**
```
[root@Jarvis-C Documents]# ls -l
total 12
-rw-rw-r--. 1 ian ian 137 Nov  7 00:51 exam2.sh
-rw-rw-r--. 1 ian ian  53 Nov  7 00:13 example.sh
drwxrwxr-x. 2 ian ian   6 Nov  8 13:51 pics
-rw-rw-r--. 1 ian ian  21 Nov  6 23:38 practice.txt

[root@Jarvis-C Documents]# chgrp users  exam2.sh
[root@Jarvis-C Documents]# ls -l
total 12
-rw-rw-r--. 1 ian users 137 Nov  7 00:51 exam2.sh
-rw-rw-r--. 1 ian ian    53 Nov  7 00:13 example.sh
drwxrwxr-x. 2 ian ian     6 Nov  8 13:51 pics
-rw-rw-r--. 1 ian ian    21 Nov  6 23:38 practice.txt

```

### chown
使用chown命令修改文件的owner属性。除此之外，chown命令可以修改文件的group属性。  
**示例：**
```
[root@Jarvis-C Documents]# ls -l
total 12
-rw-rw-r--. 1 ian users 137 Nov  7 00:51 exam2.sh
-rw-rw-r--. 1 ian ian    53 Nov  7 00:13 example.sh
drwxrwxr-x. 2 ian ian     6 Nov  8 13:51 pics
-rw-rw-r--. 1 ian ian    21 Nov  6 23:38 practice.txt

[root@Jarvis-C Documents]# chown root exam2.sh
[root@Jarvis-C Documents]# ls -l
total 12
-rw-rw-r--. 1 root users 137 Nov  7 00:51 exam2.sh
-rw-rw-r--. 1 ian  ian    53 Nov  7 00:13 example.sh
drwxrwxr-x. 2 ian  ian     6 Nov  8 13:51 pics
-rw-rw-r--. 1 ian  ian    21 Nov  6 23:38 practice.txt

[root@Jarvis-C Documents]# chown ian:ian exam2.sh
[root@Jarvis-C Documents]# ls -l
total 12
-rw-rw-r--. 1 ian ian 137 Nov  7 00:51 exam2.sh
-rw-rw-r--. 1 ian ian  53 Nov  7 00:13 example.sh
drwxrwxr-x. 2 ian ian   6 Nov  8 13:51 pics
-rw-rw-r--. 1 ian ian  21 Nov  6 23:38 practice.txt
```

### chmod
使用chmod命令可设置文件的权限。其方式有两种：

**数字法**

```
[ian@Jarvis-C Documents]$ ls -l
total 16
-rw-rw-r--. 1 ian ian 137 Nov  7 00:51 exam2.sh
-rw-rw-rw-. 1 ian ian 137 Nov  8 14:14 exam3.sh
-rw-rw-r--. 1 ian ian  53 Nov  7 00:13 example.sh
drwxrwxr-x. 2 ian ian   6 Nov  8 13:51 pics
-rw-rw-r--. 1 ian ian  21 Nov  6 23:38 practice.txt
[ian@Jarvis-C Documents]$ chmod 664 exam3.sh
[ian@Jarvis-C Documents]$ ls -l
total 16
-rw-rw-r--. 1 ian ian 137 Nov  7 00:51 exam2.sh
-rw-rw-r--. 1 ian ian 137 Nov  8 14:14 exam3.sh
-rw-rw-r--. 1 ian ian  53 Nov  7 00:13 example.sh
drwxrwxr-x. 2 ian ian   6 Nov  8 13:51 pics
-rw-rw-r--. 1 ian ian  21 Nov  6 23:38 practice.txt
```

**符号法**

```
[ian@Jarvis-C Documents]$ ls -l
total 16
-rw-rw-r--. 1 ian ian 137 Nov  7 00:51 exam2.sh
-rw-rw-r--. 1 ian ian 137 Nov  8 14:14 exam3.sh
-rw-rw-r--. 1 ian ian  53 Nov  7 00:13 example.sh
drwxrwxr-x. 2 ian ian   6 Nov  8 13:51 pics
-rw-rw-r--. 1 ian ian  21 Nov  6 23:38 practice.txt
[ian@Jarvis-C Documents]$ chmod o+w exam3.sh
[ian@Jarvis-C Documents]$ ls -l
total 16
-rw-rw-r--. 1 ian ian 137 Nov  7 00:51 exam2.sh
-rw-rw-rw-. 1 ian ian 137 Nov  8 14:14 exam3.sh
-rw-rw-r--. 1 ian ian  53 Nov  7 00:13 example.sh
drwxrwxr-x. 2 ian ian   6 Nov  8 13:51 pics
-rw-rw-r--. 1 ian ian  21 Nov  6 23:38 practice.txt
```
## 目录之权限和文件之权限
权限对目录和文件来说其意义是不同的。
### 文件之权限
* r(read)：可读取此一文件的实际内容，如读取文本文件的文字内容等；
* w(write)：可以编辑、新增或者是修改该文件的内容(但不含删除该文件)；
* x(execute)：该文件具有可以被系统执行的权限。

### 目录之权限
* r (read contents in directory)  
表示具有读取目录结构列表的权限，所以当你具有读取(r)一个目录的权限时，表示你可以查询该目录下的文件名数据。 所以你就可以利用 ls 这个指令将该目录的内容列表显示出来！
* w (modify contents of directory)：  
这个可写入的权限对目录来说，是很了不起的！ 因为他表示你具有异动该目录结构列表的权限，也就是底下这些权限：
    *   建立新的文件与目录；
    *   删除已经存在的文件与目录(不论该文件的权限为何！)
    *   将已存在的文件或目录进行更名；
    *   搬移该目录内的文件、目录位置。

