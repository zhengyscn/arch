

# Zookeeper Cluster


## Download package
```
# wget https://mirrors.tuna.tsinghua.edu.cn/apache/zookeeper/zookeeper-3.4.9/zookeeper-3.4.9.tar.gz 
```

## Configure
```
# cp conf/zoo_sample.cfg conf/zoo.cfg
# vim conf/zoo.cfg

dataDir=/data/zk/
server.1=10.13.128.229:2887:3887 
server.2=10.13.128.86:2887:3888
server.3=10.13.128.127:2887:3889

# echo 1 > /data/zk/myid
```

## Start
```
# ./bin/zkServer.sh start
# ./bin/zkServer.sh status
```

## Connect
```
# ./bin/zkCli.sh -server 10.13.128.229:2181,10.13.128.86:2181,10.13.128.127:2181
```