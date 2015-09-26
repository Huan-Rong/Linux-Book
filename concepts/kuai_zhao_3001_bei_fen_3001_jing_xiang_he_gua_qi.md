# 个人理解(待确认)

#### 快照

快照的目的并非是为了离线容灾。更明确的说法是，快照并非是为了产生一个备份文件的。存在即合理，那么，快照有什么作用呢？用于进行数据的快速恢复。

#### 备份

备份，相当于在某个时间点把数据库里的所有对象内容都COPY一份，放到一个特定的文件里(备份文件，一般是.bak)。备份的结果是文件，这个文件可以被COPY带走，或者写入磁带(放到银行里),从而实现离线容灾。

#### 镜像 

镜像和备份很类似，但是它们二者的使用场合不同，因此技术实现上也有差异。

#### 参考
1. [知乎上关于快照与备份的讨论,值得思考](http://www.zhihu.com/question/20374919)
2. [百度知道上关于快照、备份、挂起的解释，个人认为较为准确](http://zhidao.baidu.com/question/583584549824231605.html)
3. [ChinaUnix上关于镜像、克隆、快照的解释，个人认为较为准确](http://bbs.chinaunix.net/thread-3920050-1-1.html)
4. [百度百科词条：存储快照，有点深奥](http://baike.baidu.com/link?url=KlJZSaOb2nnQ4YYlaR-QiH7FoNRS-u58kpwXsZZQcX_xPM9pYk9BPg-O9LkZUN5QdUlRAgL_xyqjPkCyrjwYGq)
5. [百度百科词条：镜像](http://baike.baidu.com/link?url=wHMK8t8uLtmO3g8e3WZTcW1cFVoxplC1rO0ZcoBi-UgkiW9VImViSwSVQuvSeH3t57HnU5t8XQpyzhGV21YW-GODsjJmQewqm02uWPC4Ccq)