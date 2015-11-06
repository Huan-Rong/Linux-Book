# 查找命令
**locate命令**
* 用以快速查看文件/文件夹，locate命令执行非常**快**。
* 但locate命令**需要预先建立数据库**。数据库默认每天更新一次，可以用```updatedb```命令手工建立、更新数据库。

**find命令**
* 用以高级查看文件/文件夹
* 语法格式：```find [查找路径] 寻找参数```

		find . -name *linuxcast* 根据文件名称进行查找
		find / -name *.conf
		find / -perm 777  根据权限进行查找
		find / -type d    根据类型进行查找
		find . -name "a*" -exec ls -l {} \;

		其他的一些参数：
		-user
		-group
		-ctime
		-size