---
title: JavaScript 基础 - 第1天
author: 杨翼臣
date created: 星期六, 4月15日 2023, 11:14:39 晚上
date modified: 星期四, 4月27日 2023, 10:31:00 晚上
tags: []
aliases: 
---
# JavaScript 基础 - 第1天

> 了解变量、数据类型、运算符等基础概念，能够实现数据类型的转换，结合四则运算体会如何编程。

- 体会现实世界中的事物与计算机的关系
- 理解什么是数据并知道数据的分类
- 理解变量存储数据的“容器”
- 掌握常见运算符的使用，了解优先级关系
- 知道 JavaScript 数据类型隐式转换的特征

## 前基础
### 关键字
用来使用某一种程序语言，让计算机理解的动词；

注：指 JavaScript 内部使用的词语，不开放给你用作其他用途；如 `let` 和`var`，保留字是指 JavaScript 内部目前没有使用的词语，但是将来可能会使用词语。



### 引入方式

JavaScript 程序不能独立运行，它需要被嵌入 HTML 中，然后浏览器才能执行 JavaScript 代码。通过 `script` 标签将 JavaScript 代码引入到 HTML 中，有两种方式：

#### 内部方式

通过 `script` 标签包裹 JavaScript 代码

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>JavaScript 基础 - 引入方式</title>
</head>
<body>
  <!-- 内联形式：通过 script 标签包裹 JavaScript 代码 -->
  <script>
    alert('嗨，欢迎来传智播学习前端技术！')
  </script>
</body>
</html>
```

#### 外部形式

一般将 JavaScript 代码写在独立的以 .js 结尾的文件中，然后通过 `script` 标签的 `src` 属性引入

```javascript
// demo.js
document.write('嗨，欢迎来传智播学习前端技术！')
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>JavaScript 基础 - 引入方式</title>
</head>
<body>
  <!-- 外部形式：通过 script 的 src 属性引入独立的 .js 文件 -->
  <script src="demo.js"></script>
</body>
</html>
```

如果 script 标签使用 src 属性引入了某 .js 文件，那么 标签的代码会被忽略！！！如下代码所示：

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>JavaScript 基础 - 引入方式</title>
</head>
<body>
  <!-- 外部形式：通过 script 的 src 属性引入独立的 .js 文件 -->
  <script src="demo.js">
    // 此处的代码会被忽略掉！！！！
  	alert(666);  
  </script>
</body>
</html>
```

###  注释和结束符

通过注释可以屏蔽代码被执行或者添加备注信息，JavaScript 支持两种形式注释语法：

#### 单行注释

使用 `// ` 注释单行代码

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>JavaScript 基础 - 注释</title>
</head>
<body>
  
  <script>
    // 这种是单行注释的语法
    // 一次只能注释一行
    // 可以重复注释
    document.write('嗨，欢迎来传智播学习前端技术！');
  </script>
</body>
</html>
```

#### 多行注释

使用 `/* */` 注释多行代码

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>JavaScript 基础 - 注释</title>
</head>
<body>
  
  <script>
    /* 这种的是多行注释的语法 */
    /*
    	更常见的多行注释是这种写法
    	在些可以任意换行
    	多少行都可以
      */
    document.write('嗨，欢迎来传智播学习前端技术！')
  </script>
</body>
</html>
```

**注：编辑器中单行注释的快捷键为 `ctrl + /`**

### 结束符

在 JavaScript 中 `;` 代表一段代码的结束，**多数情况下可以省略 `;` 使用回车（enter）替代。**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>JavaScript 基础 - 结束符</title>
</head>
<body>
  
  <script> 
    alert(1);
    alert(2);
    alert(1)
    alert(2)
  </script>
