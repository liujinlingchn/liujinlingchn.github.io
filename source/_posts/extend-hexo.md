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
当然官网也提出了解决方案, 具体可以去官网查看, 如果你git用的比较熟, 还是推荐官网做法  

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

菜单配置包括三部分, 第一是菜单项(名称和连接), 第二是菜单项的显示文本, 第三是菜单项对应的图标

编辑主题配置文件, 修改一下内容

1. 设定菜单内容, 对应的字段是menu, 菜单内容的设置格式是: item name: link, 其中 item name 是一个名称,
这个名称并不直接显示在页面上, 而是用于匹配图标既翻译  

Next默认的菜单项有(标注❗️项表示需要手动创建这个页面):

键值|设定值|显示文本
---|---|---
home| home: /| 主页
archives| archives: /archives| 归档
categories| categories: /categories| 分类❗️
tags| tags: /tags| 标签页❗️
about| about: /about| 关于❗️
commonweal| commonweal: /404.html| 公益404❗️

2. 设置菜单项的显示文本.
在第一步中设置的菜单名称并不直接用于界面上的展示,Hexo在生成的时候使用这个名称去找对应的翻译,这些翻译文本在Next主题目录下的languages/{language}.yml中

3. 设定菜单项的图标, 对应的字段是menu_icons. 此设定格式是item name: icon name, 其中item name与上一步所配置的菜单名字对应, icon name 是Font Awesome图标的名字, 而enable可用于控制是否显示图标

```
menu_icons:
    enable; true
    home: home
    about: user
    categories: th
    tags: tags
    archives: archive
    commonweal: hearbeat
```

#### 设置头像

编辑站点配置文件, 新增字段avatar, 值设置成头像的链接地址, 其中头像的链接地址可以是:

地址|值
---|---
完整的互联网URL| https://example.com/avatar.png
站内地址|比如source/images/目录下, 配置为: avatar: /images/avatar.png

#### 增加评论
#### 增加百度统计
#### 增加阅读量
#### 增加搜索

## 主题配置

### 增加「标签」页面
1. 新建页面
```
hexo new page tags
```
2. 设置页面类型
编辑刚新建的页面, 将页面的类型设置为tags
```
title: 标签
date: 2016-12-17 17:02:23
type: "tags"
```
3. 修改菜单
在菜单中添加链接, 编辑主题配置文件,在menu中添加tags
```
menu:
    home: /
    archives: archives
    tags: /tags
```
4. 隐藏评论
如果开启了多说评论, 需要关闭的话, 添加comments, 并将值设置为false
```
title: 标签
date: 2016-12-17 17:02:23
type: "tags"
comments: false
```

### 代码高亮
Next 使用[Tomorrow Theme](https://github.com/chriskempson/tomorrow-theme)作为代码高亮, 共有5款主题可以选择, 可选值有normal, night, night blue, night bright, night eighties: 默认是normal  
更改highlight_theme字段, 设置成所喜欢的高亮主题

### 侧边栏社交链接
侧边栏社交链接包含两个部分, 第一是链接,第二是图标, 两者配置均在主题配置文件中
1. 链接放置在social字段下, 一行一个链接, 键值格式是 显示文本: 链接地址
```
social:
    GitHub: https://github.com/your-user-name
    微博: http://weibo.com/your-user-name
    # ...
```
2. 设定链接的图标,对应的字段是social_icons,其键值格式是 匹配键: Font Awesome, 匹配键与上一步所配置的显示文本相同
```
social_icons:
    enable: true
    GitHub: github
    微博: weibo
```

### 开启打赏
只需要在主题配置文件中填入微信和支付宝收款二维码图片地址即可开启该功能
```
wechat_subscriber:
  enabled: true
  qcode: /images/WechatRecvMoney.jpg
  description: 您的支持将鼓励我继续创作!
```

### 友情链接
编辑主题配置文件添加:
```
links_title: Links
links:
  MacTalk: http://macshuo.com/
```

### 多说评论显示UA
在每一条多说评论后显示评论者使用的代理信息,要启用此功能,需要配置duoshuo_info字段
```
duoshuo_info:
  ua_enable: true # 启用UA
  admin_enable: true # 是否展示"博主"文字
  user_id: 你自己的多说userid
  admin_nickname: 博主 # 要显示的字段
```
admin_enable用于展示「博主」文字,表明评论者是博主, 此字段需要user_id 和admin_nickname字段,user_id可以在登录多说后,并点击「我的主页」,user_id是网址最后面那串数字

### 搜索
由于Swiftype等搜索已不能用, 我目前使用Local Search
1. 安装 hexo-generator-searchdb
```
npm install hexo-generator-searchdb --save
```
2. 编辑站点配置文件, 新增以下内容到任意位置
```
search:
    path: search.xml
    field: post
    format: html
    limit: 10000
```

## SEO

### sitemap
给你的hexo站点添加sitemap网站地图
1. 安装hexo的sitemap网站地图生成插件
```
npm install hexo-generator-sitemap --save
npm install hexo-generator-baidu-sitemap --save
```
2. 编辑站点配置文件
```
# sitemap
sitemap:
    path: sitemap.xml
baidusitemap:
    path: baidusitemap.xml
```
3. 配置成功后, hexo编译后会在站点根目录下生成sitemap.xml和baidusitemap.xml

{% cq %} 更多内容请去[Next官网](http://theme-next.iissnan.com/)查看 {% endcq %}
