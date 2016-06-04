---
title: Hexo博客
date: 2016-06-01 17:35:32
tags:
---


> respon 的名字：username.github.io，
在master分支的index.html


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
  repo: https://github.com/zippera/zippera.github.io.git
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