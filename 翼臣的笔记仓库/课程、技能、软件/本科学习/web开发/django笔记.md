---
title: 安装
author: 杨翼臣
date created: 星期一, 4月17日 2023, 11:44:23 中午
date modified: 星期一, 4月17日 2023, 11:46:15 中午
tags: [django]
aliases: 
---

# 安装
```python
pip install django 
```

# 配置
## 新建项目
```
django-admin startapp 新的项目名称
```

## 配置项目
> django 的新版本已经默认支持 测试框架，无需显式声明。

要使用Django创建一个新项目，需要按照以下步骤操作：
在项目文件夹中
输入以下命令来创建一个新的Django项目：
```
  django-admin startproject projectname
```

   ```
3. 启动
   ```
   cd projectname
   python manage.py runserver
   ```
   默认地址：localhost:8000


现在，你已经成功创建了一个新的Django项目。你可以开始在项目中添加应用程序并开发你的应用程序了。