</body>
</html>
```

实际开发中有许多人主张书写 JavaScript 代码时省略结束符 `;`

### 输入和输出

输出和输入也可理解为人和计算机的交互，用户通过键盘、鼠标等向计算机输入信息，计算机处理后再展示结果给用户，这便是一次输入和输出的过程。

举例说明：如按键盘上的方向键，向上/下键可以滚动页面，按向上/下键这个动作叫作输入，页面发生了滚动了这便叫输出。

#### 输出语法
向文档中输出内容：

- 向html的body中输出内容
	- 向body内输出内容
	- 即便内容里面写的是标签，也会被解析成网页元素
```js
`document.wirte()`
```

- 作为页面的弹出警告框使用

```js
alert('要输出的内容')
```
alert和 prompt它们会跳过页面渲染先被执行

- 控制台输出，调试的时候使用

```js
console.log('控制台打印')
```


####  输入的语法
- prompt
显示一个对话框，对话框中包含一条文字信息，用来提示用户输入文字。弹出形式

```js
prompt('提示文本')
```
注意：
- alert和 prompt它们会跳过页面渲染先被执行
- 默认的字符类型是字符串类型。

### 字面量
计算机里面，字面量是在计算机中描述 事/物的
- 数字是数字字面量
- 文本是字符串字面量
- []是数组字面量
- {}是对象字面量；


## 变量

### 变量的本质
是程序在内存中申请的一块儿用来存放数据的小空间

> 理解变量是计算机存储数据的“容器”，掌握变量的声明方式

装数据。是容器。

### 如何声明变量(创建变量)
声明(定义)变量有两部分构成：用来声明的关键字、变量名（标识）
- 语法
```js
let 变量名
```

`let` 和 `var` 都是 JavaScript 中的声明变量的关键字，**推荐使用 `let` 声明变量！！！**

- 声明多个变量
使用,号连续声明即可


### 如何给变量赋值
声明（定义）变量相当于创造了一个空的“容器”，通过赋值向这个容器中添加数据。
- 语法

```js
变量名= 要赋的值
```

### 关键字let和var的区别
在现在的开发中一般已经不在使用var。let解决了var声明的如下不合理地方：
- 可以先使用 在声明（不合理）
- var 声明过的变量可以重复声明（不合理）
- 比如变量提升、全局变量、没有块级作用域等等



- 以下是使用 `let` 时的注意事项：

1. 允许声明和赋值同时进行
2.  不允许重复声明
3. 允许同时声明多个变量并赋值
4. JavaScript 中内置的一些关键字不能被当做变量名


- 以下是使用 `var` 时的注意事项：

2. 允许声明和赋值同时进行
2. 允许重复声明
3. 允许同时声明多个变量并赋值

大部分情况使用 `let` 和 `var` 区别不大，但是 `let` 相较 `var` 更严谨，因此推荐使用 `let`，后期会更进一步介绍二者间的区别。

### 如何更新变量值
在变量值的后面重新赋值，即可直接覆盖前面已经赋的值；
如：
```js
let age = 18
age =49
```


### 变量名命名规则和规范

^549138

#### 规则
- 只能是字母、数字、下划线_、$，且不能以数字开头
- 符号只允许：__和$
- 严格区分大小写，如 Age 和 age 是不同的变量
- JavaScript 内部已占用于单词（关键字或保留字）不允许使用

#### 规范
- 尽量保证变量具有一定的语义，见字知义
- 起名要有意义；
- 起名用小驼峰命名法
第一个单词首字母小写，后面每个单词首字母大小；userName


### 交换变量值
使用中间值进行交换AB。
- 声明一个临时变量temp
- 让temp = A的值
- 让A=B的值
- 把B=temp


## 数组
### 数组是什么？

**数组：**(Array)是一种可以按顺序保存数据的数据类型

**使用场景：**如果有多个数据可以用数组保存起来，然后放到一个变量中，管理非常方便
作用：将多个变量值放在一个变量下。
- 声明的语法
```
let 数组名=[A,B,C]
```
按顺序保存，每个都有自己的编号;
A的索引号为0，B的索引号为1；
ABC为变量值，要写纯文本中文要加'xxx'。

#### 元素
里面的每一项专业名词叫元素；
#### 下标
编号是下标，一般都说索引号。
#### 长度
获取数组的长度。也就是数组的元素个数。
在log中输出 数组名.length 即可
```
console.log(数组名.length)
```


### 数组的基本使用

#### 定义数组和数组单元
语法
```js
let 数组名 =[数据1，数据2，数据3，.....，数据n]
```

或者
```js
let arr =new Array(数据1,数据2，....数据n)
```

通过 `[]` 定义数组，数据中可以存放真正的数据，如小明、小刚、小红等这些都是数组中的数据，我们这些数据称为数组单元，数组单元之间使用英文逗号分隔。

#### 访问数组和数组索引
数据单元在数组中的编号称为索引值，也有人称其为下标。
索引值实际是按着数据单元在数组中的位置依次排列的，注意是从` 0` 开始的，如下图所示：


```html
<script>
  let classes = ['小明', '小刚', '小红', '小丽', '小米']
  
  // 1. 访问数组，语法格式为：变量名[索引值]
  document.write(classes[0]) // 结果为：小明
  document.write(classes[1]) // 结果为：小刚
  document.write(classes[4]) // 结果为：小米
  
  // 2. 通过索引值还可以为数组单重新赋值
  document.write(classes[3]) // 结果为：小丽
  // 重新为索引值为 3 的单元赋值
  classes[3] = '小小丽'
  document.wirte(classes[3]); // 结果为： 小小丽
</script>
```

#### 数据单元值类型

数组做为数据的集合，它的单元值可以是任意数据类型

```html
<script>
  // 6. 数组单值类型可以是任意数据类型

  // a) 数组单元值的类型为字符类型
  let list = ['HTML', 'CSS', 'JavaScript']
  // b) 数组单元值的类型为数值类型
  let scores = [78, 84, 70, 62, 75]
  // c) 混合多种类型
  let mixin = [true, 1, false, 'hello']
</script>
```

#### 数组长度属性

重申一次，数组在 JavaScript 中并不是新的数据类型，它属于对象类型。

```html
<script>
  // 定义一个数组
  let arr = ['html', 'css', 'javascript']
  // 数组对应着一个 length 属性，它的含义是获取数组的长度
  console.log(arr.length) // 3
</script>
```



### 操作数组
对数组可进行的操作：
- push 数组尾部
语法

```js
arr.push(数据)  //在数组的后面新增内容
```

- unshift 数组头部
```js
arr.unshift(新增的内容)
```
- pop 删除末尾元素
语法
```js
arr.pop()
```
- shift 删除首元素

```js
arr.shift()
```

- splice 删除指定的元素
```js
arr.splice(start,deleteCount)
arr.splice(起始位置默认为0,deleteCount删除元素的个数) //不指定deleteCount的情况下，是从开头一直删到最后；
```
- 筛选数组
```js
let arr=[2,0,6,1,77,9,54,3,78,7]
//设定一个新的数组用于存放满足条件的数据
let newArr=[]

//去遍历旧数组
for (let i=0;i<arr.length;i++){
    if(arr[i]>=10){
        //将满足条件的数据追加给新的数组
        newArr.push(arr[i])
    }
}
console.log(newArr)

