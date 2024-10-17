---
title: 博客的创建
description: "This post is for testing the draft post functionality。"
publishDate: "2024/10/14"
tags: ["blog"]
---

    这里记录了自己创建博客的一些历程。
    博客中不仅仅是关于开发相关的文章，同时也会包含自己的一些想要记录的东西。

## 域名注册

因为在国外的网站购买域名会涉及到信用卡问题，所以选择了[阿里云](https://wanwang.aliyun.com/domain/tld#.com)。
不过可以在国外购买域名，建议还是在国外买，域名会比国内多而且方便。

## 构建服务器

我个人使用[CloudFlare](https://dash.cloudflare.com/)，因为免费快捷。
注册完成后，需要将已实名的域名添加进CF中。[CF DNS Setup](https://developers.cloudflare.com/dns/zone-setups/full-setup/setup/#review-dns-records) 

## 博客框架

个人选择了[Hexo](https://hexo.io/zh-cn/docs/)，因为其免费，简单快捷，主题丰富。
仅仅只写博客完全够用，感觉没有必要花太多的精力在复杂的框架上。

## 部署

使用了CF的[Pages](https://developers.cloudflare.com/pages/get-started/git-integration/)功能，可以一键连接github中的仓库。
并在构建命令中添加上自己的命令，就可以完成部署前的准备工作。
每当github中的代码有更新，CF会自动部署。
