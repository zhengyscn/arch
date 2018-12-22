

## kafka

- 消息队列 1对1
- 发布订阅 1对多
 
```
1. 消息队列
Producter --> kafka <-- Consumer

2. 发布订阅

                    --> Consumer
Producter --> kafka --> Consumer
                    --> Consumer

```


## Package
```
# wget https://download.oracle.com/otn-pub/java/jdk/8u191-b12/2787e4a523244c269598db4e85c51e0c/jdk-8u191-linux-x64.tar.gz?AuthParam=1545389505_61b51a9b8478f98d8e10001923116c7f
# wget http://www.apache.org/dist/zookeeper/zookeeper-3.4.13/zookeeper-3.4.13.tar.gz
# wget https://ftp.cc.uoc.gr/mirrors/apache/kafka/2.1.0/kafka_2.12-2.1.0.tgz
```

## Start
```
--- 启动zookeeper集群 ---
# cp conf/zoo_sample.cfg conf/zoo.cfg
# ./bin/zkServer.sh start


--- 启动kafka集群 ---
# cd /usr/local/kafka
# ./bin/zookeeper-server-start.sh -daemon config/zookeeper.properties
# jps -l
20373 sun.tools.jps.Jps
20283 org.apache.zookeeper.server.quorum.QuorumPeerMain
# netstat -tnlp | grep java
tcp6       0      0 :::2181                 :::*                    LISTEN      20283/java          
tcp6       0      0 :::38100                :::*                    LISTEN      20283/java

# vim config/server.properties
broker.id=xxx 集群的唯一标识，每个节点唯一
# ./bin/kafka-server-start.sh config/server.properties
# ./bin/kafka-server-start.sh -daemon config/server.properties
```

## Create
```
./bin/kafka-topics.sh --zookeeper 10.13.128.229:2181 --create --topic vkops --replication-factor 2 --partitions 2
./bin/kafka-topics.sh --zookeeper 10.13.128.229:2181 --list
```
