---
layout: post
title: 在Windows上安装Jekyll
categories: Jekyll
description: Jekyll 安装
keywords: Jekyll
---

# 在Windows上安装Jekyll

## Jekyll介绍
> jekyll是一个简单的免费的Blog生成工具，类似WordPress。但是和WordPress又有很大的不同，原因是jekyll只是一个生成静态网页的工具，不需要数据库支持。但是可以配合第三方服务,例如Disqus。最关键的是jekyll可以免费部署在Github上，而且可以绑定自己的域名。

> Jekyll团队没有正式支持在Windows上使用Jekyll,官方不建议在Windows上使用Jekyll。

## 安装 Ruby

> 首先，点击下面的按钮，下载与您的系统架构（x86 / x64）相匹配的Ruby安装程序。

[Ruby Windows 下载 ](https://rubyinstaller.org/downloads/)

- 执行安装程序并执行安装步骤。当您进入下面的屏幕时，请确保检查“将Ruby可执行文件添加到PATH”框中。

<img src="/images/2017-07-22/rubu-install.png" width="100%" />

> 单击安装和Ruby将在几秒钟内安装。

## 安装 Ruby DevKit

>  Jekyll具有一些依赖性，即开箱即用，只提供原始源代码，为了使其成为完全功能的可执行文件，需要安装开发工具包。

[Ruby DevKit 下载 ](https://rubyinstaller.org/downloads/)

<img src="/images/2017-07-22/ruby-dev-kit.png" width="100%" />

- DevKit-mingw 是一个自解压档案，执行该文件时，会要求您提供文件的目的地，输入一个没有空格的路径，我建议简单一点，C:\RubyDevKit\。单击提取并等待，直到进程完成。

## 初始化 RubyDevKit
- 接下来，您需要初始化DevKit并将其绑定到您的Ruby安装。打开您最喜欢的命令行工具，并进入到您将DevKit解压缩到的文件夹。

```
cd C:\RubyDevKit
```

- 自动检测Ruby安装并将其添加到配置文件中以进行下一步。

``` sh
ruby dk.rb init
```

<img src="/images/2017-07-22/ruby-dk-rb-init.png" width="100%" />

- 安装DevKit，将其绑定到您的Ruby安装。


``` sh
ruby dk.rb install
```


## 安装 Jekyll


### 替换 RubyGems 镜像
> RubyGems 一直以来在国内都非常难访问到，在本地你或许可以翻墙，当你要发布上线的时候，你就很难搞了！

> 

``` sh
gem sources --add https://gems.ruby-china.org/ --remove https://rubygems.org/
gem sources -l
*** CURRENT SOURCES ***

https://gems.ruby-china.org
```

<img src="/images/2017-07-22/ruby-gems.png" width="100%" />

> Jekyll 本身是一个Ruby Gem的形式，它是一个易于安装的软件包。要安装Jekyll及其所有默认依赖项，请启动您习惯的命令行工具并输入以下命令


### install　bundler

``` sh
gem install bundler
```
<img src="/images/2017-07-22/gem-install-bundler.png" width="100%" />

### install　jekyll

``` sh
gem install jekyll
```

<img src="/images/2017-07-22/gem-install-jekyll.png" width="100%" />


## 以上安装成功，本地就可以快速搭建一个jekyll博客了

``` sh
jekyll new myblog  
```

<img src="/images/2017-07-22/jekyll-new-myblog.png" width="100%" />

## 进入上面新建的博客目录，并且启动博客服务，默认访问地址:
[http://localhost:4000](http://localhost:4000/)

``` sh
cd myblog  
jekyll serve  
```

<img src="/images/2017-07-22/jekyll-serve.png" width="100%" />

<img src="/images/2017-07-22/myblog-succ.png" width="100%" />
## 生成的博客文件

<img src="/images/2017-07-22/myblog.png" width="100%" />

##  jekyll 文档
[jekyll 基本用法 官方中文文档](http://jekyll.com.cn/docs/usage/)


