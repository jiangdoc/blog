---
layout: post
title: "VirtualBox桥接模式下虚拟机联网"
subtitile: "Virtual machine networking in bridging mode."
date: 2018-12-20 11:00:00
author: "乱码人生"
header-style: text
tags:
     - VirtualBox
     - 网络
     - 虚拟机
---
### VirtualBox桥接模式下虚拟机联网

1. 首先打开虚拟机，选择虚拟系统，右击设置网络，注意“连接方式：桥接网卡，界面名称：选择自己物理机的网卡”
    ![在这里插入图片描述](https://jiangdoc.github.io/blog/img/in-post/2018-12-21-VirtualBox_bridgepattern_networking/1.png)
    ![在这里插入图片描述](https://jiangdoc.github.io/blog/img/in-post/2018-12-21-VirtualBox_bridgepattern_networking/2.png)


2. 配置Linux网络设置。

首先查看物理机的IP地址：window+R 输入 cmd
>ipconfig/all

![在这里插入图片描述](https://jiangdoc.github.io/blog/img/in-post/2018-12-21-VirtualBox_bridgepattern_networking/3.png)

然后配置Linux网络：

>vi /etc/sysconfig/network-scripts/ifcfg-eth0

    ONBOOT=yes  //启动时是否激活网卡
    BOOTPROTO=dhcp //设置成dhcp[动态获取IP]，static[设置静态IP]，
    #动态IP不用添加下面的
    IPADDR=192.168.1.190 //确定在同一网段上，且IP未被占用
    GATEWAY=192.168.1.1 //上面记住的网关
    NETMASK=255.255.255.0 //上面记住的子网掩码
    DNS1=192.168.1.1 //上面的DNS(都要配置)

编辑完：shift+:  ,录入[wq!]保存退出。

然后就是重启网卡：

>service network restart 或者 #systemctl restart network (centos7)

然后查看Linux当前启网卡信息：
>ifconfig -a 

最后就是查看是否能联网:

>ping www.baidu.com 