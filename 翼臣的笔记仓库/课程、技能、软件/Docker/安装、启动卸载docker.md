# 一、安装

[[4、docker 平台图解，安装docker（完整）#^5e4507]]
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