---
title: Port
author: 杨翼臣
date created: 星期二, 2月7日 2023, 4:49:34 下午
date modified: 星期二, 2月7日 2023, 4:49:57 下午
tags: []
aliases: 
---
**Clash的配置文件是个文件，包含了所有节点内容和策略和规则。**
**支持托管更新，定时从托管服务器下新的配置文件。**

![[Pasted image 20230207165154.png]]
# Port

http代理端口

# Socks-port

Sock5的连接端口：如电报或者其他客户端需要

# Redir-port


# Allow-lan

是否允许局域网的其他设备连接过来

# Mode

模式：全局还是代理还是直连

# Log-level

日志的等级

# external-controller

提供resfor接口

# Proxies/blu

所有的节点数据信息

# Secret

密匙

## type类型

vmess等

需要添加的话为：-{

# Proxy groups

策略组、过滤网

-   为新的一组

![[Pasted image 20230207165513.png]]

![[Pasted image 20230207165531.png]]

## Type

**Url-test：**进行ping延迟的测试

**url：**测试地址

**interval：**间隔多少秒测一次



# proxies

设置为-DIRECT直接链接



-   REJECT为拒绝访问，如广告。

# Rules规则
## 规则前缀有这些内容
-   DOMAIN-SUFFIX 表示包含什么后缀的域名，走什么组

![[Pasted image 20230207165602.png]]
-   IP-CIDR IPV4匹配
-   IP-CIDR6 IPV6匹配
-   DOMAIN-KEYWORD,xxx 表示包含 xxx域名关键字的链接

![[Pasted image 20230207165622.png]]
-   DOMAIN [abc.hello.com](http://abc.hello.com) 表示包含完整的域名
-   PROCESS-NAME 表示进程名称(常用)
-   GEOIP 数据库（国家代码）匹配，ip库
-   MATCH 全匹配（一般放在最后）

# 如何查看一个网页中请求了哪些URL（统一资源定位符）？

在浏览器打开开发者模式，选择网络查看。