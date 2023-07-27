---
title: 程序的控制结构
author: 杨翼臣
date created: 星期一, 2月27日 2023, 10:10:55 上午
date modified: 星期一, 3月6日 2023, 10:36:35 上午
tags: [web开发]
aliases: 
---

# 程序的控制结构

## 例题
用概率的方法来求Pi的值
随机生成10万个点，计算点到原点之间的距离
计算随机生成的点在圆中出现的概率，来估计pi的值

```python
from random import random

import math

for i in range(1,11):

x,y =random(),random()

d =math.sqrt(x*x +y*y)

print("生成的点是:({},{})".format(x,y))

print("点到原点之间的距离是:{}".format(d))

```
输出结果如果为4e-05或者其他的不正常的数值。
这个结果可能是因为 count 和 a 都被设置为整数类型，导致结果被截断成整数形式。
可以将 count 和 a 的类型转换为浮点类型，以便得到正确的结果。
修改后的代码为：

```python
from random import random
import math

  
count = 0.0

a = 100000.0

for i in range(1, int(a) + 1):

x, y = random(), random()

d = math.sqrt(x * x + y * y)

if d <= 1:

count += 1

print((count / a) * 4)

print("2021310023 杨翼臣")

```

```python
from random import random
import math
count = 0
a=100000
for i in range(1,11):
	x,y =random(),random()
	d =math.sqrt(x*x +y*y)
if d<=1:
	count +=1
print((count/a)*4)
print("2021310023 杨翼臣")

```

## 科赫曲线的绘制
```python


```


