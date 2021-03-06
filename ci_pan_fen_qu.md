# 硬盘分区
**参考资料：**
* [鸟哥的私房菜 第三版 第三章 主机规划和磁盘分区](http://vbird.dic.ksu.edu.tw/linux_basic/0130designlinux_2.php)
* [linuxprobe.com 第六章 存储结构与磁盘划分](http://www.linuxprobe.com/chapter06/#63)
* [BIOS和CMOS的区别](http://zhidao.baidu.com/link?url=CO_OhTibuoKfy0ZELdDFM0iwlhBIEVzcTzz_4vM0x__K0quIX3-FDYrnIXl8ER2zvOSr9D4QbQ3uWnKvl69f-a)

## 硬盘的组成

硬盘主要由磁盘、机械手臂、磁盘读取头、主轴马达所组成。磁盘可细分出扇区/磁区(Sector)与磁柱(Cylinder)两种单位， 其中每一个扇区的大小为512 bytes。如下图：
![硬盘的组成](harddisk.jpg)

整个硬盘的第一个磁区特别的重要，因为它记录了整个硬盘的重要信息分别是：

* 主引导记录(Master Boot Record，MBR)：安装启动管理程序的地方，大小为446 bytes。
* 分区表(partition table)：记录硬盘的分区信息，有64 bytes。

磁柱是进行分区时分配空间的最小单位。每一个区记录了该区段的起始与结束的磁柱号码。

## 硬盘分区
* 分区表中最多只能记录4个分区信息，其中扩展分区最多只能有一个，其余三个为主分区。
* 分区编号1~4是保留给主分区或者扩展分区的，从5开始的分区编号是用于逻辑分区的。
* 扩展分区的目的是使用额外的扇区来记录分区信息，以达到获取更多分区的目的。
* 主分区和逻辑分区可以被格式化、用作数据存取。扩展分区则不可以。
* 逻辑分割的数量依操作系统而不同，在Linux系统中，IDE硬盘最多有59个逻辑分割(5号到63号)，SATA硬盘则有11个逻辑分割(5号到15号)。

## 启动流程与主引导记录MBR

**启动流程：**

1. BIOS是启动时计算机系统会主动运行的第一个程序。
2. BIOS会去分析计算机里面有哪些储存设备，我们以硬盘为例，BIOS会依据使用者的配置去取得能够启动的硬盘，并且到该硬盘里面去读取第一个磁区的MBR位置。MBR这个仅有446 bytes的硬盘容量里面会放置最基本的启动管理程序(Boot Loader)。此时BIOS就功成圆满，而接下来就是MBR内的启动管理程序的工作了。
3. 启动管理程序加载核心文件。
4. 核心文件开始工作。

**说明：**
* **OS启动需要Boot Loader**
* **Boot Loader可以安装在MBR或者Boot Sector**
* 计算机系统里面可能具有两个以上的Boot Loader。
* Boot Loader只会认识自己的系统所在分区内的可启动核心文件，以及其他Boot Loader而已。
* 多重启动的重点是多个Boot Loader。

## 挂载
挂载就是利用一个目录当成进入点，将硬盘分区的数据放置在该目录下；也就是说，进入该目录就可以读取该分区的数据。**将分区(或硬盘设备)与一个已存在的目录文件做关联的动作称为挂载**。该目录称为挂载点。

由于整个Linux系统最重要的是根目录，因此根目录一定与某一分区关联。至于其他的目录则可依使用者自己的需求来挂载到不同的分区。