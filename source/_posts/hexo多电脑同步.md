---
title: hexo多电脑同步
copyright: true
date: 2019-04-29 11:17:45
tags: 
- hexo
- 同步
categories: Hexo
---

前段时间在部署这个博客的时候遇到了一个问题，当初是在公司的电脑上部署的，公司的电脑是windows系统，而我自己的电脑是Linux系统，那么怎么去解决这个同步的问题呢？当初想了一些办法，比如在两个系统上搭建两个博客？？？好像是不太现实的，这样做会很麻烦；再就是可以把本地文件上传到百度云或者拷到U盘，但是这样做不符合程序员的气质。看了网上的一些方法，总结了一个比较简单的做法，如下：

<!--more-->

##### 如何上传博客到github

在公司的电脑搭建并部署完之后，需要将项目上传到github上，在公司的电脑上执行如下命令：

```
git init   #git初始化
git remote add origin https://github.com/用户名/你的github名.github.io.git    #添加仓库地址
git checkout -b 分支名   #新建分支并切换到新建的分支
git add .   #添加所有本地文件到git
git commit -m ""     #git提交
git push origin 分支名   #文件推送到hexo分支
```

在这里执行命令必须字啊你创建的项目下执行，其中分支名自己创建，我自己创建的分支名为`hexo`，那么我要上传自己的项目命令如下：

```
git init 
git remote add origin https://github.com/WangDaXiaa/WangDaXiaa.github.io.git
git checkout -b hexo
git add .
git commit -m "上传本地部署文件"
git push origin hexo
```

执行完上面的之后，git会询问你的用户名和昵称，填写正确就可以将博客的工程文件上传到github的hexo分支下。

##### 如何从另一台电脑上下载博客工程

那么我在我自己的电脑上如何下载项目文件呢？很简单，首先在我自己的电脑上部署好Git和nodeJS环境，然后输入以下命令：

```
git clone -b 分支名 https://github.com/用户名/你的github用户
```

克隆下载完成之后，进入到你项目的文件夹，重新配置你的hexo环境，命令如下：

```
sudo npm install -g hexo-cli  #安装hexo，注意这里不需要hexo初始化，否则之前的hexo配置参数会重置
sudo npm install   #安装依赖库
sudo npm install hexo-deployer-git  #安装git部署相关配置
```

之后就如上文所示，创建撰写新的文章，并使用`sudo hexo g -d`命令创建并部署您的网站。值得注意的是，你的私钥文件需要携带，但极其不建议私钥文件放在github，建议放在U盘或网盘中，使用时下载即可。然后拷贝到相关目录下（Windows目录在`C:/Users/你的用户名/.ssh`目录、Mac在`~/.ssh/`目录，Ubuntu也在`~/.ssh/`目录下）即可正常部署您的网站。使用密钥时需注意权限，使用`chmod 密钥名称 700`命令即可更改权限，不更改权限无法使用密钥。

##### 写完博客之后如何再次同步

写完之后如何再次同步呢？执行如下命令：

```
git add .
git commit -m ""
git push origin 分支名
```

这样在我的电脑上的数据也同步到github上面了，那么第二天只需要到公司的电脑上执行`git pull`就行，这样我的电脑上面的数据就全部同步到了公司的电脑上面了，以后部署完后，再次执行以上命令到github上就行

##### 总结

总的来说，这样可以来回控制你的版本，只要善用git，就可以在任意电脑编写博客，控制你的项目。

所以，部署完项目后公司的电脑和我的电脑部署区别如下

公司的电脑：

```
git add .
git commit -m ""
git push origin 分支名
```

我自己的电脑：

```
git pull
hexo new 文章名
hexo clean 
hexo g -d
git add .
git commit -m ""
git push origin 分支名
```

公司的电脑：

```
git pull
hexo new 文章名
hexo clean
hexo g -d
git add .
git commit -m ""
git push origin 分支名
```



文章到此就结束了，参考文章见https://cloud.tencent.com/developer/article/1046404，谢谢大佬！

