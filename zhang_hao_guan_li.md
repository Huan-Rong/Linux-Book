# 账号管理

**问题：Linux如何辨别每一个用户？**

## 相关文件
### 文件/etc/passwd

The  /etc/passwd file is a text file that describes user login accounts for the system. It should have read permission allowed for  all  users(many  utilities,  like ls(1) use it to map user IDs to usernames), but write access only for the superuser.  
Each line of the file describes  a  single  user,  and  contains  seven colon-separated fields:

    name:password:UID:GID:GECOS:directory:shell
    
### 文件/etc/shadow

shadow is a file which contains the password information for the system's accounts and optional aging information. This file must not be readable by regular users if password security is to be maintained.   
Each line of this file contains 9 fields, separated by colons (“:”), in the following order:

    login name
    encrypted password
    date of last password change
    minimum password age
    maximum password age
    password warning period
    password inactivity period
    account expiration date
    reserved field

## UID