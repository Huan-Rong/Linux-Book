# IP Address

## 概述

IP Address共有32位二进制，每八位为一组，使用句点将其分为四组并使用十进制表示。因此，IP Address的范围为[0.0.0.0, 255.255.255.255]。

### IP地址的分类
IP地址共有A、B、C、D、E五类，其中D类和E类不对民用组织开放。其他三类IP地址的范围如下表所示。

| Internet Protocol Address | 范围 | 私有IP地址范围 |
| -- | -- | -- |
| A类 | [1.0.0.0, 126.255.255.255] | [10.0.0.0, 10.255.255.255] |
| B类 | [128.0.0.0, 191.255.255.255] | [172.16.0.0, 172.31.255.255] |
| C类 | [192.0.0.0, 223.255.255.255] | [192.168.0.0, 192.168.255.255] |

据上表可知，通过IP地址的第一个十进制数可以区分ABC三类IP地址。  
另外，私有IP地址能够有效节约公网IP地址，但私有IP地址与公网之间不能直接进行通信，需要进行转换。

### IP地址与子网掩码
 
IP地址和子网掩码必须一起使用才有意义，由此可知IP地址所属**网段**以及网段能够拥有的主机数。处于不同网段的主机，通过路由进行通信；处于同一网段的主机，通过交换机进行通信。每个网段的第一个IP地址表示网络本身，而最后一个IP地址表示当前网络的广播地址，这两个IP地址都不能进行分配。

