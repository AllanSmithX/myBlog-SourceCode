---
layout: title
title: 26-Hadoop深入 HDFS原理
date: 2019-01-28 04:42:58
tags: 大数据Hadoop基础入门到高级精通
categories:
  - hadoop
---
## 26-Hadoop深入 HDFS原理
+ DataNode启动后向NameNode注册，注册后会周期性（1小时）向NameNode上报块信息（BlockReport）
  BlockReport数据内容： Block块与DataNode节点的映射关系（第二映射关系）
+ DataNode周期性的发送心跳（3s）给NameNode,心跳返回结果带有NameNode下发给DataNode的命令。如果超过10m,NameNode没有收到DataNode的心跳，则认为该节点不可用。
