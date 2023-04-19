---
title: 标题
author: 杨翼臣
date created: 星期三, 2月8日 2023, 9:33:06 晚上
date modified: 星期三, 4月12日 2023, 2:44:51 下午
tags: []
aliases: 
---
title: 标题
author: 杨翼臣
date created: 星期三, 2月8日 2023, 9:33:06 晚上
date modified: 星期三, 3月8日 2023, 6:06:55 晚上
tags: [markdown 语法]
aliases: 
---
# 标题
\ # 表示一级标题
\ ## 二级标题
\ ### 三级标题
······
以此类推，直到<font color="#ffc000">六级标</font>题。
# 斜体
![[nzfKtEkDzyIkywWQ-1096c90d-8fba-89fd-83b8-28b985cdadf7.png|300]]
# 粗体
![[nzfKtEkDzyIkywWQ-d4469e07-2d28-524f-6e97-41de6288837a.png|400]]

# 粗斜体
![[nzfKtEkDzyIkywWQ-81186572-86d5-3721-260e-2e171bb4f4d4.png|350]]

# 斜体中包含粗体
![[nzfKtEkDzyIkywWQ-f575d837-c53c-d9a2-7516-293deee48ed8.png|600]]
5

# 粗体中包含斜体
![[nzfKtEkDzyIkywWQ-715c1dcf-321d-7f0f-50bb-f9f10b610121.png|600]]
5

# 水平的分割线
![[nzfKtEkDzyIkywWQ-f1229a34-1d7e-fead-6ea6-2c4527ce8c13.png|350]]
6

# 文本删除线
![[nzfKtEkDzyIkywWQ-b43c79c7-91cd-9118-44dc-1c04e2ff4356.png|400]]
\ ~~ 文本 ~~

# 文本下划线
\ <> 文本 <>

# 列表
## 有序列表
\ 1. 空格 文本内容
> 如果需要在一个序号列表中换行显示内容，按住 shift+enter

