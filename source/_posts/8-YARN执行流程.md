---
layout: title
title: 8-YARN执行流程
date: 2019-01-14 10:40:07
tags: 大数据Hadoop基础入门到高级精通
categories:
- hadoop
---
## YARN: 资源调度、任务管理
## YARN中四大组件
   ResourceManager(RM)、 NodeManager(NM)、 ApplicationMaster(AM)、 Container
## YARN执行流程
{% asset_img "YARN执行流程.png"  This is YARN执行流程图%}
- 1>client连接RM提交作业，RM给client一个JobId（注： ApplicationsManager 和 ResourceSchedular)。
- 2>RM中的的ApplicationManager连接一个NM,让NM创建一个AM用于处理客户端作业请求。
- 3>AM连接RM中ApplicationsManager申请NodeManager。
- 4>AM去取ResourceScheduler给client的作业申请资源（CPU、内存、磁盘、网络）。
- 5>AM连接NM,发送client job作业程序和申请的资源（CPU、内存、磁盘、网络）。
- 6>NM启动container进程运行不同job的不同任务。
- 7>container进程运行状态实时反馈给AM。
- 8>AM反馈任务状态给RM中的ApplictaionManager。
- 9>client端可以连接RM或AM查询job的执行情况。

注： NM启动后去RM上进行注册，会不断发送心跳，说明处于存活状态。
