---
title: 在服务器上搭建V2ray
author: 杨翼臣
date created: 星期二, 2月7日 2023, 4:38:39 下午
date modified: 星期二, 2月7日 2023, 4:39:05 下午
tags: [v2ray 科学上网 云服务器]
aliases: 
---
```bash
chmod +x [install.sh](<http://install.sh/>)
./install.sh local
```

以上代码的意思是：

这串代码包含了两条命令，分别是 **`chmod +x install.sh`** 和 **`./install.sh local`**。

-   **`chmod +x install.sh`** 是用来修改文件权限的命令，其中 **`chmod`** 是一个 Linux 命令，意思是「change mode」（改变文件模式）。**`+x`** 指的是给文件 **`install.sh`** 添加执行权限，这样你就可以在命令行中执行这个文件了。
-   **`./install.sh local`** 是在当前目录执行脚本文件 **`install.sh`** 的命令。**`./`** 表示当前目录，**`install.sh`** 是要执行的脚本文件的文件名，**`local`** 则是传递给脚本的参数。

因此，这串代码的意思是：首先给文件 **`install.sh`** 添加执行权限，然后在当前目录执行该脚本文件，并将 **`local`** 作为参数传递给脚本。