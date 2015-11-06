# WHAT IS BASH
在弄清楚BASH是什么之前，需要先了解：```User <-----> Shell <------> OS Kernel```

* ```User```不能直接操作```OS Kernel```
* ```Shell```分为**CLI(Command Line Interface)**和**GUI(Graphical User Interface)**两种类型

---

Linux的Shell也有以上两种类型，以下为对应的实现：
* CLI: **BASH**
* GUI: **GNOME**

SHELL、CLI、GUI都是概念，而BASH、GNOME则是具体的实现。

BASH的命令格式：```命令名称 [命令参数] [命令对象]```

---
通过[强大的SHELL](http://www.linuxprobe.com/chapter02/#21_SHELL)这一小节知道，上边的图并不完整。应补充为：  
    
```User <-----> Shell <-----> 系统调用接口 <-----> OS Kernel <------> 硬件```

计算机硬件是由**运算器**、**控制器**、**存储器**、**输入/输出设备**等设备组成的，而能够让机箱内各种设备各司其职东西就叫做——系统内核。**内核负责驱动硬件、管理活动和分配/管理硬件资源**，如此说来系统内核对计算机来讲可真的是太重要了，所以它不能直接让用户操作。

因为用户不能直接控制硬件也不能直接操作内核，于是便需要基于“系统调用接口”开发出的程序/服务来满足用户日常工作了。



**SEE ALSO**：
* http://zhidao.baidu.com/link?url=7PpAJj_Y0cFQRI-lqanK5hApjamFPhsH96Qk7Uzn3kSd5qoCTn6Uowv6DRzTq5x-tBWPSoC-cYMRmDxgHmWeOq
* http://baike.baidu.com/link?url=tsQ3M9p-0UYE8gquHurAC-lXQgmTR0yjwhI9NbNb-9VeggOVHZwT8gypQzSYE9bEDYaqKdaJ38g5hgLvXkw5Sa#1
* 
