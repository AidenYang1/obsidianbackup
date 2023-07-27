---
title: DateView使用页
author: 杨翼臣
date created: 星期一, 2月6日 2023, 11:13:41 晚上
date modified: 星期二, 2月7日 2023, 3:58:02 下午
tags: [dateview\使用]
aliases: 
---
## 一、列出当前页面所有标签
``= this.file.tags``

## 二、列出某个文件夹中的所有笔记
```dataview

list

from "10 示例文件夹"

sort file.name

```

## 三、列出某个标签的笔记
```dataview

list

from #张三

sort file.name

```

## 四、按笔记名称筛选笔记
```dataview
list

from "10 示例文件夹"

where contains(file.name,"dataview")

sort file.name
```

## 五、 组合筛选

组合使用的意思是逻辑上的或与非，例如文件名中包含某个日期，同时又包含或不包含某个关键词内容。现在做几个简单示例，大家可自行发挥。

##### **2.4.1 文件名含有210604，同时包括文件名中包括dataview**
```dataview
list

from "10 示例文件夹"

where contains(file.name,"dataview")

where contains(file.name,"210604")

sort file.name

```


## 六、排除筛选
##### **文件名含有210604，同时包括文件名中不包括dataview**
```dataview
list

from "10 示例文件夹"

where !contains(file.name,"dataview")

where contains(file.name,"210604")

sort file.name
```

## 七、不限定文件夹筛选
将from改为from ""即可。如显示最近的五十项修改：
```dataview

table 说明与标签, file.mtime

from ""

sort file.mtime desc

limit (50)
```

## 八、排序
上述七中代码，倒数第二行均为sort ……，这个语句表示排序。

以七为例，sort file.name 表示按文件名正向排序。如果想要逆序排列，只需要改成 sort file.name desc 即可。
```
list

from "10 示例文件夹"

sort file.name desc
```

![[Pasted image 20230207002717.png]]
可以对上面的附件进行重命名，使用[[Z导出文件夹/Ob插件自用备忘记录#^7ed8b3|该插件]]。

## 九、用表格形式展示信息
显示特定文件夹下的笔记以及用表格的方式显示每个笔记的创建时间。
```dataview

table file.ctime

from "10 示例文件夹"

sort file.name

```

## 十、展示特定文件夹的笔记以及yaml信息
用以下代码可以列出指定文件夹下的笔记问价，以及显示指定的yaml属性信息
```dataview

table tags

from "xx"

sort file.name

```

## 十一、多列内容展示
在table一行的后面的属性添加逗号，可以展示多个属性，如：
```dataview

table 说明与标签 , file.ctime

from "10 示例文件夹"

sort file.name

```
