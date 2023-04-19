
---
title: 如何用令牌访问自己的文件，生成文件本身的链接？
author: 杨翼臣
date created: 星期五, 2月24日 2023, 4:06:59 下午
date modified: 星期五, 2月24日 2023, 4:09:51 下午
tags: [gitlab]
aliases: 
---
# 如何用令牌访问自己的文件，生成文件本身的链接？
#文件链接 #访问文件的链接
-   自己用私密访问令牌获取文件链接

(https://gitlab.com/api/v4/projects/41240066/repository/files/data%2Fclash%2Ftest.yaml/raw?ref=main&private_token=glpat-AzUd4ELf2ZAK_hS9A32d)
我的令牌：
glpat-sW-gTSPp3v3tk_3hNVjx
-   模板

[](https://gitlab.com/api/v4/projects/%E4%BB%93%E5%BA%93ID/repository/files/%E6%96%87%E4%BB%B6%E8%B7%AF%E5%BE%84/raw?ref=main&private_token=%E4%BB%A4%E7%89%8C)[https://gitlab.com/api/v4/projects/仓库ID/repository/files/文件路径/raw?ref=main&private_token=令牌](https://gitlab.com/api/v4/projects/%E4%BB%93%E5%BA%93ID/repository/files/%E6%96%87%E4%BB%B6%E8%B7%AF%E5%BE%84/raw?ref=main&private_token=%E4%BB%A4%E7%89%8C)
 **（文件路径的/要变为转译符号%2F）**
