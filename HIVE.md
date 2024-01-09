# HIVE实践

使用hiveserver2的beeline连接数据库

![image-20240108200156479](assets/HIVE/image-20240108200156479.png)

```
//启动服务
hiveserver2

//使用beeline连接hive数据库
beeline -u jdbc:hive2://localhost:10000 -n root

//数据库
jdbc:hive2://localhost:10000> show databases




```



使用自己的数据库

![image-20240108200417061](assets/HIVE/image-20240108200417061.png)



准备一个字符串文件

![image-20240108200644840](assets/HIVE/image-20240108200644840.png)

把本地的文件加载到表中

![image-20240108200550931](assets/HIVE/image-20240108200550931.png)



使用sql执行mapreduce，把结果存入word_count表中，并查看结果

![image-20240108200809959](assets/HIVE/image-20240108200809959.png)

使用datagridp可视化工具连接hive

![image-20240109101358835](assets/HIVE/image-20240109101358835.png)

![image-20240109101419954](assets/HIVE/image-20240109101419954.png)

![image-20240109101428378](assets/HIVE/image-20240109101428378.png)