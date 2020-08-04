---
author: 小郭
title: 手把手教你用 GitHub+PicGo+jsDelivr 搭建免费的博客图床
img: 'https://cdn.jsdelivr.net/gh/GuoJingtao-1997/PicBed/BlogImg/20200517125150.jpg'
cover: false
toc: true
mathjax: false
top: true
categories: 图床
tags:
  - GitHub
  - PicGo
abbrlink: 1d23231
date: 2020-05-16 00:00:00
coverImg:
password:
summary:
---
> 利用 *GitHub* 和 *PicGo* 可以很方便的搭建私人图床

## 特点

* 实现图片文件的固定链接访问，使 `Markdown` 格式文章插入图片更方便

* `GitHub` 仓库搭建图床操作简单且无需额外付费

* [jsDelivr](https://www.jsdelivr.com/) `CDN` 加速访问，解决国内 `GitHub` 访问速度慢的问题

## GitHub

### 注册 GitHub 账号

在配置 `GitHub` 仓库之前我们要先拥有一个 `GitHub` 账号，如果你还没有的话，不妨点击[这里](https://github.com/join "github注册链接")前往注册。

### 创建 GitHub 仓库

注册完毕后我们会看到以下界面，这里我们点击 `New` 创建一个新仓库 

![GitHub 界面](https://cdn.jsdelivr.net/gh/GuoJingtao-1997/PicBed/BlogImg/20200517125202.jpg)

点击 `New` 之后页面会跳转至如下界面，在该界面我们需要对仓库进行配置，具体填写步骤可参考图片内的指引  

![配置仓库属性](https://cdn.jsdelivr.net/gh/GuoJingtao-1997/PicBed/BlogImg/20200517153638.jpg)

> **注：** 仓库类型如果选为私有，则在 *PicGo* 的相册中将看不到上传后的图片，建议设为公有，因此我们在上传图片到图床时要注意保护个人隐私  

设置完毕后点击下方按钮即可创建仓库，仓库的界面如下图

![仓库界面](https://cdn.jsdelivr.net/gh/GuoJingtao-1997/PicBed/BlogImg/20200517181126.jpg)

### 生成 token

在使用 `GitHub` 图床时我们需要先生成一个 [token](https://baike.baidu.com/item/Token/2615248),生成过程也十分简单。

首先我们点击 `GitHub` 首页的用户头像并点击 `Settings` 进入设置界面，如图

![Settings 界面](https://cdn.jsdelivr.net/gh/GuoJingtao-1997/PicBed/BlogImg/20200517204558.jpg)

进入之后我们下拉至底部，点击 `Developer settings` 并选择第三个选项后，点击右上角的 `Generate new token` 进入配置界面，根据下图完成 `token` 的配置，并下拉至底部点击 `Generate token` 完成 `token` 的生成，之后即可直接将 `token` 复制到 `PicGo` 中。

![配置 token](https://cdn.jsdelivr.net/gh/GuoJingtao-1997/PicBed/BlogImg/20200517125204.jpg)

![生成的 token](https://cdn.jsdelivr.net/gh/GuoJingtao-1997/PicBed/BlogImg/20200517125206.jpg)

> **注：**  *token* 只出现一次，因此我们需将其备份起来

## PicGo

### 下载 PicGo

在使用 `PicGo` 前我们需要先到以下链接去下载,建议选择最新的稳定版本，`Beta` 版本稳定性相对没那么好。

https://github.com/Molunerfinn/PicGo/releases

如果不是下载安装包，想看源码的话，可以选择 `git clone https://github.com/Molunerfinn/PicGo.git` 克隆到本地

> **注：** `Mac` 用户选择 `.dmg` 下载， `Windows` 用户选择 `.exe` 下载。

![下载界面](https://cdn.jsdelivr.net/gh/GuoJingtao-1997/PicBed/BlogImg/20200518210625.jpg)

安装完毕，打开后会以小图标形式显示在屏幕右下角，点击小图标即可打开详细窗口，窗口界面还是十分简洁大方的。

![PicGo 小图标](https://cdn.jsdelivr.net/gh/GuoJingtao-1997/PicBed/BlogImg/20200518210623.jpg)

### 配置 PicGo

之后打开 `PicGo` 选择 `GitHub` 图床进行配置

![PicGo 界面](https://cdn.jsdelivr.net/gh/GuoJingtao-1997/PicBed/BlogImg/20200517125205.jpg)

* 仓库名的格式为 `用户名/仓库` 比如我之前创建了一个 `PicBed` 的仓库，则我需要填入 `GuoJingtao-1997/PicBed`， 分支名一般填写 `master`，`token` 则输入之前我们已生成并备份好的 `token` 

* 指定存储路径可选填，若填写则上传图片时 `GitHub` 仓库会自动创建新文件夹来保存图片

* 设置自定义域名会使 `PicGo` 生成的访问链接为 `自定义域名+文件名` 的格式，而由于国内访问 `GitHub` 的速度比较慢，因此我们需要使用 `jsDelivr CDN` 进行加速，将自定义域名设置为 `https://cdn.jsdelivr.net/gh/用户名/图床仓库名` 即可

### 使用 PicGo

接下来就可以愉快的开耍 `PicGo` 啦，选择相应的格式并将图片拖至相应位置即可上传，之后在相册中选择自己想要的格式并点击相应的图片下方最左侧的按钮即可复制图片的链接，上传图片的格式一般采用 `.jpg`，同时为了减轻 `GitHub` 服务器的压力，建议在上传图片前可以对其进行压缩，下面提供一个可进行无损压缩的网站供大家使用

https://tinypng.com/

![PicGo 相册界面](https://cdn.jsdelivr.net/gh/GuoJingtao-1997/PicBed/BlogImg/20200517153639.jpg)

> **注：** 有时会出现上传失败的情况，这时可以尝试将 *PicGo设置* 里的 *设置Server* 关闭后再打开或者重启 *PicGo*

大家可以自行探索 `PicGo` 的其他用法，希望本文的内容对大家有所帮助，也欢迎大家在下方留言指出其中错误或遗漏的地方。