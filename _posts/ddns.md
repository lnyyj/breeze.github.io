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


docker run -d --restart=always --net=host \
    -e "AKID=LTAI5tSW8pDcRdQHzaQFVHye" \
    -e "AKSCT=i6LWqINjJVSDrxG2qhIHTCQKCDNPCP" \
    -e "DOMAIN=dev.erbaner.com" \
    -e "REDO=30" \
    -e "TTL=600" \
    -e "TIMEZONE=8.0" \
    -e "TYPE=A,AAAA" \
    sanjusss/aliyun-ddns