# 正确的关机方法
## 不正常的关机
所有的数据都得要被读入内存后才能够被CPU所处理，但是数据又常常需要由内存写回硬盘当中(例如储存的动作)。由于硬盘的速度太慢(相对于内存来说)，如果常常让数据在内存与硬盘中来回写入/读出，系统的性能就不会太好。

因此在Linux系统中，为了加快数据的读取速度，所以在默认的情况中， 某些已经加载内存中的数据将不会直接被写回硬盘，而是先缓存在内存当中，如此一来， 如果一个数据被你重复的改写，那么由于他尚未被写入硬盘中，因此可以直接由内存当中读取出来， 在速度上一定是快上相当多的！

不过，如此一来也造成些许的困扰，那就是万一你的系统因为某些特殊情况造成不正常关机 (例如停电或者是不小心踢到power)时，**则可能造成文件系统的毁损**。