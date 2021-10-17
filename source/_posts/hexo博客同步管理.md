---
title: 跨设备同步博客
date: 2021-10-17 16:27:51
tags: 学习笔记
---

## 1. 新电脑中的环境搭建

1. 安装 Node.js、git、hexo
2. clone远程仓库到本地 `git clone git@github.com:username/username.github.io.git`。
3. 本地生成网站并开启博客服务器：`hexo g & hexo s`。如果一切正常，此时打开浏览器输入`http://localhost:4000/`已经可以看到博客正常运行了。

## 2. 同步博客

1. `git pull`从远程仓库的hexo分支拉取最新的Hexo环境到本地，

2. 文章写完，要发布时，需要先提交环境文件，再发布文章。按以下顺序执行命令：

   ```
   git add .
   git commit -m "some descrption"
   git push origin hexo
   hexo g -d
   ```

   