```

使用以上4个方法时，都是直接在原数组上进行操作，即成功调任何一个方法，原数组都跟着发生相应的改变。并且在添加或删除单元时 `length` 并不会发生错乱。

```html
<script>
  // 定义一个数组
  let arr = ['html', 'css', 'javascript']

  // 1. push 动态向数组的尾部添加一个单元
  arr.push('Nodejs')
  console.log(arr)
  arr.push('Vue')

  // 2. unshit 动态向数组头部添加一个单元
  arr.unshift('VS Code')
  console.log(arr)

  // 3. splice 动态删除任意单元
  arr.splice(2, 1) // 从索引值为2的位置开始删除1个单元
  console.log(arr)

  // 4. pop 删除最后一个单元
  arr.pop()
  console.log(arr)

  // 5. shift 删除第一个单元
  arr.shift()
  console.log(arr)
</script>
```


### 练习
#### 求数组中的最大值和最小值
```js
// 声明一个数组
let arr=[3,5,4,8,6]
// 声明一个保存最大元素的变量max，可以取数组中的第一个元素
let max= arr[0]
let min= arr[0]
// 遍历这个数组，用max和每个数组的元素进行比较
for(let i=1;i<arr.length;i++){
    //如果max比数组元素里面的值小，就把这个元素赋给max
    if(max<arr[i]){
        max=arr[i]
    }
}

for(let j=1;j<arr.length;j++){
    if(min>arr[j]){
        min=arr[j]
    }
}
console.log(`数组的最大值为${max}`);
console.log(`数组的最小值为${min}`);



// 也可以使用三元运算符进行写


```



## 常量
使用 const 声明
使用场景：当某个变量永远不会改变的时候，就可以使用 const 来声明，而不是let。
命名规范：和变量一致
~~~javascript
const PI = 3.14
~~~

>注意： **常量不允许重新赋值**,声明的时候必须赋值（初始化）

## 数据类型
js是弱数据类型。所以数据的类型规定不是那么严格。变量到底是什么类型数据还是要通过赋值后进行判断。
### 如何检测数据类型？
注：通过 typeof 关键字检测数据类型
语法
- 作为运算符：typeof 变量名
- 函数形式：typeof(x)




### 数值类型
number
即我们数学中学习到的数字，可以是整数、小数、正数、负数
JavaScript 中的数值类型与数学中的数字是一样的，分为正数、负数、小数等。

#### 运算方式
- +：求和
- -：求差
- \*：求积
- /：求商
- %：取余数（取模】）

### 字符串类型
可以单引号、双引号、反引号包裹，用这些包裹的是字符串。通常用单引号跟html作区分。

#### 注意事项：
1. 无论单引号或是双引号必须成对使用
2. 已经有单引号的还想用引号就用双引号互相嵌套。
3. 单引号和双引号都是找离着最近的符号进行嵌套。
4. 单引号/双引号可以互相嵌套，但是不能以自已嵌套自已
5. 必要时可以使用转义符 `\`，输出单引号或双引号

```js

    let user_name = '小明' // 使用单引号
    let gender = "男" // 使用双引号
    let str = '123' // 看上去是数字，但是用引号包裹了就成了字符串了
    let str1 = '' // 这种情况叫空字符串
    documeent.write(typeof user_name) // 结果为 string
    documeent.write(typeof gender) // 结果为 string
    documeent.write(typeof str) // 结果为 string

```

#### 如何拼接字符串？
使用+号拼接变量或常亮。+号用在两个数字是相加，用在两个变量或者常量时是相连。

#### 用模板字符串更方便的拼接字符串和变量
使用${变量名}，直接显示变量名的内容；
```js
console.log('我今年${变量名}')
```


### 布尔类型
表示肯定或否定时在计算机中对应的是布尔类型数据，它有两个固定的值 `true` 和 `false`，表示肯定的数据用 `true`，表示否定的数据用 `false`。



### undefined 未定义的类型
未定义是比较特殊的类型，只有一个值 undefined
- 怎么产生？
- 只声明变量，不赋值就能产生这个类型。
- 变量的默认值为 undefined，一般很少【直接】为某个变量赋值为 undefined。

**注：JavaScript 中变量的值决定了变量的数据类型。**
是完全没有。

### 空null类型
代表“无”、“没有”、“值未知”。有值，值就是为空。
```js
let obj=null
console.log(obg)
```
是有，值就是空。

## 类型转换（转换数据类型）

### 隐式转换（js自带的规则转换）
js自己内部设定的，已经转换的。
某些运算符被执行时，系统内部自动将数据类型进行转换，这种转换称为隐式转换。
#### 隐式转换规则
- +
数字和数字，就是加。数字和其他是连拼接。
看做正号直接转换后面的值为数字型。
任何数据和字符串相加都是字符串。
- -,\*，/
数字和数字是减。数字和其他，转字符串为数字。



### 显式转换（自己强行让系统转换）
#### 将数据转换为Number
用法：
```js
Number（要转换的内容）

#只保留整数，去掉其他内容
parseInt（要转换的内容）

#允许保留小数
parseFloat（要转换的内容）
```


#### 转换失败时
结果为 `NaN`（Not a Number）即不是一个数字。



# 案例
![[Pasted image 20230418203743.png]]


# JavaScript 基础 - 第2天



## 运算符

### 算术运算符

数字是用来计算的，比如：乘法 * 、除法 / 、加法 + 、减法 - 等等，
算术运算符：也叫数学运算符，主要包括加、减、乘、除、取余（求模）等

| 运算符 | 作用                                                 |
| ------ | ---------------------------------------------------- |
| +      | 求和                                                 |
| -      | 求差                                                 |
| *      | 求积                                                 |
| /      | 求商                                                 |
| **%**  | 取模（取余数），开发中经常用于作为某个数字是否被整除 |

> 注意：在计算失败时，显示的结果是 NaN （not a number）

```javascript
// 算术运算符
console.log(1 + 2 * 3 / 2) //  4 
let num = 10
console.log(num + 10)  // 20
console.log(num + num)  // 20

