---
title: cookie
author: 杨翼臣
date created: 星期四, 2月23日 2023, 1:34:58 下午
date modified: 星期四, 2月23日 2023, 2:26:29 下午
tags: [cookie session token]
aliases: 
---
# cookie
（存储在浏览器的数据而已。）
http是无状态的，
浏览器在每次请求中时加入用户名和密码。（即实现每次HTTP请求都自动带数据给服务器的技术）
浏览器发起http请求后，服务器会进行set-cookie的设置。
set-cookie的值：
- name
- Value

## 缺点
打开浏览器是能够看到保存了哪些cookie的。

# session
利用浏览器和服务器之间的会话存储用户登录状态 。
不同的网站对每个用户的会话都设定了一定的时间（会话结束的时间）和唯一的session id。
- 发送请求
- 确认请求是否正确
- 创建session id和会话时间。
- 将session id 和会话时间发送给浏览器。将session id 也加入到cookie中。服务器同时也会给session id 签名。
- 用户下次登录时浏览器发送含有session id 的cookie给服务器。
- cookie有效期结束后服务器会删除缓存，用户就需要重新输入用户名和密码了 

## 不足点
服务器如果负载过大就需要把用户的session id 分享给其他服务器，很麻烦。

# token（Json Web Token）
登录网页后利用token的服务器会生成一个JWT，将JWT发送给浏览器，可以让浏览器以Cookie或 者Storage的形式进行存储，假设以cookie的形式保存下来，这样用户每次发送请求都会把这个JWT发给服务器，和session类似，只是token存储在用户那边。
 
JWT由三部分组成：
- header：算法
- payload：有效的数据
- signature：签名信息




**cookie是数据载体；token是令牌，把服务器产生的数据存储在用户设备里。将存有这个信息的内容发送给服务器，服务器验证；（持久性、本地性）session是存储在服务器中的，服务器给登录的用户创建session id 和会话时间存储在浏览器中的cookie中，用户再次访问只需要继续会话就行。（限时性、远程性）**

