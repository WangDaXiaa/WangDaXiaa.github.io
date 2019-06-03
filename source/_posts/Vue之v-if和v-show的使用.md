---
title: Vue之v-if和v-show的使用
copyright: true
date: 2019-05-23 11:14:37
tags: 
- Vue
- 基础
categories: Vue
---

最近正在学习Vue的一些基础知识，今天学到了两个有点意思的指令，功能有点类似，特此记录一下~~

<!--more-->

我们先来看一张图：

{% iframe /iframe/Toggle.gif %}

点击上面的`toggle`切换按钮，下面的两个标签显示的是同样的效果，上面的一个是用`v-if`来控制的，下面的是用`v-show`来控制的，那么有什么区别呢？下面我们先来看他们的代码实现：

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
</head>
<body>
    <div id="app">
        <input type="button" value="toggle" @click = "toggle">
        <h3 v-if="flag">这是用v-if控制的元素</h3>
        <h3 v-show="flag">这是用v-show控制的元素</h3>
    </div>
    <script>
        var vm = new Vue({
            el: '#app',
            data: {
                flag: true
            },methods: {
                toggle(){
                    this.flag = !this.flag;
                }
            }
        })
    </script>
</body>
</html>
```

`v-if`的特点是：每次都会重新删除或创建元素。所以我们看到的第一句话“这是用v-if控制的元素”，每次都是删除了之后再重新创建的。

`v-show`的特点是：每次不会重新进行dom的删除和创建操作，只是切换了元素的`display:none`样式。所以第二句话“这是用v-show控制的元素”，是没有被删除的，而是被隐藏然后再显示的。

因此`v-if`有较高的切换性能消耗，`v-show`有较高的初始渲染消耗。如果元素涉及到频繁的切换，最好不要使用`v-if`，推荐使用`v-show`；如果元素可能永远也不会被显示出来给用户看到，则推荐使用`v-if`。



这篇短小的笔记就到此结束，谢谢阅读！

