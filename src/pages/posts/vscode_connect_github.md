---
layout: '../../layouts/MarkdownPost.astro'
title: 'Vscode同步更新到Github'
pubDate: 2023-3-9
description: '使用Vscode连接Github'
author: 'Caryon'
cover:
    url: 'https://i.imgtg.com/2023/03/09/YS0xC.png'
    square: 'https://i.imgtg.com/2023/03/09/YS0xC.png'
    alt: 'cover'
tags: ["Github", "Vscode"]
theme: 'dark'
featured: flase
---

![使用vscode直接同步编辑好的文件到github的仓库](https://i.imgtg.com/2023/03/09/YS0xC.png)


### 安装Git

首先去git的官网`https://git-scm.com/`安装git，这没什么好说的就是注意安装的路径不能出现中文。

### 安装Vscode

官网安装就好了

### 使用安装好的Git设置全局的用户名和邮箱地址

打开开始菜单找到`Git Bash`

输入以下命令
```
1|$ git config --global user.name "Your Name"

2|$ git config --global user.email "email@example.com"
```
应为Git是分布式版本控制系统，每个机器都必须有一个名字和Email地址，这样大家才知道是谁修改的，`其中Name和Email就是你github的用户名和邮箱。`

### 进行连接管理github仓库


打开`vscode`，`Ctrl + Shift + P`打开命令行输入git pull
![出现下图](https://i.imgtg.com/2023/03/09/Y0gax.jpg#pic_center)
就是第一个，然后会提示我们输入URL就是你仓库的链接，复制好之后直接粘贴就好了。

好了之后会提示我们将文件保存在哪里，随便放就是路径也不能出现中文。存好之后应该就可以了。

接着你可以直接创建一个新的文件，例如`xxx.md`，接着按下面图片走![这个](https://i.imgtg.com/2023/03/09/Y0mNj.jpg#pic_center)

`注意vscode的顶部中间会提示你输入ssh的密码，这是自己设置的。`

结束，接下来你就可以看到你仓库的文件就改变了。


