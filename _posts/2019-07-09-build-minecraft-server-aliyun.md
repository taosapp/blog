---
title: 在阿里云上建 MineCraft《我的世界》服务器
date: 2019-07-09 14:00:00
tags:
  - MineCraft
  - 游戏
---


>服务器环境 ubuntu 18.04

1. apt update
2. apt install default-jdk
3. mkdir minecraft
4. cd minecraft
5. 到 https://www.minecraft.net/en-us/download/server 复制 MineCraft 服务器包的链接
6. 下载：wget https://launcher.mojang.com/v1/objects/......../server.jar (上面复制的服务器包链接)
7. 运行：java -Xmx1024M -Xms1024M -jar server.jar nogui
8. 建好了