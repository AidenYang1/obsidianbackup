---
title: docker安装docker-compose
author: 杨翼臣
date created: 星期五, 3月31日 2023, 5:54:24 下午
date modified: 星期五, 3月31日 2023, 5:54:25 下午
tags: [docker docker-compose]
aliases: 
---

# debian 上安装
## 1、打开终端并使用以下命令下载 Docker Compose 二进制文

```
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose

```
上述命令将下载 Docker Compose 1.29.2 版本的二进制文件。如果您需要安装其他版本，请将 URL 中的版本号替换为您需要安装的版本号。

## 2、授予二进制文件执行权限

```
sudo chmod +x /usr/local/bin/docker-compose

```

## 3、验证是否成功

```
docker-compose --version
```

