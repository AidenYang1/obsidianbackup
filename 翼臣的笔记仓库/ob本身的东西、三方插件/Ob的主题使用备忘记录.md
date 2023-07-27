## 一、使用Anu主题的配置
>来源于bilibili的视频（忘记请参考cubox收藏夹的内容）

### 1、仓库Github地址
	https://github.com/AnubisNekhet/AnuPpuccin

### 2、插件安装
- style settings：修改主题的设置(必须安装)
- BRAt（是用来在主题没有上架官方商城的时候，从github中拉取主题文件用的）
- Mysnippets（可选的）：更方便的管理CSS片段

### 3、安装步骤
1. https://jsd.cdn.zzko.cn/gh/AnubisNekhet/AnuPpuccin@main/theme.css
2. 下载上面的theme.css文件保存到Ob目录下的/.obsidian/themes/文件夹下载  (如果已经在应用商店中安装了官方的主题，无需执行上一步)
3. 额外配色的安装：下载仓库文件的sinippets/extend-color.css文件
4. 下载其他CSS片段https://youthful-humidity-ec0.notion.site/Ob-2-0-4bda0b48053745529b1e373cf7694cb2
5. 将上述总共4个CSS文件放在下图所示的文件夹中![[Pasted image 20230205224445.png]]即，snippets文件夹。重新加载软件即可。

	### 4、针对已经放进去的css的文件修改轻主题风格，需要前往
	![[Pasted image 20230205224852.png]]进行修改。

### 4、如何更改白天和夜晚模式主题？
前往
![[Pasted image 20230205230007.png]]stylesetting插件中选择themes extened；
- light theme flavor 为浅色模式下的主题样式。
- Dark theme flavor 为深色模式下的主题样式。

### 5、如何让缩进在代码块禁用？
将首行缩进的css代码修改（代码放在了外观、最下部分的sinppets文件夹）
> 首行缩进 css 前四行改成：
> .markdown-source-view.mod-cm6 div.cm-line:not(.HyperMD-header, .hr, .HyperMD-codeblock),
> .markdown-source-view.mod-cm6.indent div.cm-line:not(.HyperMD-header, .hr, .HyperMD-codeblock) {
>   text-indent: 2em;
> }