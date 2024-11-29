---
title: 【问题记录】WSL和VMware不兼容解决办法
date: 2024-11-29T06:06:45.602Z
---


原因分析：WSL依赖于hyper-v，而VMware不依赖这个

- CMD管理员模式启动，输入`bcdedit /set hypervisorlaunchtype auto`开启，则可以使用WSL
- CMD管理员模式启动，输入`bcdedit /set hypervisorlaunchtype off`关闭，则可以使用VMware

均需重启电脑

