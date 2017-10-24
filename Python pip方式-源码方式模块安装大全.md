---
title: Python pip方式-源码方式模块安装大全
date: 2016-05-16 18:48:10
tags:
categories: Python
---


###  Python pip方式-源码方式安装所有模块


#### 1. pip install virtualenv

```bash
virtualenv通过创建独立Python开发环境的工具, 来解决依赖、版本以及间接权限
问题. 比如一个项目依赖Django1.3 而当前全局开发环境为Django1.7, 版本跨度过大, 导致不兼容使项目无法正在运行, 使用virtualenv可以解决这些问题.

$ pip install virtualenv
//或者由于权限问题使用sudo临时提升权限
$ sudo pip install virtualenv
```

参考地址：[Python--Virtualenv简明教程](http://www.jianshu.com/p/08c657bd34f1)

#### 2. pip install gevent

```bash
安装gevent
从官网下载最新稳定版1.0.2
https://pypi.python.org/pypi/gevent#downloads
使用下面的命令
wget --no-check-certificate https://pypi.python.org/packages/source/g/gevent/gevent-1.0.2.tar.gz#md5=117f135d57ca7416203fba3720bf71c1
tar zxf gevent-1.0.2.tar.gz
cd gevent-1.0.2
python setup.py install

第二种方法：
yum install -y  libevent-dev
pip install gevent
pip install greenlet
```
#### 3. pipreqs生成任何基于项目进口PIP requirements.txt文件

 第三方类库（pip install -r requirements.txt）
 
 ```bash
 pip install pipreqs
 ```
 
 ```bash
 用法

使用：
    pipreqs [options] <path> 

选项：
    --use-local使用ONLY本地包信息而不是查询PyPI 
    --pypi-server <url>使用自定义PyPi服务器
    --proxy <url>使用Proxy，参数将被传递请求库。您还可以
                          在终端中设置环境参数：
                          $ export HTTP_PROXY =“http://10.10.1.10:3128” 
                          $ export HTTPS_PROXY =“https://10.10.1.10:1080” 
    --debug打印调试信息
    -忽略<dirs> ...忽略额外的目录
    --encoding <charset>
 ```
 
 参考地址：[pipreqs ](https://github.com/bndr/pipreqs)
 
#### 4. pip2.7 install gevent 

**1. ImportError: cannot import name HTTPSHandler  **

```bash
[root@viki ~]# pip2.7 install gevent
Traceback (most recent call last):
  File "/usr/local/bin/pip2.7", line 8, in <module>
    load_entry_point('pip==1.5.4', 'console_scripts', 'pip2.7')()
  File "build/bdist.linux-x86_64/egg/pkg_resources.py", line 318, in load_entry_point
  File "build/bdist.linux-x86_64/egg/pkg_resources.py", line 2221, in load_entry_point
  File "build/bdist.linux-x86_64/egg/pkg_resources.py", line 1954, in load
  File "/usr/local/lib/python2.7/site-packages/pip-1.5.4-py2.7.egg/pip/__init__.py", line 10, in <module>
    from pip.util import get_installed_distributions, get_prog
  File "/usr/local/lib/python2.7/site-packages/pip-1.5.4-py2.7.egg/pip/util.py", line 18, in <module>
    from pip._vendor.distlib import version
  File "/usr/local/lib/python2.7/site-packages/pip-1.5.4-py2.7.egg/pip/_vendor/distlib/version.py", line 14, in <module>
    from .compat import string_types
  File "/usr/local/lib/python2.7/site-packages/pip-1.5.4-py2.7.egg/pip/_vendor/distlib/compat.py", line 31, in <module>
    from urllib2 import (Request, urlopen, URLError, HTTPError,
ImportError: cannot import name HTTPSHandler 

解决方法：
需要在安装python前，安装OpenSSl。
命令如下：

Centos:
yum install openssl openssl-devel -y

Debian or Ubuntu:
apt-get install libssl

之后，再重新编译安装下 Python即可。
```


