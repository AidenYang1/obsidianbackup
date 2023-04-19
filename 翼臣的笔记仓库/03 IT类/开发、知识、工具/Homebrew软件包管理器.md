---
title: 安装包管理器
author: 杨翼臣
date created: 星期二, 2月7日 2023, 5:26:30 下午
date modified: 星期二, 2月7日 2023, 5:29:49 下午
tags: [homebrew 软件包管理器]
aliases: 
---

# 安装包管理器
通过命令行安装常用开发软件包
# 特性
-   将软件包安装到独立目录，并将其文件软链接。
-   不会将文件安装到它本身目录之外，所以您可将 Homebrew 安装到任意位置。
-   完全基于 Git 和 Ruby，所以自由修改的同时你仍可以轻松撤销你的变更或与上游更新合并。
-   都是简单的 Ruby 脚本
-   使用 gem 来安装 RubyGems、用 brew 来安装那些依赖包。
-   “要安装，请拖动此图标……”不会再出现了。使用 **[Homebrew Cask](https://formulae.brew.sh/cask/)** 安装 macOS 应用程序、字体和插件以及其他非开源软件。
-   通过 Homebrew 下载的软件都来自于官网，绝对放心软件的安全性。

# 解决问题
-   使用时提示安装git和xcode

1.  先输入提示的xcode代码安装xcode
2.  接着再安装git

（clash x pro中复制终端代理命令进终端回车）

-   更新brew：

```powershell
brew upgrade         #更新brew
```

# 清理旧版本包

```powershell
brew cleanup -n  #查看可清理的旧版本包，不执行操作
```

```powershell
brew cleanup  #清理掉所有的包的旧版本
```

```powershell
brew cleanup git  #清理指定包的旧版本
```