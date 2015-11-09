# 其他命令
**ls命令**
ls命令有一个选项**-d**，该参数表示列出目录本身而不是目录中的内容。示例如下：
```
    [ian@Jarvis-C Documents]$ ll -d /home/ian
    drwx------. 14 ian 1000 4096 Nov  9 11:22 /home/ian
    [ian@Jarvis-C Documents]$ ll -d
    drwxr-xr-x. 3 ian 1000 68 Nov  8 15:12 .

```
说明：ll并不是一个命令，而是ls -l命令的别名.
---
**man命令**

man 该命令是一个帮助命令，在使用man命令之前需要了解帮助文档的[目录结构以及操作方式](http://www.linuxprobe.com/chapter02/#22)。

**示例：下面两条命令的效果不同**
    
    man 5 passwd
    man passwd


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

date命令用于按照指定格式显示/设置系统的时间或日期。格式为：```date [选项] [+指定的格式]```，只需键入”+”号开头的字符串指定其格式。[点击查看详细格式](http://www.linuxprobe.com/chapter02/#23)

示例：

    date 
        
    查看系统时间：Mon Aug 24 16:11:23 CST 2015    
    
    --------------------------------------------------------------
            
    date "+%Y-%m-%d %H:%M:%S"   
        
    按照格式查看系统时间：2015-11-24 16:29:12
    
    --------------------------------------------------------------
            
    date -s "20151106 8:30:00"  
        
    设置系统时间

---
**reboot命令**

reboot命令用于重启系统(仅root用户可以使用)，格式为：```reboot```

---
**wget命令**

用于使用命令行下载网络文件，格式为：```wget [命令参数] 下载地址```

| 参数 | 作用 |
| -- | -- |
| -c | 断点续传 |
| -r | 递归下载 |
| -p | 下载页面内所有资源，包括图片、视频|

---

## 系统检测命令

**ifconfig命令**

用于获取网卡配置与网络状态等信息。格式为```ifconfig [网络设备] [参数]```

