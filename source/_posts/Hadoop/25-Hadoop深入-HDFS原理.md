---
layout: title
title: 25-Hadoop深入 HDFS原理
date: 2019-01-28 04:25:15
tags: 大数据Hadoop基础入门到高级精通
categories:
  - hadoop
---
## 25-Hadoop深入 HDFS原理
DataNode
+ 数据存储在hdfs-site.xml的dfs.datanode.data.dir属性配置中
    存储内容： 数据本身数据的长度、校验和 和 时间戳。
+ 文件块（block）：基本的存储单元，默认大小是128M，通过dfs.blocksize属性配置
+ 副本策略： 默认是3个，通过dfs.replication属性配置
{% asset_img "副本策略.png"  This is hadoop hdfs 副本策略%}
  - 第一个block副本放在和client所在的node里（如果client不在集群范围内，则这第一个的node是随机选取的，当然系统会尝试不选择那些太满或者太忙的node）
  - 第二个副本放在与第一个节点不同机架的node中（随机选择）
  - 第三个副本和第二个在同一个机架，随机放在不同的node中。如何还有更多的副本，就随机放在集群的node里。
   