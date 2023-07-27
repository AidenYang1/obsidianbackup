---
author: 杨翼臣
date created: 星期四, 6月8日 2023, 2:38:35 下午
date modified: 星期四, 6月8日 2023, 10:53:56 晚上
tags: [mysql]
aliases: 
---

# 停止服务
sudo service mysql stop

# 重启服务
service mysqld restart
# 跳过权限进入
sudo mysqld_safe --skip-grant-tables &

# 使用root用户登录
mysql -u root

# 使用默认库
use mysql;

# 修改密码
 UPDATE user SET Password= Password ('密码') WHERE user='root';     # 将密码修改为root

# 刷新权限
flush privileges;

# 重启
service mysqld restart

# 登录
mysql -u root -p