---
layout: title
title: 18-hadoop分布式配置
date: 2019-01-28 02:44:16
tags: 大数据Hadoop基础入门到高级精通
categories:
  - hadoop
---

##  18-hadoop分布式配置
 分布式环境（Distributed)
    + 配置yarn-site.xml 文件
        <property>
           <name>yarn.resourcemanager.hostname</name>
           <value>master</value>
        </property>
    + 配置$HADOOP_HOME/etc/hadoop/slaves文件
       hadoop-senior01.test.com
       hadoop-senior02.test.com
       hadoop-senior03.test.com
