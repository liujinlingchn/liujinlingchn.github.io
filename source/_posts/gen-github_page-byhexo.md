---
title: 利用hexo生成github-page页面
date: 2016-12-02 09:54:36
tags: [hexo, github]
---

利用hexo编辑文章, 并上传到github生成静态网页的常见命令
<!--more--><!--more-->

# 添加一个网页
1. 生成一个markdown文章
```
hexo new [layout] 'page-name'
# 这个page-name是文章最终路径名, 而不是文章的标题, 文章的标题需要在最上方的title上修改
# 如果没有设置layout, 使用_config.yml中的default_layout参数代替
```
2. 执行上个命令后, 会提示md文件生成的位置, 编辑这个文件, 可以在tags编辑标签, 多个标签用[]
3. 生成
```
hexo generate
```
4. 测试
```
hexo server
# 运行后, 可以在本地访问127.0.0.1:4000 , 看是否是自己期望的样式, 如果不是重复步骤2
```
5. 如果是自己期望的, 就可以上传到github上
```
hexo deploy
```

# 常见问题
1. 如何在页面显示阅读全文  
需要在想隐藏内容上面加上一行  
```
<!--more--> <!--more-->
```
2. 如何在文章中加入图片
最简单的方式是在source中加入一个images文件夹, 然后在想要引入的地方使用  
看官网, 这样貌似不好, 但目前没发现, 有问题再修正
```
![](/images/img-name.jpg)
```
![](/images/vim键盘图.png)
