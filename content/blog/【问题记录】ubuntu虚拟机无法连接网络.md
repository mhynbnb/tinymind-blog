---
title: 【问题记录】Ubuntu虚拟机无法连接网络
date: 2024-11-29T06:29:46.498Z
---

### 问题分析：
ifconfig -a查看时，可以找到lo网卡，也可以找到ens33网卡，说明ens33网卡状态异常。这种情况出现一般是在上次正常使用可以上网，之后挂起或关机后再重启系统出现，初步判定与网卡状态文件记录有关 。
### 解决方案1：
停止网络服务：
```
service network-manager stop
```
删除设备网卡状态管理文件：
```
sudo rm -rf /var/lib/NetworkManager/NetworkManager.state 
```
重新启动网络服务：
```
service network-manager start
```
### 解决方案2：
    sudo dhclient ens33
	sudo ifconfig ens33

