---
title: 扩展hexo
date: 2016-12-14 10:45:05
tags: [hexo, Next]
---

hexo默认主题使用landscape, 个人觉得不太好看, 但是hexo支持自定义主题, 也可以使用别人定制好的,
可以去[hexo主题](https://github.com/hexojs/hexo/wiki/Themes)寻找自己喜欢的主题, 个人使用Next主题
<!--more--><!--more-->
## 使用Next主题
官方的使用方法是在themes目录下直接clone [Next源码](https://github.com/iissnan/hexo-theme-next themes/next), 但这样有个问题, 就是多PC更新时的主题同步, 所以推家大家去官网上直接下载压缩包,
当然官网也提出了解决方案, 具体可以去官网查看  

### 启用主题
打开站点配置文件, 找到theme字段, 并将其值改为next  
切换主题后, 最好使用hexo clean来清除Hexo的缓存

### 验证站点
hexo s --debug, 来查看站点是否正确运行

### 主题设定

#### 选择Scheme
Scheme是Next提供的一种特性, 借助于Scheme, 可以提供多种不同的外观, 目前Next支持三种Scheme, 他们是:

- Muse 默认Scheme, 这是Next最初的版本
- Mist Muse的紧凑版本
- Pisces 双栏Scheme, 目测这个用的最多

Scheme的切换可以通过更改主题配置文件来修改, 搜索scheme关键字, 打开自己喜欢的注释即可

#### 设置菜单

未完待续
