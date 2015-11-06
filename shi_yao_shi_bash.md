# WHAT IS BASH
在弄清楚BASH是什么之前，需要先了解：```User <-----> Shell <------> OS Kernel```

* ```User```不能直接操作```OS Kernel```
* ```Shell```分为**CLI(Command Line Interface)**和**GUI(Graphical User Interface)**两种类型

---

Linux的Shell也有以上两种类型，以下为对应的实现：
* CLI: **BASH**
* GUI: **GNOME**

SHELL、CLI、GUI都是概念，而BASH、GNOME则是具体的实现。

---
通过[强大的SHELL](http://www.linuxprobe.com/chapter02/#21_SHELL)这一小节知道，上边的图并不完整。应补充为：
```User <-----> Shell <-----> 系统调用接口 <-----> OS Kernel <------> 硬件```
