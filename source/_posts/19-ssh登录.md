---
layout: title
title: 19-ssh登录
date: 2019-01-28 03:15:21
tags: 大数据Hadoop基础入门到高级精通
categories:
  - hadoop
---
## SSH免密码登录
   + 生成公钥/私钥对
      ssh-keygen -t rsa
   + 拷贝公钥至远程主机或本机authorized_keys文件
      ssh-copy-id <主机名>
  