# diff
[了解diff - 1](http://www.ruanyifeng.com/blog/2012/08/how_to_read_diff.html)
[了解diff - 2](http://www.cnblogs.com/peida/archive/2012/12/12/2814048.html)

对diff的猜想：
* 从深层次来说，diff比较的是字节或者说是字符，因此这与编码方式有关。
* diff的实现需要注意空白、回车换行的处理。