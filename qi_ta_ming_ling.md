# 其他命令

**man命令**

man 该命令是一个帮助命令，在使用man命令之前需要了解帮助文档的[目录结构以及操作方式](http://www.linuxprobe.com/chapter02/#22)。

---
**cat命令**

    cat /etc/redhat-release 查看系统版本
    cat /etc/centos-release 
    
---
**echo命令**

echo命令用于在终端显示字符串或变量。格式为：```echo [字符串|变量]```

示例：
            
        echo ZhengHuanRong      将字符串输入到终端
        echo $SHELL             查看SHELL变量的值
        echo $HOSTNAME          查看本机主机名

---
**date命令**

date命令用于按照指定格式显示/设置系统的时间或日期。格式为：```date [选项] [+指定的格式]```，只需键入”+”号开头的字符串指定其格式。

示例：

        date                        查看系统时间
        date "+%Y-%m-%d %H:%M:%S"   按照格式查看系统