更多：[4.1 有序列表](obsidian://bookmaster?type=open-book&bid=nzfKtEkDzyIkywWQ&aid=1d3d1de7-f000-ee3d-b4d4-2c2668f17bb2&page=7)

## 无序列表
\ - 空格 文本
更多：[4.2 无序列表](obsidian://bookmaster?type=open-book&bid=nzfKtEkDzyIkywWQ&aid=39f38fb7-2b68-ae7c-140f-fedd557e140e&page=8)

# 引用
\ > 文本（不需要空格）

[4.3 引用](obsidian://bookmaster?type=open-book&bid=nzfKtEkDzyIkywWQ&aid=34ed5b56-11e1-192d-ae40-3b2bcb9938a2&page=9)
9

# 缩进
tab
# 退格
shift+tab

# 列表的缩退格
[4.4.3 引用的缩&退](obsidian://bookmaster?type=open-book&bid=nzfKtEkDzyIkywWQ&aid=52dc510c-7c48-397d-fc33-55ffea9124d8&page=11)
页数11


# 网页链接
\ [ 显示的内容] （链接地址 空格 "提示文本" ）

[5.1 网页链接](obsidian://bookmaster?type=open-book&bid=nzfKtEkDzyIkywWQ&aid=89738f24-37de-f4c3-322d-687258ca08d5&page=15)
页数15

## 对网页链接的加粗
1. 对显示的文本加 ** 号
如：\ [ **显示的内容**] （链接地址 空格 "提示文本" ）
1. 对整个链接格式加 ** 号
如：**[显示文本内容]（链接地址） **

## 网页链接的变量
~~\[显示文本内容] [变量名]
\[变量名]： 链接地址
如：
[百度一下][百度]
先设定好变量的内容
[百度]: http://www.baidu.com
再去引用这个变量~~
[10.1 网页链接变量](obsidian://bookmaster?type=open-book&bid=nzfKtEkDzyIkywWQ&aid=8e19d33d-fc00-d0c4-8273-b316397abd73&page=25)
页数25




# 图像、图片
![[nzfKtEkDzyIkywWQ-fd76e506-3889-0c69-4da6-546df39a8ef1.png|600]]
[5.2 图像](obsidian://bookmaster?type=open-book&bid=nzfKtEkDzyIkywWQ&aid=ff85416a-1f3a-e942-f9ab-3018bac64147&page=15)
页数15

## 设置图像路径
### 当前父目录所在的文件夹下的图片（同一文件夹下）
直接写图片名称
```
![图片描述](example.png)
```

### 在上级
```
![图片描述](../images/example.png)
```
其中，`../` 表示返回到上级目录。
如果您的图片文件在上级目录的上级目录下，则可以使用两个 `../`：
```
![图片描述](../../images/example.png)
```

### 在下级
```
![图片描述](（不加/代表当前目录下的名为images的文件夹）images/example.png)
```

其中，`images/` 表示在当前目录下找到 `images` 目录，然后再找到 `example.png` 文件。
## 设置图像的宽高
### markdown原生设置方法
```
![图片描述](/路径/图片文件名){400x300}
```
请注意，使用这种方式设置图片大小可能会导致图片变形或失真，建议使用 `<img>` 标签的方式来设置图片大小。
#### 不支持的平台：
- github


### img标签设置
```
<img src="/路径/图片文件名" alt="图片描述" width="宽度" height="高度">
```
注意：
- 长、宽、高可以只指定一个，其他的能自动按比例缩放；
### obsidian设置
默认的第一个是宽度，高度会自动缩放。
![[nzfKtEkDzyIkywWQ-fb4950da-cb45-06e7-d462-40a7134f843d.png|500]]
16

# 表格
[6. 表格](obsidian://bookmaster?type=open-book&bid=nzfKtEkDzyIkywWQ&aid=d3d96daf-4c4a-4243-6c71-f27ecd4ca290&page=16)
页数16


# 代码域
## 1、行内代码
\ `代码内容`

## 2、代码块
```java（可以标注代码的语言种类）


```
[7. 代码域](obsidian://bookmaster?type=open-book&bid=nzfKtEkDzyIkywWQ&aid=5eb2a80a-c87f-7097-304f-a9d6b51e2c8d&page=17)
页数17

## 如何在行内代码里显示反引号
[7.3 如何在行内代码里显示反引号](obsidian://bookmaster?type=open-book&bid=nzfKtEkDzyIkywWQ&aid=27bcdcdb-aee3-249a-cd98-23c979421c02&page=22)
页数22
![[Pasted image 20230208221642.png|500]]


# 任务列表待办
\ - [ ] 内容
如：
- [ ] 测试
> 待办列表也是支持缩进的

如：
- [ ] 测试
	- [ ] 测试2

[8. 任务列表（待办）](obsidian://bookmaster?type=open-book&bid=nzfKtEkDzyIkywWQ&aid=fe2016df-c824-3a5e-5cb4-2f5b9aa96660&page=23)
页数23

# 注释
\ Markdown通用：<!-- 注释内容 -->
obsidian注释格式： \ %% 注释内容 %%

# 脚注
Markdown通用格式：
\[^1]
显示：[^1] [^测试]
在脚注解释的地方使用：
\[^脚注代号]: 脚注内容
> 如：
> 人们很长一段时间[^1]认为，地球是方的。
> [^1]: 时间大概是XXXX
> 

[10.2 脚注](obsidian://bookmaster?type=open-book&bid=nzfKtEkDzyIkywWQ&aid=88947732-b0ee-6ff8-7118-6d1ed72856ba&page=25)
页数25


**以上方式在obsidian中好像无效。**



# 对文本格式的设置
## 文本高亮
\==需要高亮的文本==
渲染：==高亮==

## 上标
- Markdown通用格式：
\格式：文本 ^1^
渲染：文本^1^
(在ob中无效)
- obsidian中的上标替用方案：
用html的\<sup>标记</sup>
渲染结果：<sup>标记</sup>

## 下标
[12.3 下标](obsidian://bookmaster?type=open-book&bid=nzfKtEkDzyIkywWQ&aid=8ceefdd7-7b5b-5c5a-3bf2-a36382f74b00&page=29)
页数29
![[nzfKtEkDzyIkywWQ-34d736d7-a3bf-bbac-887f-e6485f52d994.png|300]]
29

## 字体颜色





# 其他复杂不高效的方式
## 拓展文本格式标记
[11. 拓展文本格式标记](obsidian://bookmaster?type=open-book&bid=nzfKtEkDzyIkywWQ&aid=6f551f88-05b9-938a-1752-0b42bc4031ce&page=26)
页数26
## 多彩文本（字体颜色）

## emoji表情

## 流程图


# 媒体内容的添加
## 音频
[15.1 嵌入音频](obsidian://bookmaster?type=open-book&bid=nzfKtEkDzyIkywWQ&aid=cd489353-fedc-7ba9-09cb-cae88699b7d8&page=35)
页数35
[<audio controls="controls" preload="none" src="音频链接地址"></audio>](obsidian://bookmaster?type=open-book&bid=nzfKtEkDzyIkywWQ&aid=23631d70-d08e-3f3f-d52f-eaa5b43cd800&page=36)
页数36

## 视频
[15.2 嵌入视频](obsidian://bookmaster?type=open-book&bid=nzfKtEkDzyIkywWQ&aid=1ff50dc9-5e1e-e5cc-8721-045192cf900f&page=36)
页数36
[<video width="600" height="420" controls>  
<source src="movie.mp4" type="video/mp4">  
<source src="movie.ogg" type="video/ogg">  
<source src="movie.webm" type="video/webm">  
</video>  ](obsidian://bookmaster?type=open-book&bid=nzfKtEkDzyIkywWQ&aid=0070c93c-d3c7-4285-1ce8-307f83168a66&page=36)
页数36

## 网页页面
[15.3 嵌入页面](obsidian://bookmaster?type=open-book&bid=nzfKtEkDzyIkywWQ&aid=d095a18c-01f6-49fa-416d-014209902ad3&page=36)
页数36

# 公式Latex
![[nzfKtEkDzyIkywWQ-75cc318b-23d2-8d91-cf71-bbfd8d3aad70.png|300]]
37








# 其他需要注意的
## 转义符号
\
[13. 转义字符](obsidian://bookmaster?type=open-book&bid=nzfKtEkDzyIkywWQ&aid=b8bf8373-9602-a54c-1269-01c91ce9fdc1&page=30)
页数30





