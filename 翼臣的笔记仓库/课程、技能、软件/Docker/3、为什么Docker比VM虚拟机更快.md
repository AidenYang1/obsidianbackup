---
title: 3、为什么Docker比VM虚拟机更快
author: 杨翼臣
date created: 星期二, 2月7日 2023, 5:19:17 下午
date modified: 星期二, 3月28日 2023, 9:27:39 晚上
tags: [docker]
aliases: 
---
![[Pasted image 20230207172006.png]]

镜像时静态定义，容器是镜像运行时的实体。

# 为什么docker比VM虚拟机更快？
1. docker的抽象层比虚拟机少
2. docker利用的是宿主机内核，不需要加载操作系统的os内核。
意思是，不用每次建立镜像都去重新建立一个内核，而是直接用宿主机上的内核新建容器。
