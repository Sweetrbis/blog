---
layout: '../../layouts/MarkdownPost.astro'
title: 'Astro搭建静态博客'
pubDate: 2023-3-9
description: '使用Astro搭建简洁漂亮的静态博客'
author: 'Caryon'
cover:
    url: 'https://i.imgtg.com/2023/03/09/YYQXj.png'
    square: 'https://i.imgtg.com/2023/03/09/YYQXj.png'
    alt: 'cover'
tags: ["Astro", "Blog"]
theme: 'light'
featured: true
---

![Astro](https://i.imgtg.com/2023/03/09/YYQXj.png)


## 这是一个基于前端的web框架Astro所搭建的博客

Astro JS 是一个用于构建高性能、内容为中心的网站的 web 框架。它可以让你使用你喜欢的 JavaScript web 框架（React，Svelte，Vue 等）来编写 UI 组件，然后在构建时将整个网站渲染为静态 HTML。这样，你就可以得到一个完全静态的网站，不需要加载任何 JavaScript。Astro 还支持多种前端工具，如 Tailwind CSS2，并且可以部署到任何地方，甚至是边缘服务器。Astro 最新版本是 2.0，它引入了一种新的前端架构（称为 Astro Islands），可以优化你的网站，让它加载速度提高 33%，JavaScript 减少 90%。

第一次看到这个博客是在telegram中的一个专门推荐博客的频道里看到的，刚看到的时候就感觉美观干净所以就想着自己也用来搭建一个博客看看。


![这是原博主的博客图](https://i.imgtg.com/2023/03/09/YYcPU.jpg)


看起来很干净，简洁于是我就跟着博主的教程一步一步的搭建，教程写的很详细，由于我是第一次尝试本地搭建，所以浪费了很长的时间。原博主的教程链接`https://yufengbiji.com/posts/astro-air-blog-guide`。


### 第一步使用模板创建仓库


打开<a href="https://github.com/austin2035/astro-air-blog">Astro Air Blog</a>仓库


![rt](https://i.imgtg.com/2023/03/09/YYYvq.jpg)


点击Use this template,然后在点Create a new repository


![创建仓库](https://i.imgtg.com/2023/03/09/YY9Or.jpg)


填写仓库的名字，填写完成再点Create repository from template,就创建好了你的博客仓库。


### 创建SSHkey


在开始菜单栏找到Git，打开`git bash` 输入```ssh-keygen```


![会出现接下来的提示](https://i.imgtg.com/2023/03/09/YY2LG.jpg)


可以看到第一个出现的是提示你SSHkey保存的路径如果不更改就是默认的路径，还有一个passphrase这个就是sshkey的验证密码。


![](https://i.imgtg.com/2023/03/09/YYXzI.jpg)

设置好就是这样了，可以到默认的路径去查看sshkey


![](https://i.imgtg.com/2023/03/09/YYuPD.jpg)


其中`id_rsa.pub`，就是公钥，可以使用`cat id_rsa`查看公钥的内容，`id_rsa`这个呢就是私钥，私钥不能泄漏出去。


接下来去到github的首页点击Setting


![](https://i.imgtg.com/2023/03/09/YYI9F.jpg)


接着设置全局使用的SSHkey，Title随便写key就是公钥的值


![](https://i.imgtg.com/2023/03/09/YYCT6.jpg)


填写好这里的步骤就完成了。


### 第二步克隆仓库到本地


来到你创建好的博客仓库


![n](https://i.imgtg.com/2023/03/09/YYjNM.jpg)


点击Code 在选择SSH，也可以选HTTPS。


打开电脑的终端（这里我推荐一个挺好用的终端工具`https://github.com/Eugeny/tabby`），接着输入`git clone 仓库的地址`，可以克隆到指定的路径自己cd到自己想要存放的路径在使用git clone就行。


需要注意的是Astro支持的node版本看看自己电脑上的node版本是不是支持，看着更新就行。


### 第三步安装依赖


接下来cd到克隆的过来的仓库根目录输入以下命令更新依赖。


```bash
npm install
```


### 第四步启动本地调试服务


到克隆到本地的博客目录运行以下代码


```bash
npm run dev
```


出现下图表示运行成功


![](https://i.imgtg.com/2023/03/09/YfMdb.jpg)


接着浏览器运行


```bash
https://localhost:3000
```


发现可以正常进入完成。


### 了解项目结构


了解目录的各个组成部分好修改博客内容


![](https://i.imgtg.com/2023/03/09/YfaOl.jpg)


这是各个目录的相关内容,下面是文章的结构。


![文章的结构](https://i.imgtg.com/2023/03/09/YfoNg.jpg)


博客网站的设置在`consts.js`中设置


![consts.js](https://i.imgtg.com/2023/03/09/YfqEB.jpg)


### 第五步把博客部署到Vercel


登录 vercel 后，点击 New Project 按钮，将你的博客仓库导入到 vercel 中。


![vercel部署](https://i.imgtg.com/2023/03/09/Yf5us.jpg)


这里只需要输入项目名称就行，填好之后直接部署。


之后vercel就会提供一个我们的博客链接不过有点长，可以绑定自己的域名


![](https://i.imgtg.com/2023/03/09/YfURa.jpg)


点击进行相关操作就行，需要在cloufare上添加一条记录A ，名称写上你的域名，地址填写`76.76.21.21`，还需要添加一个CNAME类型的记录，值填`cname-china.vercel-dns.com`指向vercel。


![CANME填写](https://i.imgtg.com/2023/03/09/YfW9S.jpg)

接下来应该就可以使用你的域名访问博客了。




















