
---
layout: post
title: "ddns"
author: "lnyyj"
header-img: "img/post-bg-halting.jpg"
header-mask: 0.3
tags:
  - ddns
  - ddns
---



## gitlab push

### error: RPC failed; HTTP 413 curl 22 The requested URL returned error: 413 

- 1. 首先打开命令行全局配置git：
    git config –global http.postBuffer 524288000（可能有效可能无效）
    
- 2. git所在服务器原来是直接访问的后来改成nginx转发后访问啦，于是想可能是nginx配置有问题

    解决方法：打开nginx.conf中的http配置段中加入
    client_max_body_size 100m;
    重启nginx后问题解决

