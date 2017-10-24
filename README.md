
## Python语言来源

Python是一种解释型、面向对象、动态数据类型的高级程序设计语言。
Python由`Guido van Rossum`于1989年底发明，第一个公开发行版发行于1991年。
像Perl语言一样, Python 源代码同样遵循 GPL(GNU General Public License)协议。

## python语言的对比

```bash
C 类型：编译为机器码       运行速度：非常快  代码量：非常多
Java类型： 编译为字节码  运行速度：  快     代码量： 多
Python类型： 解释执行     运行速度：慢      代码量：少
```

## Python语言介绍：

Python 是一门简单易学且功能强大的编程语言。它拥有高效的高级数据结构，并且能够用简单而又高效的方式进行面向对象编程。`Python`优雅的语法和动态类型，再结合它的解释性，使其在大多数平台的许多领域成为编写脚本或开发应用程序的理想语言。

你可以自由地从 Python 官方点: `http://www.python.org`，以源代码或二进制形式获取 Python 解释器及其标准扩展库，并可以自由的分发。此站点同时也提供了大量的第三方 Python 模块、程序和工具，及其附加文档。

你可以很容易的使用 `C 或 C++`（其他可以通过 C 调用的语言）为`Python`解释器扩展新函数和数据类型。`Python`还可以被用作定制应用程序的一门扩展语言。
可以参考入门文档读者介绍了 [Python语言及其体系相关的基本知识与概念](http://www.liaoxuefeng.com/wiki/001374738125095c955c1e6d8bb493182103fac9270762a000)。
在学习实践中结合使用 Python 解释器是很有帮助的，不过所有的例子都是完整的，所以本手册亦可离线阅读。

[Python最佳入门学习文档](http://www.pythondoc.com/pythontutorial3/appetite.html)


## TOC

效果如下：
[TOC]



## Python开发新人指南

### 基础技能

```
* 熟练掌握Python并具有良好的编码风格（参考：Google Python 风格指南）
* 懂Bash，常用的脚本要会写，做到会利用grep、awk、sed、sort、uniq等命令实现文本操作(视频资源：Shell高级编程)
* 懂Apache、Nginx等服务端常见的配置（推荐电子书：鸟哥的Linux私房菜）
* 掌握基本的HTML、Javascript知识，掌握一种Python Web框架
* 懂MySQL基本的CRUD操作和慢查询日志、EXPLAIN优化SQL查询方法（视频资源：MySQL数据库多种优化生产方案）
* 知道Redis基础命令（参考：命令参考）
* 了解一种分布式消息队列：RabbitMQ、Kafka等
* 了解HTTP协议，理解REST风格API设计
``` 

### 参考书籍

```
* 初学Python必备《Learn Python The Hard Way》
* 学习Python技巧必备《Python Cookbook》
* 快速上手bash脚本语言《bash Pocket Reference》
* 系统开发必备参考《The Linux Programming Interface》
* 网络编程基础读物《UNIX网络编程卷I：套接字联网API》
* 实战Linux运维推荐读物《高性能Linux服务器构建实战》
* Linux/Unix文化经典读物《UNIX编程艺术》
```

### Python学习资料：

```
* 《Learn Python The Hard Way》http://vdisk.weibo.com/s/FNWd70pFyC8S  （但最靠谱的阅读是经常阅读官方手册）
* 仔细阅读 Python官方文档Glossary章节、Built-in Functions
``` 

### 仔细思考：

```
* dict、list分别有哪几种初始化方式
* tuple、dict、list之间如何相互转换
* mutable与immutable之间的差别，并说出python内置类型都分别属于哪一类
* 异常类型结构，try, except, else, finally之间的使用方式
* unicode与str的差别，以及如何转换

以上都了解后，进阶思考：

* Python闭包以及何时使用
* 静态方法和类方法，都在何时使用
* 元类是什么
* __call__、__init__、__new__ 有什么特性和区别
* 哪些场景下使用回调函数
* 在什么情况下使用mixin
* functors、itertools中定义的方法主要是做什么的
* 什么时候要用到weakref中的方法
* yield通常在什么情况下使用
* 装饰器，什么时候使用它
* __future__模块是用来做什么的，有哪些用法
```



## 根据自己所学的整理下Python入门相关的文档分享与故障总结



### 1、`Centos6.9 install Python 2.7`

```bash
CENTOS 6.X 系列默认安装的 Python 2.6 ，目前开发中主要是使用 Python 2.7 ，这两个版本之间还是有不少差异的，程序在 Python 2.6 下经常会出问题。

比如： re.sub 函数 ，2.7 支持 flags 参数，而 2.6 却不支持。
所以，打算安装 Python 2.7 来运行 Flask 应用程序，但 2.6 不能删除，因为系统对它有依赖。

1、安装 sqlite-devel

因为 Flask 应用程序可能使用能 Sqlite 数据库，所以这个得装上（之前因为没装这个，导致 Python 无法导入 sqlite3 库。
当然，也可以从源码编译安装。
yum install sqlite-devel -y

2、安装 Python 2.7
wget https://www.python.org/ftp/python/2.7.8/Python-2.7.8.tgz
tar xf Python-2.7.8.tgz
cd Python-2.7.8
./configure --prefix=/usr/local
make && make install
安装成功之后，你可以在 /usr/local/bin/python2.7 找到 Python 2.7。

3、安装 setuptools + pip
这里需要注意，一定要使用 python2.7 来执行相关命令。

# First get the setup script for Setuptools:
wget https://bitbucket.org/pypa/setuptools/raw/bootstrap/ez_setup.py
# Then install it for Python 2.7 :
python2.7 ez_setup.py
# Now install pip using the newly installed setuptools:
easy_install-2.7 pip

# With pip installed you can now do things like this:
pip2.7 install [packagename]
pip2.7 install --upgrade [packagename]
pip2.7 uninstall [packagename]
4、使用 virtualenv

# Install virtualenv for Python 2.7 and create a sandbox called my27project:
pip2.7 install virtualenv
virtualenv-2.7 my27project

# Check the system Python interpreter version:
python --version
# This will show Python 2.6.6

# Activate the my27project sandbox and check the version of the default Python interpreter in it:
source my27project/bin/activate
python --version
# This will show Python 2.7.X
deactivate
基本就是这些了，网上很多教程都说要做软链接，但我感觉那样做或多或少会对系统有一些未知的影响。这个方法能尽量保持系统的完整性，很多自带 Python 程序其实在头部都指定了 #!/usr/bin/python ，所以它们用的其实是 Python 2.6 ，而不是新安装的 Python 2.7 。

安装搭建最好统一初始化实现，写成脚本安装实现。
```

### 2、Python入门心得一个新手的一些重点标记


```bash
* 失效与换行
r'...'让转义符失效

 '''...'''让回车可以直接换行
* 中文问题
文字符串在Python环境下遇到 UnicodeDecodeError，这是因为.py文件保存的 格式有问题 可以在第一行添加注释

-- coding: utf-8 -- 如果是用notepad写的话应该加上来让其可以读取中文 而u是为了注明这是中文
因此一般用python命令行就只用使用u 但目前用的版本可以直接翻译 可以两者都不要。

* 计算
* 整数和浮点数混合运算的结果就变成浮点。
* 关于list
数字不需要引号。list里规则还是要讲规则，但是不一定和平时效果一样。元素之间还需要用逗号隔开。

在list中插入元素时，-1是按原来的排列正向插入的。
举例：

L=[3,4,5]
L.insert(-1,6)
print L
[3,4,6,5]
list连删两个元素，顺序要重算。

* 缩进
具有相同缩进的代码被视为代码块。
if条件句的代码块要空四格。（貌似很多条件句都是）

* +
a+3=a3此种情况两者皆以字符形式出现。

* 三者比较
dict，list，tuple皆为集合，因此都能用len求和。
dict{},访问时用[],.get时用()
list[],访问时用[],操作(添加，删除，等等)时用（）
tuple(),访问时用[],且不能改变

* set的重点
set的内部结构和dict很像，唯一区别是不存储value，因此，判断一个元素是否在set中速度很快。
set存储的元素和dict的key类似，必须是不变对象，因此，任何可变对象是不能放入set中的。

* 关于循环
Python 的 for循环不仅可以用在list或tuple上，还可以作用在其他任何可迭代对象上。

点都比较杂，但都是自己入门这门语言的一点经验，希望对大家有帮助，如果有错误也欢迎纠正~

转载慕课网：链接：http://www.imooc.com/article/17236
```
```bash

```
### 1、安装依赖包`numpy scipy sklearn  matplotlib  pandas  sparkit-learn`

```bash
安装依赖包
yum -y install pycairo pycairo-devel  gcc-c++ lapack blas lapack-devel blas-devel
pip install numpy scipy sklearn matplotlib pandas sparkit-learn

numpy 如果安装不成功 可试着用 easy_install-2.7 numpy，其他包安装超时一样可以用easy安装
其他包都依赖numpy 这个包
pip install scipy sklearn matplotlib pandas sparkit-learn
https://pypi.python.org/pypi/sparkit-learn#downloads
```
### 2、安装 `xlrd , xlwt`模块

```bash
安装xlrd . xlwt模块 下载地址：

wget https://pypi.python.org/packages/source/x/xlrd/xlrd-0.9.4.tar.gz#md5=911839f534d29fe04525ef8cd88fe865
tar -zxvf xlrd-0.9.4.tar.gz
cd xlrd-0.9.4
python setup.py install
python
import xlrd

tar -zxvf xlwt-0.7.5.tar.gz
cd xlwt-0.7.5
python setup.py install
python
import xlwt
```

### 3、安装 `pyquery、lxml`模块

```bash
install lxml 
这个可以用pip 和easy_install
easy_install lxml 
出现这个错误就说easy_install 这个安装工具需要升级或者从新安装。

yum install libxslt-devel libxml2-devel -y
easy_install lxml 
然后安装 yum install MySQL-python  -y
先安装下这个 因为提示没有这个包 找不到
这里我直接用ln -s做个软链接
ln -s /usr/local/bin/easy_install-2.7 /usr/bin/easy_install


install pyquery 
这个可以用pip 和easy_install
easy_install  pyquery  
这里提示easy_install  如果有问题，就说明版本不对。
因为我之前是用python2.6.6版本 所有现在升级python2.7版本，之前版本在
先查看下版本 python -V
python-2.7.7

如果是其他版本就需要做个软链接到/usr/bin/python
ln -s /usr/local/bin/python-2.7.7 /usr/bin/python  
提示如果存在，先rm -rf python 然后在ln -s
在看看easy_install 版本，同样升级到最高版本。就可以了。
```

### 4、安装爬虫环境

```bash
系统环境: centos 6.7_64位 关闭selinux

一、升级系统组件
#yum remove audit
#yum -y install gcc gcc-c++ autoconf libjpeg libjpeg-devel libpng libpng-devel freetype freetype-devel libxml2 libxml2-devel zlib zlib-devel glibc glibc-devel glib2 glib2-devel bzip2 bzip2-devel ncurses ncurses-devel curl curl-devel e2fsprogs e2fsprogs-devel krb5 krb5-devel libidn libidn-devel openssl openssl-devel openldap openldap-devel nss_ldap openldap-clients openldap-servers make libffi-devel libffi libxslt-devel libxml2-devel sqlite-devel  

二、升级python
#wget http://python.org/ftp/python/2.7.3/Python-2.7.3.tar.bz2
#tar -jxvf Python-2.7.3.tar.bz2  
#cd Python-2.7.3
#./configure
#make all           
#make install
#make clean
#make distclean
#mv /usr/bin/python /usr/bin/python2.6.6
#ln -s /usr/local/bin/python2.7 /usr/bin/python 

修改yum，避免系统不正常运行
#vi /usr/bin/yum
将文件头部的
#!/usr/bin/python

改成
#!/usr/bin/python2.6.6

三、安装scrapy
1、安装pip
下载pip安装程序，链接如下
http://pan.baidu.com/s/1jHiitZw

安装
#python get-pip.py

2、安装scrapy

#pip install scrapy

#pip install scrapyd
#pip install Beautifulsoup4 
# pip install --allow-external mysql-connector-python   mysql-connector-python
#pip install scrapy_jsonrpc
```
### 5、安装爬虫`scrapy`包

```bash
easy-install scrapy  用这个方法是不能解决一次性依赖
pip install scrapy 这个可以解决一次性的依赖问题

安装问题：
easy-install scrapy 提示这个错误  这里我没有按照Twisted 包 
这里手动下载Twisted包安装上，就好了。官网链接：https://twistedmatrix.com/trac/

这里提示python 2.6 版本 这里如果不想从新下载安装就直接做个软链接 因为一般都是不自动读取到2.7的
这里我重新编译安装过了。上一步：
先查了很多资料 都说scrapy版本过于太低。这里我升级下版本。pip install —upgrade scrapy 
提示报错。

这里用pip install setuptools 安装成功了。

可是执行脚本还是有出错后来看到下面有提示
少 service_identity ，_sqlite3这个包 后提示路径https://pypi.python.org/pypi/service_identity

这里下载下来我安装上了identity包，最后面一条提示没有安装sqlite3
参考连接：http://stackoverflow.com/questions/33734651/importerror-error-loading-object-scrapy-contrib-memusage-memoryusage-no-modu

可是运行还是有报错。
我百度查看了很多资料，参考链接。
https://github.com/lra/mackup/issues/220

查看安装：find / -name _sqlite3.so
/usr/lib64/python2.6/lib-dynload/_sqlite3.so
这里只有python2.6版本
所以找不到这个 只能重新做个软链接:
ln -s /usr/lib64/python2.6/lib-dynload/_sqlite3.so /usr/local/python27/lib/python2.7/lib-dynload/_sqlite3.so

我自己安装python 2.7 的目录是/usr/local/python27/lib/python2.7

然后在执行就不会报错了。
到这里爬虫工具已经全部安装上了。
```

### 6、使用`easy_install,ipython`报错

```bash
[root@localhost setuptools-3.3]# easy_install pip
Traceback (most recent call last):
File "/usr/bin/easy_install", line 5, in <module>
from pkg_resources import load_entry_point
File "build/bdist.linux-i686/egg/pkg_resources.py", line 2749, in <module>

File "build/bdist.linux-i686/egg/pkg_resources.py", line 446, in _build_master

File "build/bdist.linux-i686/egg/pkg_resources.py", line 459, in _build_from_requirements
is returned.
File "build/bdist.linux-i686/egg/pkg_resources.py", line 628, in resolve
error that occurred. Usually this will be a ``DistributionNotFound`` or
pkg_resources.DistributionNotFound: setuptools==0.9.6

因为之前的python版本为2.4的后来升级为2.7的，但是easy_install还是读取2.4的配置

所以要重新做个软连接

[root@localhost bin]# ln -s /usr/local/python2.7/bin/easy_install /usr/bin/easy_install
ln: 正在创建指向“/usr/local/python2.7/bin/easy_install”的符号链接“/usr/bin/easy_install”: 文件已存在
[root@localhost bin]# rm -rf /usr/bin/easy_install
[root@localhost bin]# ln -s /usr/local/python2.7/bin/easy_install /usr/bin/easy_install

ipython同样的原理，安装完ipython后无法使用，同样创个软连接


[root@localhost ipython-1.2.1]# ln -s /usr/local/python2.7/bin/ipython /usr/bin/ipython
[root@localhost ipython-1.2.1]# ipython
Python 2.7.6 (default, Feb 14 2014, 06:05:34)
Type "copyright", "credits" or "license" for more information.
IPython 1.2.1 -- An enhanced Interactive Python.
? -> Introduction and overview of IPython's features.
%quickref -> Quick reference.
help -> Python's own help system.
object? -> Details about 'object', use 'object??' for extra details.
In [1]:
```

### 7、pip安装提示：`ImportError: cannot import name HTTPSHandler with pip`


```bash
运行pip install numpy scipy


Traceback (most recent call last):
  File "/Users/aaronmeurer/anaconda/bin/pip", line 4, in <module>
    from pip import main
  File "/Users/aaronmeurer/anaconda/lib/python3.3/site-packages/pip/__init__.py", line 10, in <module>
    from pip.util import get_installed_distributions, get_prog
  File "/Users/aaronmeurer/anaconda/lib/python3.3/site-packages/pip/util.py", line 17, in <module>
    from pip._vendor.distlib import version
  File "/Users/aaronmeurer/anaconda/lib/python3.3/site-packages/pip/_vendor/distlib/version.py", line 14, in <module>
    from .compat import string_types
  File "/Users/aaronmeurer/anaconda/lib/python3.3/site-packages/pip/_vendor/distlib/compat.py", line 66, in <module>
    from urllib.request import (urlopen, urlretrieve, Request, url2pathname,
ImportError: cannot import name HTTPSHandler
```

问题：`这个是因为不能访问外网，ping.www.baidu.com，所以需要添加DNS`



### 8、安装`pexpect-2.3`方法

```bash
wget http://pexpect.sourceforge.net/pexpect-2.3.tar.gz
tar xzf pexpect-2.3.tar.gz
cd pexpect-2.3
python ./setup.py install

sendEmail的下载: http://caspian.dotconf.net/menu/Software/SendEmail/  

tar -zxvf sendEmail-v1.56.tar.gz
cp -a sendEmail-v1.56/sendEmail /usr/local/bin  
chmod +x /usr/local/bin/sendEmail 
/usr/local/bin/sendEmail  
```

### 9、搭建`pip`本地源


```bash
参考地址：搭建自己的 pip 源:http://liuliqiang.info/post/build-your-own-pip-source/

```

### 10、Python包管理器安装pip+setuptools


pip类似RedHat里面的yum,安装Python包非常方便装

 一、pip的安装（方法一）

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

二、pip安装（方法二）

```bash
cd /usr/local/src
wget https://bootstrap.pypa.io/get-pip.py --no-check-certificate -O ./get-pip.py
python get-pip.py
```

 三、pip更换国内源地址


```bash
cd 
mkdir .pip
vim .pip/pip.conf

[global]
index-url = http://pypi.douban.com/simple
[install]
trusted-host = pypi.douban.com
```


 pip使用方法：


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



### 11、Centos 快速安装升级Python,setuptools+pip 

CENTOS 6.X 系列默认安装的 Python 2.6 ，目前开发中主要是使用 Python 2.7 ，这两个版本之间还是有不少差异的，程序在 Python 2.6 下经常会出问题。
比如： re.sub 函数 ，2.7 支持 flags 参数，而 2.6 却不支持。
所以，打算安装 Python 2.7 来运行 Flask 应用程序，但 2.6 不能删除，因为系统对它有依赖。

1、安装 sqlite-devel
因为 Flask 应用程序可能使用能 Sqlite 数据库，所以这个得装上（之前因为没装这个，导致 Python 无法导入 sqlite3 库。

当然，也可以从源码编译安装。

```bash
yum install sqlite-devel -y
```

 2、安装 Python 2.7

```bash
yum install -y zlib-devel  gcc make
wget https://www.python.org/ftp/python/2.7.8/Python-2.7.8.tgz
tar xf Python-2.7.8.tgz
cd Python-2.7.8
./configure --prefix=/usr/local
make && make install
mv /usr/bin/python /usr/bin/python2.6.6 
ln -s /usr/local/bin/python2.7 /usr/bin/python.  #做个软连接到当前用户的bin目录 
sed -i 's|#!/usr/bin/python|#!/usr/bin/python2.6.6|g' /usr/bin/yum  #升级安装好新版本python以后，默认依然是python2.6  vim /usr/bin/yum  

查看安装的新版本信息 
python -V
python2.9 
```
安装成功之后，你可以在 /usr/local/bin/python2.7 找到 Python 2.7。

3、安装 setuptools + pip

这里需要注意，一定要使用 python2.7 来执行相关命令。

```bash
# First get the setup script for Setuptools:
wget https://bitbucket.org/pypa/setuptools/raw/bootstrap/ez_setup.py

# Then install it for Python 2.7 :
python2.7 ez_setup.py

# Now install pip using the newly installed setuptools:
easy_install-2.7 pip

# With pip installed you can now do things like this:
pip2.7 install [packagename]
pip2.7 install --upgrade [packagename]
pip2.7 uninstall [packagename]
```


4、使用 virtualenv

```bash
# Install virtualenv for Python 2.7 and create a sandbox called my27project:
pip2.7 install virtualenv
virtualenv-2.7 my27project

# Check the system Python interpreter version:
python --version
# This will show Python 2.6.6

# Activate the my27project sandbox and check the version of the default Python interpreter in it:
source my27project/bin/activate
python --version
# This will show Python 2.7.X
deactivate
基本就是这些了，网上很多教程都说要做软链接，但我感觉那样做或多或少会对系统有一些未知的影响。这个方法能尽量保持系统的完整性，很多自带 Python 程序其实在头部都指定了 #!/usr/bin/python ，所以它们用的其实是 Python 2.6 ，而不是新安装的 Python 2.7 。
```
原文：http://digwtx.duapp.com/54.html

参考： http://toomuchdata.com/2014/02/16/how-to-install-python-on-centos/



### 感兴趣欢迎加入技术讨论群

🐧 🐧 Linux shell_高级运维派: `459096184` 圈子 (系统运维-应用运维-自动化运维-虚拟化技术研究欢迎加入)
🐧 🐧 BigData-Exchange School :`521621407` 圈子（大数据运维)（Hadoop开发人员)（大数据研究爱好者) 欢迎加入

