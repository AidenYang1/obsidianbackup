---
title: 删除容器id
author: 杨翼臣
date created: 星期二, 2月7日 2023, 5:20:45 下午
date modified: 星期二, 3月21日 2023, 3:59:57 下午
tags: [docker 命令]
aliases: 
---
# 汇总表格

|     | 功能                                                 | 命令                                                   |                |
|:--- |:---------------------------------------------------- | ------------------------------------------------------ | -------------- |
|     | 所有帮助                                             | docker help                                            |                |
|     | 创建并启动容器                                       | docker run                                             |                |
|     | 交互式启动容器                                       | [[Docker大笔记#^576f87\|交互式启动]]                   |                |
|     | 列出当前正在运行的容器                               | docker ps                                              |                |
|     | 列出所有容器                                         | docekr ps -a    [[Docker大笔记#^0349b9]]               |                |
|     | 列出本地镜像                                         | docker images                                          |                |
|     | 列出所有镜像                                         | docker images -a                                       |                |
|     | 推送                                                 | docker push                                            |                |
|     | 拉取                                                 |docker pull|                |
|     | 根据dockerfile文件构建镜像                           | docker build                                           |                |
|     | 停止容器运行                                         | docker stop                                            |                |
|     | 删除容器                                             | docker rm                                              |                |
|     | 删除镜像                                             |docker rmi|                |
|     | 删除所有                                             | docker rm -rf /\**                                     |                |
|     | 删除所有镜像                                         | docker rmi -f $(docker images -qa)                     |                |
|     | 强制                                                 | -f                                                     |                |
|     | 查看容器的日志输出                                   | docker logs                                            |                |
|     | 查看容器内部进程                                     | docker top 容器id                                      |                |
|     | 查看容器的详细信息，内部细节                         | docker inspect                                         |                |
|     | 创建一个网络                                         | docker network create                                  |                |
|     | 将容器连接到指定的网络                               | docker network connect                                 |                |
|     | 查看容器端口的映射情况                               | docker port                                            |                |
|     | 停止多个容器的应用                                   | docker-compose down                                    |                |
|     | 根据 docker-compose.yml 构建镜像                     | docker-compose build                                   |                |
|     | 停止多个容器的运行                                   | docker-compose stop                                    |                |
|     | 启动多个容器的运行                                   | docker-compose start                                   |                |
|     | 重启多个容器的运行                                   | docker-compose restart                                 |                |
|     | 查看多个容器的日志输出                               | docker-compose logs                                    |                |
|     | 列出多个容器的状态                                   | docker-compose ps                                      |                |
|     | 在指定服务上运行命令                                 | docker-compose run                                     |                |
|     | 创建一个数据卷                                       | docker volume create                                   |                |
|     | 列出所有数据卷                                       | docker volume ls                                       |                |
|     | 拷贝容器目录到宿主机上                               | docker cp 容器id：容器内要拷贝的目录 宿主机目录        |                |
|     | 删除指定的数据卷                                     | docker volume rm                                       |                |
|     | 初始化一个 Swarm 集群                                | docker swarm init                                      |                |
|     | 将节点加入到一个 Swarm 集群                          | docker swarm join                                      |                |
|     | 在 Swarm 集群上创建一个服务                          | docker service create                                  |                |
|     | 启动docker                                           | systemctl start docker                                 |                |
|     | 停止docker                                           | systemctl stop docker                                  |                |
|     | 重启docker                                           | systemctl restart docker                               |                |
|     | 查看docker状态                                       | systemctl status docker                                |                |
|     |             查看容器状态                                         |  docker stats                                                      |                |
|     | 查看镜像/容器/数据卷所占的空间                       | docker system df                                       |                |
|     |                                                      |                                                        |                |
|     |                                                      |                                                        |                |
|     |                                                      |                                                        |                |
|     | 开机自启动                                           |                                                        |                |
|     | 清理未使用的镜像、容器和卷，并删除任何未使用的数据。 | sudo docker system prune -a                            |                |
|     |                                                      |                                                        |                |
|     |  |                                                        |                |
|     | 搜索镜像                                             | docker search                                          |                |
|     | 限定列出多少项镜像                                   | docker search --limit 数量 镜像名称                    |                |
|     |                                                      |                                                        |                |
|     |                                                      |                                                        |                |
|     |                                                      |                                                        |                |
|     |                                                      |                                                        |                |
|     | 只显示镜像id                                         | docker images -q                                       |                |
|     |                                                      |                                                        |                |
|     |                                                      |                                                        |                |
|     |                                                      |                                                        |                |
|     | 在运行的容器中执行命令                               | docker excc                                            |                |
|     |                                                      |                                                        |                |
|     | **compose类命令**   **compose类命令**                               |**compose类命令**|                |
|     | 查看帮助                                             | docker-compose    -h                                   |                |
|     | 启动所有docker-compose服务                           | docker-compose up                                      |                |
|     | 启动所有docker-compose服务并后台运行                 | docker-compose up -d                                   |                |
|     | 停止并删除容器、网络、卷、镜像                       | docker-compose down                                    |                |
|     | 进入容器实例内部                                     | docker-compose  exec "yml文件里面写的服务id" /bin/bash |                |
|     | 展示当前docker-compose编排过的运行的所有容器         | docker-compose ps                                      |  |
|     | 展示当前docker-compose编排过的容器进程，并非在运行   | docker-compose top                                     |                |
|     | 查看容器输出日志                                     | docker-compose logs yml里写的服务id                    |                |
|     | 检查配置                                             | docker-compose  config                                 |                |
|     | 检查配置，如果有问题就输出内容                       | docker-compose  config -q                              |                |
|     | 重启compose服务                                      | docker-compose  restart                                |                |
|     | 启动compose服务                                      | docker-compose   start                                 |                |
|     | 停止compose服务                                                     | docker-compose stop                                                       |                |


  

# 删除容器id
docker rm -f 容器id

# 显示所有容器id
docker ps -a

# 进入某个容器的目录
docker exec -it **7e8a19150af7**（容器id） /bin/bash
# 查看容器所使用系统镜像版本
#系统版本 cat /etc/os-release

# 如何在docker中安装vim
> 要在 Ubuntu 或 Debian 上安装 Vim，请使用 apt 命令： apt update 
> apt install vim 
> 要在 CentOS 或 Red Hat 上安装它，请使用 Yum 命令： yum install vim 
> 如果是 Alpine Linux，请使用 apk 命令： apk update 
> apk add vim> 
> 要在 Ubuntu 或 Debian 上安装 Vim，请使用 apt 命令： apt update 
> apt install vim 
> 要在 CentOS 或 Red Hat 上安装它，请使用 Yum 命令： yum install vim 
> 如果是 Alpine Linux，请使用 apk 命令： apk update 
add vim

^2bb89e

# 启动容器id
docker start container id

# 重启容器、启动容器、停止容器
```
docker restart container id
docker start container id
docker stop container id
```