// 1. 取模(取余数)  使用场景：  用来判断某个数是否能够被整除
console.log(4 % 2) //  0  
console.log(6 % 3) //  0
console.log(5 % 3) //  2
console.log(3 % 5) //  3

// 2. 注意事项 : 如果我们计算失败，则返回的结果是 NaN (not a number)
console.log('pink老师' - 2)
console.log('pink老师' * 2)
console.log('pink老师' + 2)   // pink老师2
```

### 赋值运算符

赋值运算符：对变量进行赋值的运算符

 =     将等号右边的值赋予给左边, 要求左边必须是一个容器num

| 运算符 | 作用     |
| ------ | -------- |
|+=|加法赋值，num自己加“几”|
| -+     |减法赋值。|
| *=     | 乘法赋值 |
| /=     | 除法赋值 |
| %=     | 取余赋值 |

```javascript
<script>
let num = 1
// num = num + 1
// 采取赋值运算符
// num += 1
num += 3
console.log(num)
</script>
```

### 自增/自减运算符
每次都只加1
| 符号 | 作用 | 说明                       |
| ---- | ---- | -------------------------- |
| ++   | 自增 | 变量自身的值加1，例如: x++ |
| --   | 自减 | 变量自身的值减1，例如: x-- |

- 前置自增：++变量名，先自加再参与代码运算
- 后置自增：变量名++，先参与代码运算再自加i原本的值


1. ++在前和++在后在单独使用时二者并没有差别，而且一般开发中我们都是独立使用
2. ++**在后（后缀式）我们会使用更多**

> 注意：
>
> 1. 只有变量能够使用自增和自减运算符
> 2. ++、-- 可以在变量前面也可以在变量后面，比如: x++  或者  ++x 

```javascript
<script>
    // let num = 10
    // num = num + 1
    // num += 1
    // // 1. 前置自增
    // let i = 1
    // ++i
    // console.log(i)

    // let i = 1
    // console.log(++i + 1)
    // 2. 后置自增
    // let i = 1
    // i++
    // console.log(i)
    // let i = 1
    // console.log(i++ + 1)

    // 了解 
    let i = 1
    console.log(i++ + ++i + i)
  </script>
```

### 比较运算符

使用场景：比较两个数据大小、是否相等，根据比较结果返回一个布尔值（true / false）

| 运算符 | 作用                                   |
| ------ | -------------------------------------- |
| >      | 左边是否大于右边                       |
| <      | 左边是否小于右边                       |
| >=     | 左边是否大于或等于右边                 |
| <=     | 左边是否小于或等于右边                 |
| ===    | 左右两边是否`类型`和`值`都相等（重点） |
| ==     | 左右两边`值`是否相等                   |
| !=     | 左右值不相等                           |
| !==    | 左右两边是否不全等                     |

注意：NaN不等于任何其他值，包括他自己；NaN跟任何值比较都是false；
如果数据类型是不同的，那么会把数据隐式转换成number后在进行比较；


```javascript
<script>
  console.log(3 > 5)
  console.log(3 >= 3)
  console.log(2 == 2)
  // 比较运算符有隐式转换 把'2' 转换为 2  双等号 只判断值
  console.log(2 == '2')  // true
  // console.log(undefined === null)
  // === 全等 判断 值 和 数据类型都一样才行
  // 以后判断是否相等 请用 ===  
  console.log(2 === '2')
  console.log(NaN === NaN) // NaN 不等于任何人，包括他自己
  console.log(2 !== '2')  // true  
  console.log(2 != '2') // false 
  console.log('-------------------------')
  console.log('a' < 'b') // true
  console.log('aa' < 'ab') // true
  console.log('aa' < 'aac') // true
  console.log('-------------------------')
</script>
```


### ASCII 字符代码表
![[Pasted image 20230421170509.png|600]]
将字符转换为十进制，可以比较每个字符的大小；

比较方法：
- 从左到右比较
- aa<ab,是对的aa<aac也是对的
- 比较完第一位再比较第二位，以此类推




### 逻辑运算符

使用场景：可以把多个布尔值放到一起运算，最终返回一个布尔值

| 符号 | 名称   | 日常读法 | 特点                       | 口诀           |
| ---- | ------ | -------- | -------------------------- | -------------- |
| &&   | 逻辑与 | 并且     | 符号两边有一个假的结果为假 | 一假则假       |
| \|\| | 逻辑或 | 或者     | 符号两边有一个真的结果为真 | 一真则真       |
| !    | 逻辑非 | 取反     | true变false  false变true   | 真变假，假变真 |

| A     | B     | A && B | A \|\| B | !A    |
| ----- | ----- | ------ | -------- | ----- |
| false | false | false  | false    | true  |
| false | true  | false  | true     | true  |
| true  | false | false  | true     | false |
| true  | true  | true   | true     | false |

```javascript
<script>
    // 逻辑与 一假则假
    console.log(true && true)
    console.log(false && true)
    console.log(3 < 5 && 3 > 2)
    console.log(3 < 5 && 3 < 2)
    console.log('-----------------')
    // 逻辑或 一真则真
    console.log(true || true)
    console.log(false || true)
    console.log(false || false)
    console.log('-----------------')
    // 逻辑非  取反
    console.log(!true)
    console.log(!false)

    console.log('-----------------')

    let num = 6
    console.log(num > 5 && num < 10)
    console.log('-----------------')
  </script>
