# 归档与压缩

* **zip**命令用以压缩文件，如```zip linuxcast.zip myfile``` 
* **unzip**命令用以解压缩命令 
* **gzip**命令用以压缩文件 
* **tar**用以归档文件


    tar -cvf out.tar linuxcast  创建一个归档
    tar -xvf linuxcast.tar  释放一个归档
	tar -cvzf backup.tar.gz /etc 先进行归档，然后使用gzip进行压缩。
	                                其实是tar命令调用gzip命令。

| 参数 | 作用 |
| -- | -- |
| -c | 创建压缩文件 |
| -x | 释放压缩文件 |
| -v | 显示压缩或解压缩的过程 |
| -z | 使用Gzip压缩或者解压缩 |
| -f | 目标文件名 |
	    
[更多参数说明](http://www.linuxprobe.com/chapter02/#29)