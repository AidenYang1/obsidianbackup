---
title: 建立集群
author: 杨翼臣
date created: 星期五, 4月7日 2023, 4:11:24 下午
date modified: 星期五, 4月7日 2023, 8:06:34 晚上
tags: [docker redis 集群]
aliases: 
---
# 建立集群
关闭防火墙、启动docker启动后台服务
## 新建6个redis容器实例
- 命令
```
```docker run -d --name redis-node-1 --net host --privileged=true -v /data/redis/share/redis-node-1:/data redis:6.0.8 --cluster-enabled yes --appendonly yes --port 6381
```
- 解释
```
```docker run -d --name redis-node-1（实例1的名字） --net host --privileged=true（开启权限） -v /data/redis/share/redis-node-1:/data（容器卷目录映射） redis:6.0.8 --cluster-enabled（开启集群） yes --appendonly yes --port 6381（端口号）
```
![[Pasted image 20230407161919.png]]
在配置第二台和以后的依次改名称和端口号。


## 进入一台容器实例配置东西
（只需要进入一台就行）
修改一下自己的宿主机ip地址，运行此命令
```
redis-cli --cluster create 192.168.111.147:6381 192.168.111.147:6382 192.168.111.147:6383 192.168.111.147:6384
192.168.111.147:6385 192.168.111.147:6386
--cluster-replicas 1
```
![[Pasted image 20230407162541.png]]
确认输入yes

分配成功的表：
![[Pasted image 20230407162809.png]]

完成三主三从的配置。

## 查看集群状态
随便进入一台配置的容器实例，执行命令
`redis -cli -p 6381（容器实例端口）`
- 查看主机哪三台，从机哪三台,哪台挂在哪台上
命令：`cluster nodes`
- 检查集群检查其他命令：
`redis- cli --cluster check 本机ip地址:容器端口（随便一个容器都行，一般用第一个）`

# 哈希值槽位
![[Pasted image 20230407165356.png]]
# 如何数据读取和储存
进入1号机（配置主从时用到的机器）
执行命令：
`redis- cli -p 6381（1号机的端口）`会发现集群建立key值出现问题，
需要执行正确的命令：加参数-c；优化路由
`redis- cli -p 6381 -c`
用集群环境运行；超过此机器的哈希值会跳到其他机器，**命令行也会跳转到其他机器；**

# 主从容错切换迁移
如果一个主服务器宕机，从机必须要能承担起他的职责；
- 如何检测？
docker中杀掉一个主容器；
进入其他容器，打开集群，命令`cluster nodes`
查看之前的slave服务器是否变成了master服务器； 

杀掉的服务器再恢复只能变成从服务器了；不是原来的master了，如果想要恢复原来的主从关系；先停掉站位的原从服务器，等待宕机恢复后的服务上位后再启动站位的从服务器；


# 如何扩容redis集群并重新分配哈希槽
## 新建两个容器并命名为7、8
命令：
```
docker run -d --name redis-node-7 --net host --privileged=true -v /data/redis/share/redis-node-1:/data redis:6.0.8 --cluster-enabled yes --appendonly yes --port 6387
```

## 进入7号容器内部，添加到集群
命令：
```
docker exec -it redis-node-7 /bin/bash
```

- 作为master节点加入原集群
使用命令：

```
redis-cli --cluster add-node 自己的实际ip地址：6387 自己的实际IP地址：6381
```


- 查看是否成功加入
在容器中执行：
`redis- cli --cluster check 本机实际地址：6381`
查看是否多了一条master主机信息；

## 重新分配哈希槽位（是匀出来的）
是之前的已经存在的容器每个人都匀出来的，不是重新分配的；
命令：
```
redis-cli --cluster reshard 本机ip地址：端口号

```

- 提示每个槽位how many slots do you want to move(from 1 to 16384)?
这要最大值16384除master台数；
**(记住：n个人已经平均分的东西想要分给另外一个人再达到所有人平均，之前的每个人都要分出n+1分之1)**
- node id
填写新加入的容器id
![[Pasted image 20230407173559.png]]


## 检查哈希槽位的分配
命令：
```
redis-cli --cluster reshard 本机ip地址：端口号
```

## 挂从服务
```
redis-cli --cluster add-node ip:新slave端口 ip:新master端口 --cluster-slave --cluster-master-id 新主容器节点ID
```

## 再次检测集群状态

```
redis- cli --cluster check 本机实际地址：6381
```


# 如何缩容redis集群并重新分配哈希槽位
## 思路
- 清除一个从节点
- 将清出来的槽号重新分配
- 再次删除主节点
- 达成恢复状态


## 操作
- 用检查集群状态
redis- cli --cluster check 本机实际地址：6381
- 删除从节点，命令：
命令：redis-cli --cluster del-node ip:从机端口 从机6388节点
- 检查集群状态
- 重新分配槽号
	- redis-cli --cluster reshard 本机ip地址：端口号（以第一个作为突破口，对整个集群突破）
	- 大小为要删除的节点槽位
	- 让第一台机器接收
	- 从哪移动，写要删除的节点id
  - 检查集群状态
  - 删除主节点：
	  - redis-cli --cluster del-node ip:从机端口 从机6387节点