```

#### 逻辑运算符案例
让用户输入一个数，判断这个数能否被4整除，但是不能被100整除；满足条件则弹出true，否则弹出false；


### 运算符优先级
![[Pasted image 20230421171954.png|600]]

> 逻辑运算符优先级： ！> && >  ||  
> 一元运算符中逻辑非的优先级最高；



## 语句

### 表达式和语句
#### 表达式
表达式是可以被求值的，一般都有赋值号；
#### 语句
不一定有值，没有赋值号；


## 控制程序流程的语句 3个
###  顺序结构
默认模式，从上到下，从左到右；
### 分支语句
分支语句可以根据条件判定真假，来选择性的执行想要的代码

分支语句包含：
1. if分支语句（重点）
2. 三元运算符
3. switch语句

#### if 单分支语句
语法：
~~~javascript
if(条件表达式) {
  // 满足条件要执行的语句
}
~~~
- （结果只有两种，一种是满足，一种是不满足，满足就走后面的代码）
- 小括号内的结果若不是布尔类型时，会发生类型转换为布尔值，类似Boolean()
- 如果大括号只有一个语句，大括号可以省略；

注意：
- 除了0，所有的数字都是真；
- 除了' '，空字符串，其他任何的中文和字符串都是真；
- 简单理解就是，if的条件表达式（）里面有象征着没有的具体的值，就是false；

~~~javascript
<script>
    // 单分支语句
    // if (false) {
    //   console.log('执行语句')
    // }
    // if (3 > 5) {
    //   console.log('执行语句')
    // }
    // if (2 === '2') {
    //   console.log('执行语句')
    // }
    //  1. 除了0 所有的数字都为真
    //   if (0) {
    //     console.log('执行语句')
    //   }
    // 2.除了 '' 所有的字符串都为真 true
    // if ('pink老师') {
    //   console.log('执行语句')
    // }
    // if ('') {
    //   console.log('执行语句')
    // }
    // // if ('') console.log('执行语句')

    // 1. 用户输入
    let score = +prompt('请输入成绩')
    // 2. 进行判断输出
    if (score >= 700) {
      alert('恭喜考入黑马程序员')
    }
    console.log('-----------------')

  </script>
~~~

#### if双分支语句

如果有两个条件的时候，可以使用 if else 双分支语句

~~~javascript
if (条件表达式){
  // 满足条件要执行的语句
} else {
  // 不满足条件要执行的语句
}
~~~

前者为满足时执行的，后者是不满足时执行的；
例如：

~~~javascript
 <script>
    // 1. 用户输入
    let uname = prompt('请输入用户名:')
    let pwd = prompt('请输入密码:')
    // 2. 判断输出
    if (uname === 'pink' && pwd === '123456') {
      alert('恭喜登录成功')
    } else {
      alert('用户名或者密码错误')
    }
  </script>
~~~

#### if 多分支语句
使用场景： 适合于有多个条件的时候
语法
```js
if (条件1){代码1}
	else if(条件2){代码2}
	else if(条件3){代码3}
	else{}
	
