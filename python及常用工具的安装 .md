---
title:  python及常用工具的安装
date: 2015-02-26 18:48:10
tags:
categories: Python
---

# python及常用工具的安装


现在python一般情况下我们使用的2.7版本.系统自带的是2.6版本，可以在官方https://www.python.org/downloads/ 下载,它的安装还是很简单的。
tar包下载后可以直接解压，`configure、make、make install`即可。


#### python安装以后注意：

这里要强调一下的是安装Python后很有可能linux的yum就不能正常使用了。
一方面我们可以改下yum可执行文件的内容，文件位置为`/usr/bin/yum`

```bash
第一行#!/usr/bin/python
改成
#!/usr/bin/python2.4(python2.6)，也就是系统原来的python
```

另外一种是把新按装的Python可执行文件ln到/usr/local/bin这里，其它的也可以不用更改。
这样即不会影响到yum的使用，也不会影响新安装版本的使用。
如果有特殊的需求那就根据情况来设置环境变量吧。




