---
title: docker daemon 
author: 杨翼臣
date created: 星期二, 3月28日 2023, 9:33:28 晚上
date modified: 星期五, 5月5日 2023, 12:13:04 凌晨
tags: [docker 教程]
aliases: 
---
# docker daemon 
是docker的后台守护进程。是核心组件。负责管理镜像、容器、网络和存储等资源。
- docker的运行必须要保持daemon在后台运行，否则docker无法正常工作。

![[IMG_0085.jpeg|600]]


# 架构
是一个C/S模式的架构，后端是一个松耦合架构。众多模块配合。
>[!note] c/s（client-server）模式：
>客户端/服务器模式，客户端和服务器分别作为独立的进程运行在不同的计算机上，通过网络通信进行数据交换。客户端发送请求到服务器，服务器处理请求的模式，可以实现双向通信。


> [!note] 松耦合架构：
> 设计模式，目的在与降低系统的各个组件或模块之间的耦合度，能够提高系统的灵活性和可扩展性和可维护性。（就是每个组件和模块之间没有那么强的互相必要性依赖关系要尽可能少）


# 安装

^5e4507

## debain
1.  首先，更新Debian软件包列表：

```bash
sudo apt-get update
```

2.  安装Docker依赖的软件包：

```bash
sudo apt-get install apt-transport-https ca-certificates curl gnupg2 software-properties-common
```

3.  添加Docker官方GPG密钥：

```bash
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -
```
4.  添加Docker官方软件源：

```bash
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian $(lsb_release -cs) stable"
```

5.  再次更新软件包列表：

```bash
sudo apt-get update
```

6.  最后，安装Docker：

```bash
sudo apt-get install docker-ce
```

7.  验证Docker是否正确安装：

```bash
sudo docker run hello-world
```

## cent os
以下是在CentOS上安装Docker的步骤：
1. 更新软件包列表：
   ```

   sudo yum update

   ```
2. 安装Docker依赖库：
   ```

   sudo yum install -y yum-utils device-mapper-persistent-data lvm2

   ```
1. 添加Docker的YUM仓库：
(**如有需要，将此处的代码换成国内阿里云的**`yum-config-manager --add -repo http://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo`)
   ``` ^acacc7

   sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo

   ```
4. 安装最新版本的Docker：
   ```

   sudo yum install docker-ce docker-ce-cli containerd.io

   ```
5. 启动Docker服务：
   ```

   sudo systemctl start docker

   ```
6. 验证Docker是否正确安装：
   ```

   sudo docker run hello-world

   ```
   如果输出 "Hello from Docker!"，则表明Docker已成功安装。

注意：在安装Docker之前，请确保您的系统满足Docker的最低要求。例如，Docker需要64位的CentOS 7或更高版本。

## ubuntu
以下是在Ubuntu上安装Docker的步骤：
1. 更新软件包列表：
   ```bash
   sudo apt-get update
   ```
2. 安装Docker的依赖库：
   ```bash
   sudo apt-get install -y apt-transport-https ca-certificates curl gnupg-agent software-properties-common

   ```
3. 添加Docker的GPG密钥：[[4、docker 平台图解#^1b54df|为什么多了这一步骤？]]
   ```bash

   curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

   ```
1. 添加Docker的APT仓库：**如有需要，换成阿里云镜像仓库。** [[4、docker 平台图解，安装docker（完整）#^acacc7|阿里云镜像]]
   ```bash

   sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"

   ```
5. 再次更新软件包列表：
   ```bash
   sudo apt-get update
   ```
6. 安装最新版本的Docker：
   ```bash
   sudo apt-get install docker-ce docker-ce-cli containerd.io
   ```
7. 启动Docker服务：
   ```

   sudo systemctl start docker

   ```
8. 验证Docker是否正确安装：
   ```

   sudo docker run hello-world

   ```
   如果输出 "Hello from Docker!"，则表明Docker已成功安装。

  
注意：在安装Docker之前，请确保您的系统满足Docker的最低要求。例如，Docker需要64位的Ubuntu 18.04或更高版本。


## 为什么需要添加gpg秘钥？
^1b54df
添加Docker的GPG密钥是为了**确保从Docker官方仓库下载的软件包是经过官方签名的**，以确保软件包的完整性和安全性。GPG密钥是一种安全机制，用于验证软件包的身份和完整性。在添加Docker的APT仓库之前，需要先添加它们的GPG密钥。
GPG密钥是一种公钥加密系统，它使用一对密钥：公钥和私钥。私钥只有所有者可以访问，用于对数据进行加密和签名。公钥可以向任何人公开，用于对数据进行解密和验证签名。在安装Docker之前，需要添加Docker官方GPG密钥以确保下载的软件包是经过官方签名的。

## 为什么centos安装时不需要添加gpg秘钥？
在CentOS安装Docker时，添加Docker的GPG密钥步骤不是必需的。这是因为在添加Docker的YUM仓库时，已经包含了GPG密钥信息。在安装Docker之前，您可以使用以下命令验证Docker的GPG密钥是否正确安装：
```

sudo rpm --import https://download.docker.com/linux/centos/gpg

```

  

如果这个命令没有任何输出，则表明Docker的GPG密钥已正确安装。
## 其他步骤参考官网

## 检查是否安装成功
docker两端安装成功`docker version`显示服务端和客户端的版本

# docker的卸载
- systemctl stop docker 
- yum remove docker-ce docker-ce-cli containerd.io
- rm -rf/var/lib/docker
- rm -rf/var/lib/containerd



# 阿里云容器镜像加速服务（相当于挂了个镜像拉取下载的vpn）
阿里云官网的容器镜像服务里面有一个镜像工具；在镜像工具中可以得到自己的加速器地址。按照介绍进行操作。

## 最好自备梯子，方便的话


# 理解镜像拉取的规则
![[Pasted image 20230328223311.png|600]]
