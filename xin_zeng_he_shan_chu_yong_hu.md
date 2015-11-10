## 新增用户
    useradd [-u UID] 
            [-g 初始群组] 
            [-G 次要群组] 
            [-mM] 
            [-c 说明栏] 
            [-d 家目录绝对路径] 
            [-s shell] 
            用户名
            
使用useradd命令最重要的事情是：**useradd命令参考了哪些文件、对哪些文件进行了修改**。

            
对于不同的选项，系统已经有了相应的默认值。因此，我们可以简单地使用命令```useradd user_name```。系统默认处理如下的事情：
* 在/etc/passwd里面创建一行与账号相关的数据，包括创建 UID/GID/家目录等
* 在/etc/shadow里面将此账号的口令相关参数填入，但是尚未有口令
* 在/etc/group里面加入一个与账号名称一模一样的组名
* 在/home 底下创建一个与账号同名的目录作为用户家目录，且权限为 700

### 参考文件
    /etc/default/useradd
    /etc/login.defs
    /etc/skel/* 

需要注意的概念：**私有用户组机制、公共用户组机制**。

### 需要修改的文件

    用户账号与口令参数方面的文件：/etc/passwd, /etc/shadow
    使用者群组相关方面的文件：/etc/group, /etc/gshadow
    用户的家目录：/home/账号名称

## passwd
新的 distributions 是使用较严格的 PAM 模块来管理口令
## 删除用户
**userdel**的目的在于删除用户相关的数据。如果只是要某一账号暂时无法使用，可将/etc/shadow的账号失效日期(第八字段)设置为0，从而保留该账号相关的数据。

## 修改账号信息
**usermod**用于微调账户的设置。


