# 虚拟机环境准备

## xshell 连接 centos7（初始机）

1. 修改 vi /etc/sysconfig/network-scripts/ifcfg-ens33 网卡

   ```
   [zxt@localhost ~]$ su
   [zxt@localhost ~]# vi /etc/sysconfig/network-scripts/ifcfg-ens33
   ...
   ONBOOT=no => yes
   [zxt@localhost ~]# reboot
   ```

2. 查看 ip 地址

   ```
   [zxt@localhost ~]$ ip addr
   ```

3. Unit iptables.service could not be found 解决方法

   CentOS 7 默认没有 iptables 文件，使用 yum 安装

   + 更新 yum 源

     https://blog.csdn.net/zytbft/article/details/81166345

   + 安装 iptables

     ```
     yum install iptables-services
     ```

## 虚拟机准备

1. 关闭防火墙

   ```
   [zxt@localhost ~]# service iptables stop
   [zxt@localhost ~]# chkconfig iptables off
   ```

2. 创建一般用户

   ```
   [zxt@localhost ~]# useradd atguigu
   [zxt@localhost ~]# passwd atguigu
   ```

   

