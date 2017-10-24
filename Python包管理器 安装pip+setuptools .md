---
title: Python包管理器安装pip+setuptools
date: 2016-03-26 18:48:10
tags:
categories: Python
---

pip类似RedHat里面的yum,安装Python包非常方便装

#### 一、pip的安装（方法一）

```bash
cd  /usr/local/src
wget "https://pypi.python.org/packages/source/p/pip/pip-1.5.4.tar.gz#md5=834b2904f92d46aaa333267fb1c922bb" --no-check-certificate
tar -xzvf pip-1.5.4.tar.gz
cd pip-1.5.4
python setup.py install
```

如果上述出现`ImportError: No module named setuptools `的解决方案

```bash
cd  /usr/local/src
wget http://pypi.python.org/packages/source/s/setuptools/setuptools-0.6c11.tar.gz --no-check-certificate
tar zxvf setuptools-0.6c11.tar.gz
cd setuptools-0.6c11
python setup.py build
python setup.py install

如果安装这一步出现问题：

  "Compression requires the (missing) zlib module"  
<strong>RuntimeError: Compression requires the (missing) zlib module
出错原因：

提示的很清楚，缺少 zlib模块导致安装失败
# yum install zlib  
# yum install zlib-devel  
下载成功后，进入python2.7的目录，重新执行  
# make  
# make install  
  
此时先前执行的 软连接仍旧生效  
然后进入 setuptool目录
# python setup.py install
```

#### 二、pip安装（方法二）

```bash
cd /usr/local/src
wget https://bootstrap.pypa.io/get-pip.py --no-check-certificate -O ./get-pip.py
python get-pip.py
```

#### 三、pip更换国内源地址


```bash
cd 
mkdir .pip
vim .pip/pip.conf

[global]
index-url = http://pypi.douban.com/simple
[install]
trusted-host = pypi.douban.com
```


#### pip使用方法：


```bash
安装package

pip install package-name

setuptools
列出安装的package
pip freeze

安装特定版本的package

通过使用==, >=, <=, >, <来指定一个版本号。

$ pip install 'package-name<2.0'
$ pip install 'package-name>2.0,<2.0.3'
升级包

升级包到当前最新的版本，可以使用-U 或者 --upgrade

$ pip install -U package-name
卸载包

$ pip uninstall package-name
查询包

pip search package-name
```