```

适合三个及以上使用，抛开一个初始块，抛开一个全非块（不是上面的条件就走）

~~~javascript
 <script>
    // 1. 用户输入
    let score = +prompt('请输入成绩：')
    // 2. 判断输出
    if (score >= 90) {
      alert('成绩优秀，宝贝，你是我的骄傲')
    } else if (score >= 70) {
      alert('成绩良好，宝贝，你要加油哦~~')
    } else if (score >= 60) {
      alert('成绩及格，宝贝，你很危险~')
    } else {
      alert('成绩不及格，宝贝，我不想和你说话，我只想用鞭子和你说话~')
    }
  </script>
~~~

#### 三元运算符（三元表达式）

**使用场景**： 一些**简单的双分支**，可以使用  三元运算符（三元表达式），写起来比 if  else双分支 更简单

**符号**：? 与 : 配合使用

语法：

~~~javascript
条件 ? 表达式1 ： 表达式2
~~~

条件？满足条件执行的代码 : 不满足条件执行的代码（一般用来取值）

例如：

~~~javascript
// 三元运算符（三元表达式）
// 1. 语法格式
// 条件 ? 表达式1 : 表达式2 

// 2. 执行过程 
// 2.1 如果条件为真，则执行表达式1
// 2.2 如果条件为假，则执行表达式2

// 3. 验证
// 5 > 3 ? '真的' : '假的'
console.log(5 < 3 ? '真的' : '假的')

// let age = 18 
// age = age + 1
//  age++

// 1. 用户输入 
let num = prompt('请您输入一个数字:')
// 2. 判断输出- 小于10才补0
// num = num < 10 ? 0 + num : num
num = num >= 10 ? num : 0 + num
alert(num)
~~~


##### 案例
让用户输入一个数，如果数字小于10，则前面补上一个0，比如07、05等；利用三元运算符；




#### switch语句（了解）
语法
```js
switch (数据) {
    case 值1:
        代码1
        break（退出switch）
    case 值2:
        代码2
        break
    default:(都没有满足的时候执行)
        代码n
        break
}
```
使用场景： 适合于有多个条件的时候，也属于分支语句，大部分情况下和 if多分支语句 功能相同

注意：

1. switch case语句一般用于等值判断, if适合于区间判断
2. switchcase一般需要配合break关键字使用 没有break会造成case穿透
3. if 多分支语句开发要比switch更重要，使用也更多

例如：

~~~javascript
// switch分支语句
// 1. 语法
// switch (表达式) {
//   case 值1:
//     代码1
//     break

//   case 值2:
//     代码2
//     break
//   ...
//   default:
//     代码n
// }

<script>
  switch (2) {
    case 1:
    console.log('您选择的是1')
    break  // 退出switch
    case 2:
    console.log('您选择的是2')
    break  // 退出switch
    case 3:
    console.log('您选择的是3')
    break  // 退出switch
    default:
    console.log('没有符合条件的')
  }
</script>
~~~

#### 断点调试

**作用：**学习时可以帮助更好的理解代码运行，工作时可以更快找到bug

浏览器打开调试界面

1. 按F12打开开发者工具
2. 点到源代码一栏 （ sources ）
3. 选择代码文件

**断点：**在某句代码上加的标记就叫断点，当程序执行到这句有标记的代码时会暂停下来



### 循环语句

使用场景：重复执行 指定的一段代码，比如我们想要输出10次 '我学的很棒'

学习路径：

1.while循环

2.for 循环（重点）

#### while循环

while :  在…. 期间， 所以 while循环 就是在满足条件期间，重复执行某些代码。

**语法：**

~~~javascript
while (条件表达式) {
   // 循环体    
}
~~~

例如：

~~~javascript
// while循环: 重复执行代码

// 1. 需求: 利用循环重复打印3次 '月薪过万不是梦，毕业时候见英雄'
let i = 1
while (i <= 3) {
  document.write('月薪过万不是梦，毕业时候见英雄~<br>')
  i++   // 这里千万不要忘了变量自增否则造成死循环
}
~~~

循环三要素：

1.初始值 （经常用变量）

2.终止条件

3.变量的变化量

例如：

~~~javascript
<script>
  // // 1. 变量的起始值
  // let i = 1
  // // 2. 终止条件
  // while (i <= 3) {
  //   document.write('我要循环三次 <br>')
  //   // 3. 变量的变化量
  //   i++
  // }
  // 1. 变量的起始值
  let end = +prompt('请输入次数:')
let i = 1
// 2. 终止条件
while (i <= end) {
  document.write('我要循环三次 <br>')
  // 3. 变量的变化量
  i++
}

</script>
~~~

#### 中止循环
- break:运行到这以后退出整个循环，后边的也不执行了；
- continue:中止满足条件的后面代码的执行，后面的大循环继续进行；这次的小循环continue后面的不再执行；


~~~javascript
<script>
    // let i = 1
    // while (i <= 5) {
    //   console.log(i)
    //   if (i === 3) {
    //     break  // 退出循环
    //   }
    //   i++

    // }


    let i = 1
    while (i <= 5) {
      if (i === 3) {
        i++
        continue
      }
      console.log(i)
      i++

    }
  </script>
~~~

#### 无限循环

1.while(true) 来构造“无限”循环，需要使用break退出循环。（常用）

2.for(;;) 也可以来构造“无限”循环，同样需要使用break退出循环。

~~~javascript
// 无限循环  
// 需求： 页面会一直弹窗询问你爱我吗？
// (1). 如果用户输入的是 '爱'，则退出弹窗
// (2). 否则一直弹窗询问

// 1. while(true) 无限循环
// while (true) {
//   let love = prompt('你爱我吗?')
//   if (love === '爱') {
//     break
//   }
// }

// 2. for(;;) 无限循环
for (; ;) {
  let love = prompt('你爱我吗?')
  if (love === '爱') {
    break
  }
}
~~~

## 综合案例-ATM存取款机



![67101878155](assets/1671018781557.png)



分析：

①：提示输入框写到循环里面（无限循环）

②：用户输入4则退出循环 break

③：提前准备一个金额预先存储一个数额 money

④：根据输入不同的值，做不同的操作

​     (1)  取钱则是减法操作， 存钱则是加法操作，查看余额则是直接显示金额

​     (2) 可以使用 if else if 多分支 来执行不同的操作

完整代码：

~~~javascript
<script>
  // 1. 开始循环 输入框写到 循环里面
  // 3. 准备一个总的金额
  let money = 100
while (true) {
  let re = +prompt(`
请您选择操作：
1.存钱
2.取钱
3.查看余额
4.退出
`)
  // 2. 如果用户输入的 4 则退出循环， break  写到if 里面，没有写到switch里面， 因为4需要break退出循环
  if (re === 4) {
    break
  }
  // 4. 根据输入做操作
  switch (re) {
    case 1:
      // 存钱
      let cun = +prompt('请输入存款金额')
      money = money + cun
      break
      case 2:
      // 存钱
      let qu = +prompt('请输入取款金额')
      money = money - qu
      break
      case 3:
      // 存钱
      alert(`您的银行卡余额是${money}`)
      break
  }
}
</script>
~~~

# JavaScript 基础第三天笔记

**if 多分支语句和 switch的区别：**

1. 共同点

   - 都能实现多分支选择， 多选1 
   - 大部分情况下可以互换

2. 区别：

   - switch…case语句通常处理case为比较**确定值**的情况，而if…else…语句更加灵活，通常用于**范围判断**(大于，等于某个范围)。
   - switch 语句进行判断后直接执行到程序的语句，效率更高，而if…else语句有几种判断条件，就得判断多少次
   - switch 一定要注意 必须是 ===  全等，一定注意 数据类型，同时注意break否则会有穿透效果
   - 结论：
     - 当分支比较少时，if…else语句执行效率高。
     - 当分支比较多时，switch语句执行效率高，而且结构更清晰。

   ​

## for 语句


### for语句的基本使用
语法
```js
for(变量的起始值;终止条件;变量变化量){
//循环体
}
```
1. 实现循环的 3 要素

```html
<script>
  // 1. 语法格式
  // for(起始值; 终止条件; 变化量) {
  //   // 要重复执行的代码
  // }

  // 2. 示例：在网页中输入标题标签
  // 起始值为 1
  // 变化量 i++
  // 终止条件 i <= 6
  for(let i = 1; i <= 6; i++) {
    document.write(`<h${i}>循环控制，即重复执行<h${i}>`)
  }
