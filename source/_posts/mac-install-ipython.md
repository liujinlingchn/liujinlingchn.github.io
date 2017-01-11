---
title: mac安装ipython
date: 2017-01-11 11:26:19
tags: [mac, python]
---

原来都是在公司的开发机上写代码, 有一次开发机有问题, 导致不能使用, 线下又没有环境, 就想着自己在线下也搭建一套,
这样开发机不能用, 至少还能线下测试, 一路brew install, 很顺利, 到安装ipython的时候, 死活装不上

<!--more--><!--more-->

报权限错误, sudo也不行, 心想root都不行了, 这尼玛神了, google了下, 原来mac下最新加了个SIP的东西, 现在有两种解决方法
1. 取消SIP
>重启电脑，按住Command+R(直到出现苹果标志)进入Recovery Mode(恢复模式)
左上角菜单里找到实用工具 -> 终端
输入csrutil disable回车
重启Mac即可
如果想重新启动SIP机制重复上述步骤改用csrutil enable即可
2. 基于用户的权限来安装
```
pip install ipython --user -U
```
