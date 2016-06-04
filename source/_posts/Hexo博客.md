---
title: Hexo博客
date: 2016-06-01 17:35:32
tags:
---


```
在自己的GitHub账号下创建一个新的仓库，命名为username.github.io（username是你的账号名)。

在这里，要知道，GitHub Pages有两种类型：User/Organization Pages 和 Project Pages，而我所使用的是User Pages。

简单来说，User Pages 与 Project Pages的区别是：

1.User Pages 是用来展示用户的，而 Project Pages 是用来展示项目的。

2.用于存放 User Pages 的仓库必须使用username.github.io的命名规则，而 Project Pages 则没有特殊的要求。

3.User Pages 将使用仓库的 master 分支，而 Project Pages 将使用 gh-pages 分支。

4.User Pages 通过http(s)://username.github.io 进行访问，而 Projects Pages通过http(s)://username.github.io/projectname 进行访问。
```

### 使用Hexo搭建git page

安装node.js

``` 
hexo init

hexo g
hexo s

```
搭建起本地的hexo博客了,到浏览器输入localhost:4000看看。

编辑_config.yml
```
deploy:
  type: git
  repo: https://github.com/qilin7536/qilin7536.github.io.git
  branch: master
  message: [message]
```
然后
```
hexo g
hexo d
```
> hexo3.0中 type：github已经不行 需要改为git 改过后
运行下npm install hexo-deployer-git --save
再 hexo g hexo d

### 使用Hexo新建文章    
```
hexo new "postName" #新建文章

hexo new "postName"会在..\source\_posts目录下生成一个markdown文件：postName.md

可以使用一个支持markdown语法的编辑器来编辑该文件。

编辑完文章进行生成和部署：
hexo g
hexo d
```

### 使用其他主题


如果想要使用其他主题，可以使用git clone将别人的主题拷贝到..\themes下，然后将_config.yml中的theme: landscape改为对应的主题名字。


### 优化部署管理
建立GitHub Pages的仓库，建两个分支，一个用来存放Hexo网站的文件，一个用来发布网站。


* 创建仓库，qilin7536.github.io
* 创建两个分支：master 与 hexo
* 设置hexo为默认分支
* 建立qilin7536.github.io文件夹，通过Git bash依次执行npm install hexo、hexo init、npm install 和 npm install hexo-deployer-git;
* 使用git clone git@github.com:qilin7536/qilin7536.github.io.git拷贝仓库，将.git文件夹拷贝到hexo的文件夹中
* 在qilin7536.github.io文件夹中Git bash（此时当前分支应显示为hexo）
* 修改_config.yml中的deploy参数，分支应为master；
* hexo3.0中 type：github已经不行 需要改为git 改过后，运行下npm install hexo-deployer-git --save
* 依次执行git add .、git commit -m “…”、git push origin hexo提交网站相关的文件(这里只需要将必要的文件（source文件夹，_config.yml）git add便可以，因为git add .会有部分文件名太长导致无法全部git add)

* 执行hexo g,hexo d 生成网站并部署到GitHub上。
