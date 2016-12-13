---
title: 多台电脑同步博客
date: 2016-12-11 04:46:26
tags: [hexo]
---

hexo写博客,确实减少了维护博客投入的精力,但我们大多数不可能一直在同一台写博客,所以同步hexo生成的博客势在必行
<!--more--> <!--more-->
## 准备工作
这里假设, 原来更新博客的电脑是A, 新电脑是B

### A电脑准备

1. cd gitblog
2. git init
3. git remote add origin git@github.com:liujinlingchn/{{yourname}}.github.io.git
4. git checkout -b hexo  //新建分支并hexo切换到hexo分支
5. git add .
6. git commit -m "first commit"
7. git push origin hexo

到这步, 就已经把当前目录下的所有文件同步到hexo分支下了  
如果自己想过滤敏感信息, 自己设置.gitignore

### B电脑操作
1. 安装git
2. 安装nodejs
3. npm install -g hexo-cli
4. git clone -b hexo git@github.com:liujinlingchn/{{yourname}}.github.io.git
5. cd {{yourname}}.github.io
6. npm install
7. npm install hexo-deployer-git --save

此时, B电脑环境配置完毕, 和A电脑一样了, 可以发布文章并推送了  
每次在操作前, 要记得先更新下当前仓库
