

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


## install
```
# wget https://ftp.cc.uoc.gr/mirrors/apache/kafka/2.1.0/kafka_2.12-2.1.0.tgz
# wget https://download.oracle.com/otn-pub/java/jdk/8u191-b12/2787e4a523244c269598db4e85c51e0c/jdk-8u191-linux-x64.tar.gz?AuthParam=1545389505_61b51a9b8478f98d8e10001923116c7f

```

## start
```
# cd /usr/local/kafka
# ./bin/zookeeper-server-start.sh -daemon config/zookeeper.properties
# jps -l
20373 sun.tools.jps.Jps
20283 org.apache.zookeeper.server.quorum.QuorumPeerMain
# netstat -tnlp | grep java
tcp6       0      0 :::2181                 :::*                    LISTEN      20283/java          
tcp6       0      0 :::38100                :::*                    LISTEN      20283/java

```

$ jps -l
