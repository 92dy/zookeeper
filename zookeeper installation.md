## JDK
```
~]# tar -xf jdk-8u45-linux-x64.tar.gz -C /usr/local/
~]# cd /usr/local/
local]# ln -sv jdk1.8.0_45/ jdk1_8
local]# vim /etc/profile.d/jdk.sh
local]# vim /etc/profile.d/jdk.sh
export JAVA_HOME=/usr/local/jdk1_8
export PATH=$JAVA_HOME/bin:$PATH
export CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
local]# source  /etc/profile.d/jdk.sh
```

## 获取zk- [zk下载](https://www.apache.org/dyn/closer.cgi/zookeeper/)
```
src]# wget http://apache.mirror.globo.tech/zookeeper/stable/zookeeper-3.4.14.tar.gz
src]# tar -xf zookeeper-3.4.14.tar.gz -C ../
src]# cd ../
local]# ln -sv zookeeper zookeeper-3.4.14/
local]# cd zookeeper-3.4.14/conf/
conf]# cp zoo_sample.cfg zoo.cfg
conf]# vim zoo.cfg
  tickTime=2000
  initLimit=10
  syncLimit=5
  dataDir=../data
  clientPort=12181
  server.1=10.42.0.20:12888:13888
  server.2=10.42.0.33:12888:13888
  server.3=10.42.0.44:12888:13888
conf]# mkdir ../data
```
```
conf]# echo 1 > ../data/myid
conf]# echo 2 > ../data/myid
conf]# echo 3 > ../data/myid
```
```
conf]# ../bin/zkServer.sh  start
```
