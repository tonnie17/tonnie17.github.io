---
title: "迁移博客图床到腾讯云"
date: 2020-03-31T00:00:00+08:00
tags: [""]
categories: [""]
draft: false
---

最近访问尘封已久的博客，发现之前使用免费图床的链接都失效了，在没有备份的情况下丢失了数张图片，再次明白了一个道理：**免费的东西是最贵的**。因为博客大部分文章都有同步发表到知乎，所以不少图片还能找回来，为了避免图片再次丢失的风险，对比了数家云服务的产品和定价，最终决定把博客的图片迁移到腾讯云cos。

迁移步骤如下：首先把现存文章中带有的图片链接解析出来，批量下载到本地，再上传到腾讯云cos bucket，设置访问权限为公有读和私有写和防盗链，上传完毕后使用正则表达式把文章中的图片链接批量替换为cos的文件链接地址。
