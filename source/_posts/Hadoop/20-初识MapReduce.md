---
layout: title
title: 20、21-初识MapReduce
date: 2019-01-28 03:25:18
tags: 大数据Hadoop基础入门到高级精通
categories:
  - hadoop
---
##  20、21-初识MapReduce

+ WordCount程序
     bin/hadoop jar share/hadoop/mapreduce/hadoop-mapreduce-examples-2.x.x.jar wordcount <input> <output>
+ WEB UI 监控
  - 节点状况
  - MapReduce Application状况
  - Container分配状况
   
+ 启动Hadoop服务器
   sbin/start-all.sh
+ 浏览器访问   
+ 各个指标
  a.Cluster Metrics
     集群指标：app(提交、排队、运行、完成）、Container个数、资源（内存、cpu) 
  b.Cluster Nodes Metrics
     及其状态： active、 decommissioning、decommissioned、lost、unhealthy\reboot
  c.dr.who用户的指标
    dr.who用户：通过浏览器访问访问默认使用dr.who 的用户   
## 聚合日志
  a.含义： I.分布式计算作业放到Nodemanager运行，日志信息放在NodeManager本地目录
    yarn.nodemanager.log-dirs: ${yarn.log.dir}/userlogs
           II.通过配置将本地日志放到HDFS服务器上，即聚合日志的概念
  b.配置
      + yarn.log-aggregation-enable 是否启用日志聚合功能，日志聚合开启后保存到HDFS上
      + yarn.log-aggregation.retain-seconds 聚合后的日志在HDFS上保存多长时间，单位为s
      + yarn.log-aggregation.retain-check-interval-seconds 删除任务在HDFS上执行的间隔，执行时候讲满足条件的日志删除（超过保存时间的日志），如果是0或者负数，则为参数2设置为1/10
      + yarn.nodemanager.log.retain-seconds 当不启用日志聚合此参数生效，日志文件保存在本地的时间，单位为s
      + yarn.nodemanager.remote-app-log-dir 当应用程序运行结束后，日志被转移到的HDFS目录（启用日志聚集功能时有效），修改为保存的日志文件夹
      + yarn.nodemanager.remote-app-log-dir-suffix 远程日志目录子目录名称（启用日志聚集功能时有效）
     
   