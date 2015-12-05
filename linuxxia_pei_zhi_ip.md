# Linux下配置IP

在Linux系统中配置IP地址的方法有4种：

1. ```ifconfig```命令**临时**配置IP
2. setup工具永久配置IP，但setup是Redhat系列发行版的**专有命令**
3. 修改网络配置文件，是标准的配置方法
4. 通过图形界面配置IP

| 方法 | 说明 |
| -- | -- |
| ifconfig命令 | 通过```ifconfig```命令可以**临时**配置IP地址，但是```ifconfig```命令主要用于**查看**网络状态。 |
| setup工具 | setup工具可以永久配置IP地址，但setup是Redhat系列的**专有命令**。 |
| 网络配置文件 | 通过修改网络配置文件来配置IP地址是标准的配置方法，必须掌握。 |
| 图形界面 | 与在Windows下配置IP的方法类似，仅作了解 |

## ifconfig

## setup