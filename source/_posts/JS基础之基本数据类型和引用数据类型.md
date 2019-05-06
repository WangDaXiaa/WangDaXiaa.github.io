---
title: JS基础之基本数据类型和引用数据类型
copyright: true
date: 2019-04-25 14:24:50
tags: 
- JavaScript
- 基础
- 数据类型
categories: JS基础
---

 JS有六种数据类型，我们可以把他们分为两类：基本数据类型和引用数据类,其中基本数据类型包括：String,Number,Boolean,Null,Undefined;引用数据类型包括：Object。

#### 下面我们来看两段代码：

```     
var a = 123;
var b = a;
a++;
console.log(a);   //124
console.log(b);  //123
```

<!--more-->

##### 上面这段代码定义了两个变量a和b，最后a的值和b的值是一样的

```
var obj = new Object();
obj.name = "孙悟空";
var obj2 = obj;
obj.name = "猪八戒"
console.log(obj.name);//猪八戒
console.log(obj2.name);//猪八戒
```

##### 为什么obj2.name的值变成了猪八戒呢？

首先JS中的变量都是保存到**栈**内存中的，基本数据类型的值直接在栈内存中存储，值与值之间是独立存在的，修改一个变量不会改变其他的变量；对象是保存到**堆**内存中的，每创建一个新的对象，就会在堆内存中开辟出一个新的内存空间。而变量保存的是对象的内存地址（对象的引用），如果两个变量保存的是同一个对象引用，当一个通过一个变量修改属性时，另一个也会受到影响。

---

###### 接下来我用两张图来解释一下

{% asset_img 1.png  %}

{% asset_img 2.png  %}

{% asset_img 3.png  %}




