---
layout: title
title: 17-ntp服务器同步时间
date: 2019-01-28 02:44:16
tags: 大数据Hadoop基础入门到高级精通
categories:
  - hadoop
---
## 17-ntp服务器同步时间
## 分布式环境(distributed)
  + ntp服务器同步时间
    - 1> 作用  同步三个服务器的时间，让服务器一致
    - 2> 机器1上配置ntp时间服务器
     ```
     vim /etc/sysconfig/ntpd
        SYNC_HWCLOCK=yes
     vim /etc/ntp.conf
        #server xxx
        server 127.127.1.0
        fudge  127.127.1.0 stratum 10
        restrict 192.168.160.0 xxxx
     ```  
     - 3> 机器1重启ntp服务器
         service ntpd restart
     - 4> 机器1设置时间
          date -s yyyy-MM-dd
          date -s HH:mm:ss
     - 5>机器2/3 同步时间
     手工同步：
        /usr/sbin/ntpdate <主机名>
     定时同步：
        crontab -e :0-59/10****/usr/sbin/ntpdate <主机名> 
        
        注： crontab格式： 分 小时 天 月 周 <command>


    
    
    /etc/sysconfig/ntpd文件添加SYNC_HWCLOCK = yes
    /etc/ntp.conf 文件配置
    取消注释：
    //修改为统一网段
    ```
        restrict 192.168.139.0 mask 255.255.255.0 nomodify notrap
        server 127.127.1.0   #local clock
        fudge  127.127.1.0 stratum 10
    ```