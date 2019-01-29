---
layout: title
title: 24-Hadoop深入 HDFS原理
date: 2019-01-28 04:07:01
tags: 大数据Hadoop基础入门到高级精通
categories:
  - hadoop
---
##  24-Hadoop深入 HDFS原理
# 1、HDFS原理
   + 1>三大组件
      NameNode、DataNode、SecondaryNameNode
   + 2>NameNode
       a.作用
            存储元数据（文件名、创建时间、大小、权限、文件与block块映射关系）
   + 3>DataNode
       a.作用
             存储真实的数据信息
   + 4>SecondaryNameNode
       a.作用
             减去NameNode压力，将edits编辑日志文件和fsimage镜像文件进行合并。
   + 数据存储在hdfs-site.xml的dfs.namenode.name.dir属性配置中
   - 1.fsimage:镜像文件，存储某时段内元数据信息和文件与Block块的映射关系（NameNode第一映射关系）
   - 2.edits：编辑日志文件
   - 3.seen_txid操作事务id
   - 4.VERSION:存储命名空间ID、集群ID等信息
   ## 多次格式化namenode的问题原因解释
   + hdfs格式化会改变VERSION文件中的clusterID,首次格式化时datanode和namenode会产生相同的clusterID;
   如果重新执行格式化，namenode的clusterID改变，就会与datanode的clusterID不一致，如果重新启动或读写hdfs就会挂掉。
   