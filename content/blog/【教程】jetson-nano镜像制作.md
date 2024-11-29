---
title: 【教程】jetson nano镜像制作
date: 2024-11-29T06:21:47.013Z
---

## 查看SD卡分区
```
sudo fdisk -l
```
## 制作镜像并压缩
```
sudo dd if=/dev/mmcblk0 conv=sync,noerror bs=200M | gzip -c > ~/backup_image.img.gz
```
## 查看进度
新建终端，输入：
```
sudo pkill -USR1 -n -x dd
```

