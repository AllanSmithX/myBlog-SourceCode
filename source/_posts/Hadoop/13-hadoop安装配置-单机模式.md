---
layout: title
title: 13-hadoop安装配置 单机模式
date: 2019-01-26 08:26:15
tags: 大数据Hadoop基础入门到高级精通
categories:
  - hadoop
---

## 13、14 -hadoop安装配置（单机模式、伪分布式模式）
+ 单机模式（standalone) 
   仅适用于单机运行分布式计算作业，直接指向mapreduce-examples.jar案例

```
  mkdir input
  cp etc/hadoop/*.xml input
  bin/hadoop jar share/hadoop/mapreduce/hadoop-mapreduce-examples-2.6.0-cdh5.9.0.jar grep input output 'dfs[a-z.]+'
  cat output/*
  ```
  
 + 伪分布式模式
    一个服务器上运行多个进程。
   一、HDFS
    - 1> 配置 etc/hadoop/core-site.xml
       
       ```
       <configuration>
            <property>
                <name>fs.defaultFS</name>
                <value>hdfs://localhost:9000</value>
            </property>
       </configuration>
       ```
       
     - 2> 配置 etc/hadoop/hdfs-site.xml
     
       ```
       <configuration>
            <property>
                <name>fs.replication</name>
                <value>1</value>
            </property>
       </configuration>
       ```
     - 3> 格式化NameNode
       作用：清空NameNode目录下的所有数据，生成目录结构，初始化一些信息到文件中。
     - 4> 启动HDFS各个进程
         ```
         sbin/start-dfs.sh 
         或
         sbin/hadoop-daemon.sh start namenode
         sbin/hadoop-daemon.sh start datanode
         sbin/hadoop-daemon.sh start secondarynamenode
         ```
     - 5>浏览器访问
           http://<主机名>:50070
         注： 50070是http协议的端口号；8020是RPC tcp协议的端口号
   二、YARN
       - 1>配置mapred-site.xml
       - 2>配置yarn-site.xml
       - 3>启动YARN进程   ResourceManager、NodeManager
          ``` 
            sbin/start-yarn.sh
            或
            sbin/yarn-daemon.sh start resourcemanager
            sbin/yarn-daemon.sh satrt nodemanager
          ```
        - 4> 浏览器访问
          http://<主机名>:8088
          注：8032是RPC tcp协议的端口号；8088 是http协议的端口号
     

