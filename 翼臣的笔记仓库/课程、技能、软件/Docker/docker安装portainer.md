---
title: 1. 在Docker主机上创建一个名为“portainer_data”的目录，用于保存Portainer的数据：
author: 杨翼臣
date created: 星期五, 3月31日 2023, 5:49:15 下午
date modified: 星期一, 4月3日 2023, 10:35:54 上午
tags: [portainer]
aliases: 
---
# 1. 在Docker主机上创建一个名为“portainer_data”的目录，用于保存Portainer的数据：

```
sudo mkdir /opt/portainer_data

```

我自定义的数据卷

```
sudo mkdir /root/data/portainer_data
```

# 2.拉取并运行

```
sudo docker run -d --name portainer --restart always \
  -p 9000:9000 \
  -v /var/run/docker.sock:/var/run/docker.sock \
  -v /opt/portainer_data:/data \
  portainer/portainer-ce
```

会从Docker Hub拉取Portainer CE镜像并在Docker主机上启动一个名为“portainer”的容器。选项说明如下：

-   `-d`：容器在后台运行
-   `--name portainer`：容器名称为“portainer”
-   `--restart always`：容器将在Docker主机启动时自动重新启动
-   `-p 9000:9000`：将Docker容器的9000端口映射到Docker主机的9000端口
-   `-v /var/run/docker.sock:/var/run/docker.sock`：将Docker主机的Docker套接字（socket）与容器共享，以便Portainer可以管理Docker守护进程
-   `-v /opt/portainer_data:/data`：将Docker主机上的“portainer_data”目录与容器中的“/data”目录共享，以便Portainer可以保存数据
-   `portainer/portainer-ce`：使用Portainer CE镜像创建容器

3.  打开Web浏览器并访问`http://<Docker主机IP地址>:9000`，然后按照屏幕上的说明完成Portainer的设置。完成后，你可以使用Web界面管理Docker主机和其上的容器。

请注意，在此配置中，我们将Portainer的数据保存在Docker主机的“/opt/portainer_data”目录中。如果你希望将数据保存在不同的位置，请相应地更改`-v`选项中的路径。