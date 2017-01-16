---
title: hexo错误汇总
date: 2017-01-16 11:31:08
tags: [hexo]
---

hexo的一些错误情况汇总

# 升级nodejs后hexo dtrace-provider模块报错
错误输出如下
```
Error: The module
'/usr/local/lib/node_modules/hexo-cli/node_modules/dtrace-provider/build/Release/DTraceProviderBindings.node'
was compiled against a different Node.js version using
NODE_MODULE_VERSION 48. This version of Node.js requires
NODE_MODULE_VERSION 51. Please try re-compiling or re-installing
the module (for instance, using `npm rebuild` or`npm install`).
```
解决方案如下
```
$ npm install hexo --no-optional
if it doesn't work
try
$ npm uninstall hexo-cli -g
$ npm install hexo-cli -g
```

