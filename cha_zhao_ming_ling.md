# 查找命令
**locate命令**
* 用以快速查看文件/文件夹。
* locate命令执行非常快。
* 但locate命令需要预先建立数据库，数据库默认每天更新一次，可以用updatedb命令手工建立、更新数据库。

## find用以高级查看文件/文件夹

		find 查找位置 查找参数

		find . -name *linuxcast*
		find / -name *.conf
		find / -perm 777  根据权限进行查找
		find / -type d    根据类型进行查找
		find . -name "a*" -exec ls -l {} \;

		其他的一些参数：
		-user
		-group
		-ctime
		-size