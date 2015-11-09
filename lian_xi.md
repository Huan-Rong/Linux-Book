**练习1：**在/etc/passwd中新增一行数据，其name为test，其UID为ian账号的UID；然后修改ian账号的UID为其他值；最后查看原来ian账户中的任一文件。

    // 第一步：修改/etc/passwd文件之前，查看/home/ian/Documents目录下的文件
    [ian@Jarvis-C Documents]$ ls -l
    total 12
    -rw-rw-r--. 1 ian  1000 137 Nov  7 00:51 exam2.sh
    -rw-rw-r--. 1 ian  1000  53 Nov  7 00:13 example.sh
    drwxrwxr--. 2 root root  21 Nov  8 15:12 pics
    -rw-rw-r--. 1 ian  1000  21 Nov  6 23:38 practice.txt

    // 第二步：修改/etc/passwd文件
    [root@Jarvis-C Documents]# vim /etc/passwd
    // 省略部分数据...
    ian:x:1001:1000:ian:/home/ian:/bin/bash
    test:x:1000:1000:test::/bin/bash

    // 第三步：修改/etc/passwd文件后，查看/home/ian/Documents目录下的文件
    [ian@Jarvis-C Documents]$ ls -l
    total 12
    -rw-rw-r--. 1 test 1000 137 Nov  7 00:51 exam2.sh
    -rw-rw-r--. 1 test 1000  53 Nov  7 00:13 example.sh
    drwxrwxr--. 2 root root  21 Nov  8 15:12 pics
    -rw-rw-r--. 1 test 1000  21 Nov  6 23:38 practice.txt
    

**练习2：在/etc/passwd中修改ian账户的UID之后，ian账户无法再次登录系统。**
测试环境为：CentOS 7。
