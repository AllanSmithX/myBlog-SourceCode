---
layout: title
title: 10-MapReduce执行流程
date: 2019-01-14 18:53:25
tags: 大数据Hadoop基础入门到高级精通
categories:
  - hadoop
---

## MapReduce 概述

- 将计算过程分为两个阶段：Map 和 Reduce
  Map 阶段并行处理输入数据
  Reduce 阶段对 Map 结果进行汇总
- Shuffle 连接 Map 和 Reduce 两个阶段
  Map Task 将数据写入到本地磁盘
  Reduce Task 从每个 Map Task 上读取一份数据
- 仅适合离线批处理
  具有很好的容错性和扩展性
  适合简单的批处理任务
- 缺点明显
  系统开销大、过多使用磁盘导致效率低下等

## MapReduce 执行过程

{% asset_img "MapReduce执行过程.png"  This is MapReduce执行过程图%}