</script>
```

2. 变化量和死循环，`for` 循环和 `while` 一样，如果不合理设置增量和终止条件，便会产生死循环。


3. 跳出和终止循环

```html
<script>
    // 1. continue 
    for (let i = 1; i <= 5; i++) {
        if (i === 3) {
            continue  // 结束本次循环，继续下一次循环
        }
        console.log(i)
    }
    // 2. break
    for (let i = 1; i <= 5; i++) {
        if (i === 3) {
            break  // 退出结束整个循环
        }
        console.log(i)
    }
</script>
```

结论：

- `JavaScript` 提供了多种语句来实现循环控制，但无论使用哪种语句都离不开循环的3个特征，即起始值、变化量、终止条件，做为初学者应着重体会这3个特征，不必过多纠结三种语句的区别。
- 起始值、变化量、终止条件，由开发者根据逻辑需要进行设计，规避死循环的发生。
- 当如果明确了循环的次数的时候推荐使用`for`循环,当不明确循环的次数的时候推荐使用`while`循环

>注意：`for` 的语法结构更简洁，故 `for` 循环的使用频次会更多。


### 使用for循环打印数组
```js
let arr=['你好','我好','他好','我们好']

for(let i=0;i<=3;i++)

{

console.log(arr[i]);

}
```
要打印整个数组，i<=值要是数组长度（元素个数）减1；从0开始算的；
高级语法：
- 不加等号

```js
for(let i=0;i<arr.length;i++)
```
- 加等号
```js
for(let i=0;i<=arr.length -1;i++)
```

### for循环和while循环的区别
- 当明确了循环的次数时使用for；
- 不明确时使用while；


### 退出循环
- continue：退出本次循环，一般用于排除或者跳过某一个选项的时候，用continue；
- break:退出**整个for循环**，一般用于结果已经得到，后续的循环不需要使用的时候使用；




### 循环嵌套
- 一个循环再套一个循环，一般指的是for循环的嵌套；但是其他循环也支持循环嵌套
- 外层循环循环一次，里层循环循环全部
```js
for (let i = 1; i <= 3; i++) {
    document.write(`这是第${i}天<br>`)
    for (let j = 1; j <= 5; j++)
        document.write(`记住了第${j}个单词<br>`)
}```

#### 倒三角

~~~javascript
 // 外层打印几行
for (let i = 1; i <= 5; i++) {
    // 里层打印几个星星
    for (let j = 1; j <= i; j++) {
        document.write('★')
    }
    document.write('<br>')
}
~~~

 ![64791867895](assets/1647918678956.png)

#### 九九乘法表

样式css

~~~css
span {
    display: inline-block;
    width: 100px;
    padding: 5px 10px;
    border: 1px solid pink;
    margin: 2px;
    border-radius: 5px;
    box-shadow: 2px 2px 2px rgba(255, 192, 203, .4);
    background-color: rgba(255, 192, 203, .1);
    text-align: center;
    color: hotpink;
}
~~~

javascript 

~~~javascript
 // 外层打印几行
for (let i = 1; i <= 9; i++) {
    // 里层打印几个星星
    for (let j = 1; j <= i; j++) {
        // 只需要吧 ★ 换成  1 x 1 = 1   
        document.write(`
		<div> ${j} x ${i} = ${j * i} </div>
     `)
    }
    document.write('<br>')
}
~~~


## 冒泡排序
```js
let arr=[4,5,2,9,7,0]
//需要的趟数
for (let i=0;i<arr.length -1;i++){
    //每一趟交换的次数
    for(let j=0;j<arr.length -i -1;j++){
        //开始交换，前提是第一个数大于第二个数发生
        if(arr[j]>arr[j+1]){
            let temp=arr[j]
            arr[j]=arr[j+1]
            arr[j+1]=temp
        }

    }
}
console.log(arr);
```
判断大小交换值，从第一个开始两两相比较；
- 需要走多少趟？
数组长度-1
- 每一趟交换多少次？
数组的长度 -i -1 
- 两个变量交换


开发中用sort进行排序，默认按照升序
```js
arr.sort()
```

## sort排序
开发中用sort进行排序，默认按照升序，从小到大
```js
arr.sort()
```

### 升序完整的代码

```js
arr.sort(function(a,b){    //理解，a是小的,b是大的；
return a-b
})
```

### 降序
```js
arr.sort(function (a,b)){
		 return b-a
}
```

# JavaScript 基础 - 第4天笔记

## 函数
包裹代码块，打包代码块
### 声明（定义）
```js
function 函数名(){
	函数体
}
```
声明（定义）一个完整函数包括关键字、函数名、形式参数、函数体、返回值5个部分

### 命名规范
- 和变量命名基本一致[[JS 笔记汇总#^549138]]
- 尽量使用小驼峰的命名方式
- 前缀应该为动词
- 建议：常用动词进行约定
	- can 判断是否能够执行某个动作
	- has 判断是否含有某个值
	- is 判断是否为某个值
	- get 获取某个值
	- set 设置某个值
	- load 加载某些数据

> 注：函数名的命名规则与变量是一致的，并且尽量保证函数名的语义。
### 调用
对声明完的函数进行调用
```js
函数名()
```

#### 函数复用代码和循环重复代码有什么不同？
- 循环重复代码写完立即执行；
- 函数复用代码，需要就调用；
#### 小案例： 小星星

~~~javascript
<script>
        // 函数声明
        function sayHi() {
            // document.write('hai~')
            document.write(`*<br>`)
            document.write(`**<br>`)
            document.write(`***<br>`)
            document.write(`****<br>`)
            document.write(`*****<br>`)
            document.write(`******<br>`)
            document.write(`*******<br>`)
            document.write(`********<br>`)
            document.write(`*********<br>`)
        }
        // 函数调用
        sayHi()
        sayHi()
        sayHi()
        sayHi()
        sayHi()
    </script>
~~~

###  参数
设定两个等待位置，等待正儿八经需要传进来的值代替这个位置去执行代码；
通过向函数传递参数，可以让函数更加灵活多变，参数可以理解成是一个变量。
总结：
1. 声明（定义）函数时的形参没有数量限制，当有多个形参时使用 `,` 分隔
2. 调用函数传递的实参要与形参的顺序一致



#### 形参和实参
- 形参：声明函数时写在函数名右边小括号里的叫形参（形式上的参数）

- 实参：调用函数时写在函数名右边小括号里的叫实参（实际上的参数）

形参可以理解为是在这个函数内声明的变量（比如 num1 = 10）实参可以理解为是给这个变量赋值

开发中尽量保持形参和实参个数一致

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>JavaScript 基础 - 函数参数</title>
</head>
<body>
  <script>
    // 声明（定义）一个计算任意两数字和的函数
    // 形参 x 和 y 分别表示任意两个数字，它们是两个变量
    function count(x, y) {
      console.log(x + y);
    }
    // 调用函数，传入两个具体的数字做为实参
    // 此时 10 赋值给了形参 x
    // 此时 5  赋值给了形参 y
    count(10, 5); // 结果为 15
  </script>
</body>
</html>
```

