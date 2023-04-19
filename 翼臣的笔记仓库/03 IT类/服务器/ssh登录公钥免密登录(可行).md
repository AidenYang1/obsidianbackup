---
title: ssh登录公钥免密登录
author: 杨翼臣
date created: 星期一, 3月20日 2023, 11:03:28 上午
date modified: 星期五, 3月31日 2023, 5:35:49 下午
tags: [ssh 免密登录]
aliases: 
---
##   本地机如果没有生成秘钥需要先生成
1. 打开终端或命令提示符。

输入命令：ssh-keygen -t rsa
2. 按Enter键。

1. 如果您希望在生成密钥对时使用特定的文件名和/或密码，请按照提示操作。
2. **如果不需要，请直接按Enter键。**
**生成完毕**
## 进入目录获取公钥
cd ~
cd .ssh/
5. 完成后，您将在主目录中找到.ssh文件夹，并在其中找到id_rsa和id_rsa.pub文件。id_rsa是您的私钥，而id_rsa.pub是您的公钥。

## 公钥添加到远程服务器的authorized_keys文件中
   
1. 打开.ssh文件夹，复制公钥id_rsa.pub的文本内容到本地剪贴板中。
   （将“USERNAME”替换为远程服务器的用户名。）
   
2. 登录到远程服务器。使用以下命令：
`   ssh username@remote_server`
(如果之前已经登录过存在hostknown文件需要删除本地机器hostknown文件里保存的远程服务器的host文本)
   - 将“username”替换为您的用户名，
   - “remote_server”替换为远程服务器的IP地址或主机名。
 
3. 创建ssh目录和authorized_keys文件（如果尚不存在）。您可以使用以下命令：
   mkdir -p ~/.ssh
   创建文件
   touch ~/.ssh/authorized_keys
   
4. 打开authorized_keys文件并将公钥粘贴到其中。您可以使用以下命令：
   nano ~/.ssh/authorized_keys或者使用vim
   将公钥粘贴到文件中。

5. 保存并关闭文件。

  
## 现在，您可以使用SSH密钥对登录到远程服务器而无需输入密码。
ssh username@remote_server`