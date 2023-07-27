---
title: CSS实际开发时
author: 杨翼臣
date created: 星期四, 4月13日 2023, 1:31:58 凌晨
date modified: 星期四, 4月13日 2023, 1:32:14 凌晨
tags: [css 开发 书写]
aliases: 
---

# CSS reset
重置掉所有可能影响样式的浏览器设置

## 参考范例
```css
/* CSS Reset */

* {

margin: 0;

padding: 0;

box-sizing: border-box;

}

.clear {

clear: both;

}

html {

font-size: 16px;

}

  

body {

font-family: Arial, sans-serif;

font-size: 1rem;

line-height: 1.5;

}

  

h1,

h2,

h3,

h4,

h5,

h6 {

font-weight: bold;

}

  

ul,

ol {

list-style: none;

}

  

a {

text-decoration: none;

color: inherit;

}

  

button,

input,

textarea {

border: none;

outline: none;

font-size: 1rem;

font-family: Arial, sans-serif;

}

  

button {

cursor: pointer;

}

  

/* End CSS Reset */

/* End CSS Reset */

```
### 这个CSS Reset代码片段包括以下内容：
1. 所有元素的内外边距都被设置为0，盒模型被设置为border-box。
2. html元素的文本大小被设置为16px，body元素的字体被设置为Arial、sans-serif，字体大小为1rem，行高为1.5。

1. h1到h6元素的字体重量被设置为粗体。
2. ul和ol元素的列表样式被设置为无。
3. a元素的文本装饰被设置为无，颜色为继承自父元素的颜色。
4. button、input和textarea元素的边框都被设置为无，文本大小为1rem，字体为Arial、sans-serif。
5. button元素的鼠标指针被设置为手型。

这个CSS Reset代码片段只是一个示例，具体的代码可以根据项目需求进行调整和修改。
## 清理所有元素的内外边距
    
```css

/* 清除所有元素的内外边距 */

* {

  margin: 0;

  padding: 0;

}

```

# 盒子A悬浮在盒子B上并且对齐

```css
.container {
position: relative;
}

.B {
}

.A {
position: absolute;
top: 0;
}
```
