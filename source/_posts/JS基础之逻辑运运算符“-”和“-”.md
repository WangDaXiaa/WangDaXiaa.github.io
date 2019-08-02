---
title: JS基础之逻辑运运算符“||”和“&&”
copyright: true
date: 2019-08-02 11:48:42
tags: 
- JavaScript
- 逻辑运算符
categories: JS基础
---

 本次要说的是逻辑运算符里面的“||”（逻辑或）和“&&”（逻辑与）

<!--more-->

##### 一、“||”（逻辑或）

从字面上来说，逻辑或只有在前后都是`false`的时候才返回`false`，否则返回`true`，如下：

```
console.log(true || false);   //true
console.log(false || true);   //true
console.log(true || true);    //true
console.log(false || false);   //false
```

但是，从深层意义上来说的话，却有另一番天地，看下面的代码：

```
console.log( 0 || 1);    //   1
```

显然我们知道前面`0`意味着`false`，后面的`1`意味着`true`，那么上面的结果应该是`true`，而事实返回的结果是`1`，在看下面代码：

```
console.log( 2 || 1);    //   2
```

我们知道，前面`2`是`true`，后面`1`也是`true`，那么返回结果是啥呢，事实上返回结果是`2`，继续看如下代码：

```
console.log( 'a' || 1);   // 'a'
```

同样的，前面`a`是`true`，后面`1`也是`true`，结果是`'a'`，接着看如下代码：

```
console.log( '' || 1 ); //前面''为false，后面1位true，返回结果为1
console.log( 'a' || 0); //前面'a'为true，后面0位false，返回结果为'a'
console.log( 'a' || 'b'); //前面'a'为true，后面'b'为true，返回结果为'a'
console.log( '' || 0); //前面''为false，后面0为false，返回结果为0
console.log( 0 || ''); //前面0为false，后面''为false，返回结果为''
```

由此可知：

##### 1、只要 `||`前面为`false`，不管`||`后面是`true`还是`false`，都返回`||`***后*** 面的值；

##### 2、只要 `||`前面为`true`，不管`||`后面是`true`还是`false`，都返回`||`*前* 面的值。

---

##### 二、”&&“（逻辑与）

从字面上来说，只有前后都是`true`的时候才返回`true`，否则返回`false`，如下：

```
console.log(true && false);  // false
console.log(true && true);  // true
console.log(false && false);  // false
console.log( false && true );  // false
```

然后，根据上面的经验，我们看看`&&`号前后，不单单是布尔类型的情况。如下：

```
console.log( '' && 0 );  //前面''是false，后面1是true，返回结果为''
console.log( '' && 0 );  //前面''是false，后面0是false，返回结果为''
console.log( 'a' && 1 );  //前面'a'true，后面1是true，返回结果为1
console.log( 'a' && 0 );  //前面'a'是true,后面是0是false，返回结果为0
console.log( 'a' && '' );  //前面'a'是true,前面0是false,返回结果为''
console.log( 0 && 'a' );  //前面0是false,后面是'a'是true，返回结果为0
console.log( 0 && '' );  //前面0是false,前面0是false,返回结果为0
```

这意味着：

##### 1、只要`&&`前面是`false`，无论后面是`true`还是`false`，结果都将返回*前* 面的值；
##### 2、只要`&&`前面是`true`，无论后面是`true`还是`false`，结果都将返回*后* 面的值；





本篇笔记到这里就结束了，谢谢阅读！

参考：<https://www.cnblogs.com/pigtail/archive/2012/03/09/2387486.html>