### 给形参默认值
不设置默认值，函数缺少实参的情况下会输出undefined；
- 在声明函数的时候设置默认值
如
```js
function getSum(a=0,b=0)
```
不会影响后边的实参传递，只会在后面函数调用时没写形参时执行；
### 向函数传递参数
在调用已经预设好位置和形参个数的函数时，用
```js
函数名（参数值）
```
### 返回值
语法
```js
return 数据
```
函数的本质是封装（包裹），函数体内的逻辑执行完毕后，函数外部如何获得函数内部的执行结果呢？要想获得函数内部逻辑的执行结果，需要通过 `return` 这个关键字，将内部执行结果传递到函数外部，这个被传递到外部的结果就是返回值。

```js
function fn() {
    return 20
}

// 相当于执行了fn（）=20
let re = fn
console.log(re)
```


#### 为什么要用return？
- 函数的return语句用于指定函数的返回值。当函数执行到return语句时，它会停止执行并返回一个值给调用它的代码。这个返回值可以是任何类型的数据，包括整数、字符串、布尔值、数组、对象等。
- 在函数内部，return语句可以帮助你控制函数的行为。例如，你可以在函数内部使用if语句来判断一些条件，然后根据条件返回不同的值。这样，你就可以让函数在不同的情况下返回不同的结果。
- 另外，return语句也可以用于提前退出函数。如果你在函数内部遇到了某些错误或特殊情况，可以使用return语句提前跳出函数，避免执行不必要的代码，从而提高程序的效率。
#### 总结：

1. 在函数体中使用return 关键字能将内部的执行结果交给函数外部使用
2. 函数内部只能出现1 次 return，并且 return 下一行代码不会再被执行，所以return 后面的数据不要换行写
3. return会立即结束当前函数
4. 函数可以没有return，这种情况默认返回值为 undefined

### 作用域

通常来说，一段程序代码中所用到的名字并不总是有效和可用的，而限定这个名字的可用性的代码范围就是这个名字的作用域。

作用域的使用提高了程序逻辑的局部性，增强了程序的可靠性，减少了名字冲突。

#### 全局作用域

作用于所有代码执行的环境(整个 script 标签内部)或者一个独立的 js 文件

处于全局作用域内的变量，称为全局变量

#### 局部作用域

作用于函数内的代码环境，就是局部作用域。 因为跟函数有关系，所以也称为函数作用域。

处于局部作用域内的变量称为局部变量

>如果函数内部，变量没有声明，直接赋值，也当全局变量看，但是强烈不推荐
>
>但是有一种情况，函数内部的形参可以看做是局部变量。

### 匿名函数

函数可以分为具名函数和匿名函数

匿名函数：没有名字的函数,无法直接使用。

#### 函数表达式

~~~javascript
// 声明
let fn = function() { 
   console.log('函数表达式')
}
// 调用
fn()
~~~

#### 立即执行函数

~~~javascript
(function(){ xxx  })();
(function(){xxxx}());
~~~

>无需调用，立即执行，其实本质已经调用了
>
>多个立即执行函数之间用分号隔开















​		在能够访问到的情况下 先局部 局部没有在找全局