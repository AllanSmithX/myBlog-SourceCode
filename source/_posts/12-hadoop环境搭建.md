---
layout: title
title: 12-hadoop环境搭建
date: 2019-01-14 21:47:58
tags: 大数据Hadoop基础入门到高级精通
categories:
  - hadoop
---

## hadoop 环境搭建

1. 三个环境

- 单机
- 伪分布式
- 分布式

2. 三个分支

- apache 版本（Apache 基金会）
- cdh 版本(cloudera 公司）
- hdp 版本(HortOnWorks 公司)

3. 部署环境
   服务器： VMWare 虚拟机、Centos 6.4 系统
   客户端： xShell
4. 配置

- a.设置静态 IP
  - 图形化界面
  - 命令行

```
      vim /etc/sysconfig/network-scripts/ifcfg-th0
      service network restart
```

- b.设置主机名
  - 暂时性
  - 永久性
- c.主机名与 IP 映射

```
     vim /etc/sysconfig/network
     service newwork restart
```

5.  单机环境（Standalone)

```
mkdir input
cp etc/hadoop/*.xml input
bin/hadoop jar share/hadoop/mapreduce/hadoop-mapreduce-examples-2.6.0-cdh5.9.0.jar grep input output 'dfs[a-z]'
```
