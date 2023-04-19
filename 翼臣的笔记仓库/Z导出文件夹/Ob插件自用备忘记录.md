---
author: 杨翼臣
date created: "星期六, 2月4日 2023, 8:46:11 晚上"
date modified: "星期一, 2月6日 2023, 11:46:45 晚上"
tags:
- ob插件
title: Ob 插件自用备忘记录
---

- pangu:在输入中英文时，自动为中英文字符添加空格。

- outliner：自动排序，适用于列表编辑。

- drawio（Diagrams）：图标编辑、画图 ，需要自己新建图。  

- booknote：支持 pdf 文档的编辑和书写，不支持 epub

- webbrowser：ob 访问网页

- various complements：自定义词典补全

- quick explore:快捷资源管理器，位于菜单栏的最上部分

- quiet outline：带有搜索功能的 ob 原插件补充插件

- recent files :快捷打开最近文件

- emoji toolbar：在 ob 中快速插入表情

  - <font color="#ffc000">注意事项：</font>
    <font color="#ffc000">在使用 emoji toolbar 时，前往 ob 设置的快捷键设置搜索 emoji，在 emoji toolbar open emoji picker 设置打开表情栏的快捷键。</font>

- search Assistant：ob 的核心搜索插件，可以再搜索时显示有关内容的笔记的大视图。该插件没有命令代码和设置界面，是嵌入 ob 的搜索功能的。

- Meld encrypt：这个插件可以创建加密文件，该文件只能输入纯文本，不是 md 文件的格式。如果想要加密某个笔记的单行内容，可以使用双%使用。
  加密和解密的方法都是通过命令行输入 cry 搜索就行。

- omnisearch 插件：不需要额外的设置。需要添加搜索的文件类型请前往 omnisearch 的设置中添加全方位智能搜索。若要使用中文分词，需要前往 omnisearch 的代码仓库中下载额外支持的中文分词。

- 哔哩哔哩播放的插件：bilibili 插件，另外还要安装 Media 和 media

- 弹窗编辑器：Hover Editor

- 一键生成各种图表：charts 插件

- 生成折线图、柱状图：excalidraw

- 可视化表格创建：table enhance

- advanced tables：表格插件，用竖线创建表格。可在阅读模式下编辑

- buttons：在 ob 中创建自定义按钮功能。

- pandoc：将该页笔记导出为各类型的文档，word 等等。

- excalidraw：可以自由绘图。

- weread：导入和同步微信读书里面的笔记。

- 实现网盘同步：
  1. 使用同步云盘将整个 ob 的文件夹同步（需要包含隐藏文件夹）
  2. 使用插件同步。如 remotely save。

- dateview:数据视图插件。

- mindmap：将笔记中的标题和列表都生成思维导图。

- templater：模板，用模板创建新页面。

- pdf 的文档标注 annotator：文档标注后自动保存 md 文件（一般不用这个插件）

- heading shifter 插件：批量改装标题的级别

- Remember cursor position：记住光标的位置，在下次打开该笔记文件时恢复光标所在位置。

- yaml 格式的自动配置和更新：使用 linter
  可以自动更新笔记的修改时间，动态的。可以匹配更多关键词，对缺少的主键进行添加的同时不会修改属性值。

- 使用paste image rename插件：快速对插入的附件进行重命名
  \> - 不仅对图片有效，对附件同样有效 \^7ed8b3

- 使用note rafactor拆分同级标题为子页面。

- 
