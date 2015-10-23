# bfs
distributed file system(small file storage) writen by golang according to facebook haystack.
分布式小文件存储
今日更新
* 使用yaml解析配置文件；
* 增加了volume的benchmark 代码，使用go test -bench=. 可以全量测试；
* 完成了store的meta index 文件解析，可以指定volume的存储位置、索引和对应的id；

TODO：
* 对外暴露api，（rpc，http等）；
* README文档；

昨日本机macbook air ssd压测：
单线程 volume 1kb写入
单词write：35405.74tps/s 吞吐：30-40mb/s，dd测试：40mb/s
批量write：73453.79tps/s 吞吐：80-90mb/s，dd测试：110mb/s
包含block追加写，和index追加写

多线程read: 79983.32qps/s
