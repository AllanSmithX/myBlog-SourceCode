---
layout: title
title: 4-hdfs的引入
date: 2019-01-13 11:32:38
tags: 大数据Hadoop基础入门到高级精通
categories:
  - hadoop
---

## HDFS(Hadoop Destribute File System) 分布式文件系统

a.文件系统：文件管理 + block 块管理

- 单机文件系统：
  windows: FAT16、 FAT32 ...
  linux: EXT2/3/4、VFS
- 分布式文件系统
  多个服务器共同存储文件

## 搜索引擎存储文件示例图

{% asset_img "搜索引擎的文件存储.png"  This is 搜索引擎的文件存储 %}

## HDFS 示例图

在搜索引擎存储架构基础上提取出 driver 大管家中的公共部分，就基本得到 hfdfs 的架构
{% asset_img "HDFS文件系统(对比搜索引擎得到).png"  This is HDFS文件系统(对比搜索引擎得到)%}
下面是 HDFS 的文件系统图
{% asset_img "HDFS文件系统.png"  This is HDFS文件系统%}
