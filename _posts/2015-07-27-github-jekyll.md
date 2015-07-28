---
layout: post
category : Github
title: GitHub+Jekyll 搭建 blog
tags : [jekyll, tutorial]
---
{% include JB/setup %}

开博第一篇说下怎么用 GitHub+Jekyll 搭建 blog ~~

程旭媛开启碎碎念模式，慎点

----------------------------------------------------------我是萌萌哒分割线----------------------------------------------------------------------

## Overview

### What is Jekyll?

[Jekyll](http://jekyllrb.com/) 是一个简单的博客形态的静态站点生产机器。它有一个模版目录，其中包含原始文本格式的文档，通过一个转换器(如 Markdown)和我们的 Liquid 渲染器转化成一个完整的可发布的静态网站，你可以发布在任何你喜爱的服务器上。Jekyll 也可以运行在 GitHub Page 上，也就是说，你可以使用 GitHub 的服务来搭建你的项目页面、博客或者网站，而且是完全免费的。

### Examples

This website is created with Jekyll.

## Setup Tutorial

下面记录的是我搭建blog的过程哟~~(说了那么久才进入正题)

### 创建GitHub Pages

1.注册一个GitHub账号

2.新建一个REPOSITORY(仓库)

![img]({{site.image_url}}/{{ page.date | date: '%Y%m%d' }}/20150728113400.png)

3.创建一个repository，并命名为`username.github.io`，其中xxxx表示你的github帐号名，其他默认即可。

![img]({{site.image_url}}/{{ page.date | date: '%Y%m%d' }}/20150728113642.png)

4.创建完成后，进入项目，点击右下角`Settings`(设置)

![img]({{site.image_url}}/{{ page.date | date: '%Y%m%d' }}/20150728114819.png)

5.点击`Launch automatic page generator`(页面自动生成器)

![img]({{site.image_url}}/{{ page.date | date: '%Y%m%d' }}/20150728115418.png)

6.Pick a theme you like ,and then publish

![img]({{site.image_url}}/{{ page.date | date: '%Y%m%d' }}/20150728115800.png)

7.done，美美的主页就这么生成了~

![img]({{site.image_url}}/{{ page.date | date: '%Y%m%d' }}/20150728120015.png)


### 使用Jekyll

**1.安装ruby**

下载最新的[RubyInstaller](http://rubyinstaller.org/downloads)并安装(我下载的是rubyinstaller-2.1.6.exe)

安装过程中勾选 `Add Ruby executables to your PATH`(可选，用于从命令行模式执行Ruby。如果安装时没勾选，也可设置环境变量，path中配置C:\Ruby21\bin目录)
![img]({{site.image_url}}/{{ page.date | date: '%Y%m%d' }}/20150728152452.png)

然后在命令行终端下输入`gem update --system`来升级gem；

**2.下载最新的DevKit**

DevKit是windows平台下编译和使用本地C/C++扩展包的工具。它就是用来模拟Linux平台下的make,gcc,sh来进行编译。但是这个方法目前仅支持通过RubyInstaller安装的Ruby，并双击运行解压到C:\DevKit。然后打开终端cmd，输入下列命令进行安装：

    cd C:\DevKit

    ruby dk.rb init

    ruby dk.rb install

**3.安装Jekyll**

因为Jekyll是用Ruby编写的，最好的安装方式是通过RubyGems(gem):

`gem install jekyll`

并使用命令检验是否安装成功 

`jekyll --version`

如果安装过程中遇到以下错误

    ERROR: Could not find a valid gem 'jekyll' (>= 0), here is why:
    Unable to download data from https://rubygems.org/ - Errno::ETIMEDOUT:
    A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond. - connect(2) for "https://rubygems.org/" port 443 (https://api.rubygems.org/latest_specs.4.8.gz) 

那么有可能是因为被墙了或者网络不佳原因导致失败，现在淘宝的ruby工程师架设了rubygems的国内镜像。使用方法如下：

    $ gem sources --remove https://rubygems.org/
    $ gem sources -a https://ruby.taobao.org/
    $ gem sources -l
    *** CURRENT SOURCES ***

    https://ruby.taobao.org
    # 请确保只有 ruby.taobao.org
    
然后在运行gem命令就可以了！

    $ gem install jekyll

reference:[RubyGems 镜像](https://ruby.taobao.org/)
，[解决国内gem不能用的问题](http://www.haorooms.com/post/gem_not_use)

**4.安装Rdiscount，这个用来解析Markdown标记的包**

使用如下命令：`gem install rdiscount`

## Use Jekyll

1.安装Jekyll引导程序（Jekyll-Bootstrap）[网上参考教程](http://www.mceiba.com/develop/jekyll-introduction.html)

    $ git clone https://github.com/plusjade/jekyll-bootstrap.git username.github.io
    $ cd username.github.io
    $ git remote set-url origin git@github.com:username/username.github.io.git
    $ git push origin master

但是因为之前我们已经在GitHub上创建了Blog([网上参考教程](http://pigerla.com/learn-note/2013-06-12/create-a-blog-with-jekyll-bootstrap/))，so
先将repository根目录下所有文件删除，再使用Git命令

`git clone https://github.com/plusjade/jekyll-bootstrap.git`

将jekyll-bootstrap下载到本地xxxx.github.io文件上，打开jekyll-bootstrap文件夹，并将里面所有的文件拷贝出来放在根目录下，并把jekyll-bootstrap文件夹删除。



2.本地运行

    $ cd USERNAME.github.io
    $ jekyll --serve

在浏览器预览 http://localhost:4000，见到如下界面

![img]({{site.image_url}}/{{ page.date | date: '%Y%m%d' }}/1360135507_2641.jpg)

更多使用介绍，请看官方文档

