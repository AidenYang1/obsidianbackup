# 一、安装

## 1、安装所需要的软件包：

-   utils

```bash
yum install -y yum-utils
```

## 2、安装稳定的仓库

阿里云镜像仓库（无科学上网环境）

官网（有科学上网）

## 3、更新yum软件包的索引(可选项)

```bash
yum makecache fast
```

## 4、安装Docker引擎

```bash
yum -y install docker-ce docker-ce-cli containerd.io        #运行安装docker CE
```

# 二、启动Docker

启动代码

```bash
systemctl start docker    #运行启动docker
```

### 可选项

```bash
docker version #查看docker的版本
```

# 三、Docker 的卸载

```bash
systemctl stop docker
yum remove docker-ce docker-ce-cli containerd.io
rm -rf /varllib/docker
rm -rf /varllib/containerd

#以上卸载基于centos ，其他系统请使用对应的包管理工具命令
```