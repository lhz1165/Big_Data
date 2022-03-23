# HIVE 和 HADOOP实战

启动hadoop

```
start-dfs.sh
```

创建一个单词文本



启动hive

```
hive
#上传到hadoop hdfs
hive> load data local inpath '/home/lai/bigdata/data.txt' into table wordcount;
#创建一个数据库
hive>  create table jishu(danci string);
# 切分单词 插入数据库
hive>insert into table jishu select explode(split(line," ")) as danci from wordcount;
#查询结果
hive> select danci,count(*) from jishu group by danci;
```

