# 账号管理

**问题：Linux如何辨别每一个用户？**

---

## /etc/passwd

The  /etc/passwd file is a text file that describes user login accounts for the system. It should have read permission allowed for  all  users(many  utilities,  like ls(1) use it to map user IDs to usernames), but write access only for the superuser.  
Each line of the file describes  a  single  user,  and  contains  seven colon-separated fields:

    name:password:UID:GID:GECOS:directory:shell