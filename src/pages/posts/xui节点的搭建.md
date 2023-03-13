---
layout: '../../layouts/MarkdownPost.astro'
title: 'XUI节点搭建'
pubDate: 2023-3-13
description: 'x-ui节点的搭建'
author: 'Caryon'
cover:
    url: 'https://i.imgtg.com/2023/03/13/fym9S.png'
    square: 'https://i.imgtg.com/2023/03/13/fym9S.png'
    alt: 'cover'
tags: ["xui", "cloudflare"]
theme: 'dark'
featured: true
---

![](https://i.imgtg.com/2023/03/13/fym9S.png)


搭建这个是因为发现我用的梯子体验速度不需要很快，就日常上telegram,twitter,youtube就没什么，刚好我还有一台闲置的rn机器。接下来就进入正题。


## 安装xui

首先进入xui的官网`https://github.com/vaxilu/x-ui`。你也可以直接输入以下一键安装命令：
```python
bash <(curl -Ls https://raw.githubusercontent.com/vaxilu/x-ui/master/install.sh)
```


也可以选择手动安装，这个你可以直接去官方github看。使用ssh客户端安装好之后会出现让你输入用户名密码，自定义端口，输入好了之后直接用你的ip加自定义的端口号即可。


![xui面板](https://i.imgtg.com/2023/03/13/fmeHB.jpg)


## 配置SSL证书


我使用的xui自带的脚本里面的申请ssl功能，输入上面的一键安装命令在输入16就是了。


首先申请证书需要以下条件：


1：你有一个域名。


2：cloudflare的帐号。


3：cloudflare绑定了你的域名。


首先到<a href='https://dash.cloudflare.com/'>Cloudflare的仪表盘</a>，接着点开User Profile > API Tokens。


![](https://i.imgtg.com/2023/03/13/fmp0L.jpg)


复制好之后，回到上面的步骤直接在脚本内申请ssl证书。按提示输入即可。输入好之后会生成公钥和私钥，公钥的地址是/root/cert/fullchain.cer，私钥匙的/root/cert/xxxx.key,就是带你域名的后缀为key的文件。


## cloudflare加速cdn


按上面步骤配置好之后，来到xui页面直接点到入站规则，我展示如下配置(面板设置记得也填写以下公钥，私钥的路径)：


![](https://i.imgtg.com/2023/03/13/fmtHt.jpg)


<a href='https://dash.cloudflare.com/'>Cloudflare</a>主页选择自己的域名（上面步骤xui绑定的域名）点击DNS，打开小云朵即可。


![](https://i.imgtg.com/2023/03/13/fm4Xx.jpg)

