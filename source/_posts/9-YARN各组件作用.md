---
layout: title
title: 9-YARN各组件作用
date: 2019-01-14 15:42:23
tags: 大数据Hadoop基础入门到高级精通
categories:
  - hadoop
---

## YARN 各组件作用

- ResourceManageer
  - 处理客户端请求
  - 启动/监控 ApplicationMaster
  - 监控 NodeManager
  - 资源分配与调度
- ApplicationMaster
  - 程序切分
  - 为应用程序申请资源
  - 任务监控与容错
- NodeManage
  - 单个节点上的资源管理
  - 处理来自 ReousrceManger 的命令
  - 处理来自 ApplicationMaster 的命令
- Container
  - 对任务运行环境的抽象，封装了 CPU、内存等多维资源以及环境变量、启动命令等任务运行香港的信息
