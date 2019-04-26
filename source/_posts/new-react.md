---
title: 从零开始搭建一个自己的React项目
copyright: true
date: 2019-04-23 09:48:41
tags:
- react
- 项目
---

### 1.安装nodeJS和npm

####         由于我们要使用npm这个包管理器，所以要安装nodeJS。现在版本的nodeJS已经集成了npm，所以我们只需要安装一次即可。

下载nodeJS，放到系统环境变量的路径里面，打开cmd，输入node -v（npm -v），如显示，安装正确。这样以后就可以在硬盘中任何一个位置使用npm命令。

### 2.安装VS Code及插件

<!--more-->

### 3.全局安装脚手架（作用：帮你配置开发环境）

```
npm install -g create-react-app
```

#####      注：

#####            如果npm安装不成功，先安装cnpm：

```
npm install -g cnpm --registry=https://registry.npm.taobao.org
```

##### 通过cnpm安装 cnpm install -g create-react-app(安装cnpm后，后续的命令npm都改为		cnpm)

### 4.创建工程项目

#### 	创建一个名字为antd-demo的React工程：

```
create-react-app antd-demo
```

#### 	进入项目文件夹：

```
cd antd-demo
```

### 5.开始运行项目

```
npm start
```

#### 	浏览器自动弹出项目初始页面





