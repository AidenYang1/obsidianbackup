---
title: Docker
author: 杨翼臣
date created: 星期二, 2月7日 2023, 5:21:35 下午
date modified: 星期二, 2月7日 2023, 5:30:27 下午
tags: [docker]
aliases: 
---
Docker为每个应用提供分隔开的运行环境，不同环境之间互不影响 ，在docker中称为Container容器。

### 目录

[docker命令](https://www.notion.so/docker-f01f5ee4fd334682ad07daf6a3b21223)

# Docker

-   Image镜像：虚拟机的快照，包含部署的应用程序和所有库软件

Docker可以在装载镜像后，可以从镜像中拿出所需工具给每个软件封装环境。

-   Dockerfile：Docker的自动化脚本

# Vs code有Docker的拓展插件

# 用Docker部署应用

## 创建Docker自动化脚本

-   FROM 导入镜像名称。（用标签设置）
-   WORKDIR：镜像导入之后其他的所有文件工作路径
-   COPY：导入文件
-   RUN：创建镜像时运行特定的命令（创建镜像时使用）
-   CMD：可以指定当Docker容器运行以后需要执行的命令（运行容器时使用）

## 使用

-   创建容器：

```powershell
Docker build -t 名字 .(句号不能省略，指在当前目录下寻找dockerfile)
```

-   启动容器：

```powershell
docker run -p
```

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/654557b1-5c65-4c6c-823b-931169dbd3f0/Untitled.png)

-   p：将容器中的某个端口映射到我自己的主机上，实现从主机上访问容器中的Web应用

前面的80是本地主机端口，后面是容器端口。

-   d： 让容器在后台运行，容器的输出不会直接显示在控制台。

**（详细信息可以下载Docker桌面端应用）**

# 删除时保留容器中的数据

需要创建数据卷

# Docker compose

-   创建docker-compose.yml文件：定义多个container

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/83c90a25-6772-469c-96ce-0b88cbba9085/Untitled.png)

-   可以创建一个数据卷，永久存放数据

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/27f3e7e2-e6ec-48eb-b913-456d19f04d85/Untitled.png)

```powershell
Docker compose up    （-d后台运行）运行所有容器
```

```powershell
Docker compose down （停止并删除所有创建的容器，数据卷需要手动删除。）
```

以上都可以在图形化界面操作。

# 服务器重启后Docker进程挂掉

执行

```powershell
systemctl daemon-reload
```

```powershell
systemctl restart docker.service
```

# Docker中我遇到的问题及解决办法

## 把自己的镜像推送到远程dockerhub报错：denied: requested access to the resource is denied

> Docker发布镜像时报错denied: requested access to the resource is denied解决办法

> docker tag  docker_name  aaaa/docker_name

重命名镜像tag后推送

> docker push aaaa/docker_name

## docker启动容器之后马上又自动关闭

[blog.csdn.net](https://blog.csdn.net/fengqing5578/article/details/94554897)

> docker启动容器之后马上又自动关闭

> docker run -dit centos /bin/bash 添加-it 参数交互运行 添加-d 参数后台运行

## 在docker中安装vim

# 怎样在 Docker 容器中安装 Vim

[bynss.com](https://bynss.com/linux/758448.html)

> docker exec -it container_name_or_ID sh

进入目录

> 验证它使用哪个 Linux 发行版： cat /etc/os-release

> 要在 Ubuntu 或 Debian 上安装 Vim，请使用 apt 命令： apt update apt install vim 要在 CentOS 或 Red Hat 上安装它，请使用 Yum 命令： yum install vim 如果是 Alpine Linux，请使用 apk 命令： apk update apk add vim