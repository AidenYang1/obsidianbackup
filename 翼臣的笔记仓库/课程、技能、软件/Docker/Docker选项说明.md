---
title: Docker选项说明
author: 杨翼臣
date created: 星期一, 4月3日 2023, 10:42:53 上午
date modified: 星期一, 4月3日 2023, 10:43:01 上午
tags: [Docker 选项]
aliases: 
---
# 镜像选项说明
- repository： 镜像的仓库源
- tag：镜像的标签版本号
- image id：镜像id
- created：镜像创建时间
- size：镜像大小

同一仓库源可以有多个TAG版木，代表这个仓库源的不同个版木，我们使用 REPOSITORY：TAG 来定义不同的镜像。
如果你不指定一个镜像的版木标签，例如你只使用 ubuntu， docker 将默认使用 ubuntu:latest 的最新镜像

# 镜像搜索选项说明
- official：是否是官方的
- automated：是否是自动构建的
- 