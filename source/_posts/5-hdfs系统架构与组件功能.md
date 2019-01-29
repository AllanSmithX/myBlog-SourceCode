---
layout: title
title: 5-hdfs系统架构与组件功能
date: 2019-01-13 12:35:36
tags: 大数据Hadoop基础入门到高级精通
categories:
  - hadoop
---

## HDFS 的架构图

{% asset_img "HDFS文件系统.png"  This is HDFS文件系统%}

## HDFS 组件

- NameNode：为主节点，存储文件元数据，如 文件名、文件目录、文件属性（生成时间、大小等），以及每个文件的块列表和块所在的 DataNode 等。
- DataNode: 在本地文件系统存储文件块数据，以及块数据的校验和。
- SecondaryNameNode: 用于监控 HDFS 状态的辅助后台程序，每隔一段时间获取 HDFS 元数据的快照。
