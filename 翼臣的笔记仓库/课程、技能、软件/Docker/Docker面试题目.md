---
title: 什么是docker的虚悬镜像？
author: 杨翼臣
date created: 星期一, 4月3日 2023, 11:10:49 上午
date modified: 星期一, 4月3日 2023, 4:33:27 下午
tags: [docker 面试题目]
aliases: 
---
# 1~2亿条数据需要缓存，请问如何设计这个存储案例？
答：单机单台100%不可能，肯定需要用到的是分布式存储，那么用redis如何落地？
- 哈希取余分区
![[Pasted image 20230407154832.png|]]
缺点：扩容的时候不方便![[Pasted image 20230407154913.png]]
- 一致性哈希算法分区
	- 提出背景：1997年由麻省理工学院提出，设计目标是为了解决分布式缓存数据变动和映射问题，比如某个机器宕机，或者分母的数量改变了，自然取余数的办法就不行了。
	- ![[Pasted image 20230407155755.png]]
	- ![[Pasted image 20230407155836.png]]
	- ![[Pasted image 20230407155901.png]]
	- ![[Pasted image 20230407160025.png]]
	- ![[Pasted image 20230407160039.png]]
	- ![[Pasted image 20230407160226.png]]
	- 缺点：hash环会出现数据倾斜问题
		- ![[Pasted image 20230407160319.png]]
-  哈希槽分区
![[Pasted image 20230407160629.png]]
![[Pasted image 20230407160653.png]]
![[Pasted image 20230407160806.png]]
![[Pasted image 20230407160832.png]]
![[Pasted image 20230407160921.png]]



# 为什么docker的centos只需要200多MB？
对于一个精简的os，rootfs可以很小，只需要包括最基本的命令、工具和程序库即可。因为底层的直接用宿主机的通用linux kernel就行了，自己只需要提供rootfs就行了，对于不同的linux发行版本，bootfs基本是一致的，rootfs会有差别。公用bootfs就行了。
# 什么是docker的虚悬镜像？
仓库名、标签都是<none>的镜像叫做虚悬镜像，构建无效的镜像。dangling images


