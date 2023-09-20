# Big_Data大数据环境

## 准备wsl2 docker

设置docker 源 或者使用代理

```json
 "registry-mirrors": [
    "https://hub-mirror.c.163.com",
    "https://mirror.baidubce.com"
  ]
```

打开2375 端口

Expose daemon on tcp://localhost:2375 without TLS



##  安装 hadoop+spark+hive

找到项目

```
git clone https://github.com/Marcel-Jan/docker-hadoop-spark.git

## 进入执行docker命令 等待下载完毕
docker-compose up -d
```

![image-20230918222437479](/assets/README/image-20230918222437479.png)

docker中

![image-20230918222505229](/assets/README/image-20230918222505229.png)

## Quick Start HDFS

把本地的测试文件复制到docker中

example.txt

```
hello world hello china 
hello laihong
good morning
```

复制

```
docker cp /mnt/d/ProgramSoft/BIG_DATA/docker-hadoop-spark/example.txt namenode:exampl
e.txt
```

进入docker 

```
  docker exec -it namenode bash
```

创建hdfs文件夹

```
hdfs dfs -mkdir -p /data/openbeer/breweries
```

复制金hdfs中,并查看

```
 hdfs dfs -put example.txt /data/openbeer/breweries/example.txt
 hdfs dfs -ls  /data/openbeer/breweries/
```

![image-20230918223315989](/assets/README/image-20230918223315989.png)

## 测试

使用hadoop自带测试jar

![image-20230918223635086](/assets/README/image-20230918223635086.png)



wordcount 测试

指定jar 以及输入，输入，输出路径

```
hadoop jar /opt/hadoop-3.2.1/share/hadoop/mapreduce/hadoop-mapreduce-examples-3.2.1.jar wordcount /data/openbeer/breweries/example.txt /data/openbeer/breweries/out
```

![image-20230918223843228](/assets/README/image-20230918223843228.png)

查看结果

```
hdfs dfs -ls /data/openbeer/breweries/out

hdfs dfs -cat /data/openbeer/breweries/out/part-r-00000
```

结果如下

![image-20230918224114962](/assets/README/image-20230918224114962.png)
