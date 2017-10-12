# Python 
* 可参考教程：http://www.liaoxuefeng.com/wiki/001374738125095c955c1e6d8bb493182103fac9270762a000

Python 是一门简单易学且功能强大的编程语言。它拥有高效的高级数据结构，并且能够用简单而又高效的方式进行面向对象编程。Python 优雅的语法和动态类型，再结合它的解释性，使其在大多数平台的许多领域成为编写脚本或开发应用程序的理想语言。

你可以自由地从 Python 官方点: http://www.python.org，以源代码或二进制形式获取 Python 解释器及其标准扩展库，并可以自由的分发。此站点同时也提供了大量的第三方 Python 模块、程序和工具，及其附加文档。

你可以很容易的使用 C 或 C++（其他可以通过 C 调用的语言）为 Python 解释器扩展新函数和数据类型。Python 还可以被用作定制应用程序的一门扩展语言。

本手册非正式的向读者介绍了 Python 语言及其体系相关的基本知识与概念。在学习实践中结合使用 Python 解释器是很有帮助的，不过所有的例子都是完整的，所以本手册亦可离线阅读。

如果需要了解相关标准库或对象的详细介绍，请查阅 Python 参考文档 。Python 参考手册 提供了更多语言相关的正式说明。如果想要使用 C 或 C++ 编写扩展，请查阅 Python 解释器扩展和集成章节 和 C API 参考手册 。当然也可阅读一些深入介绍 Python 知识的图书。

本手册不会尝试涵盖 Python 的全部知识和每个特性，甚至不会涵盖所有常用的特性。相反地，它介绍了 Python 中许多最引人瞩目的特性，并且会给你一个关于语言特色和风格的认识。读完之后，你将能够阅读和编写 Python 模块或程序，并为以后使用 Python 参考手册 继续学习诸多 Python 模块库做好准备。


词汇表 也值得浏览一下。

1. 开胃菜
2. 使用 Python 解释器
2.1. 调用 Python 解释器
2.1.1. 参数传递
2.1.2. 交互模式
2.2. 解释器及其环境
2.2.1. 源程序编码
3. Python 简介
3.1. 将 Python 当做计算器
3.1.1. 数字
3.1.2. 字符串
3.1.3. 列表
3.2. 编程的第一步
4. 深入 Python 流程控制
4.1. if 语句
4.2. for 语句
4.3. range() 函数
4.4. break 和 continue 语句, 以及循环中的 else 子句
4.5. pass 语句
4.6. 定义函数
4.7. 深入 Python 函数定义
4.7.1. 默认参数值
4.7.2. 关键字参数
4.7.3. 可变参数列表
4.7.4. 参数列表的分拆
4.7.5. Lambda 形式
4.7.6. 文档字符串
4.7.7. 函数注解
4.8. 插曲：编码风格
5. 数据结构
5.1. 关于列表更多的内容
5.1.1. 把链表当作堆栈使用
5.1.2. 把链表当作队列使用
5.1.3. 列表推导式
5.1.4. 嵌套的列表推导式
5.2. del 语句
5.3. 元组和序列
5.4. 集合
5.5. 字典
5.6. 循环技巧
5.7. 深入条件控制
5.8. 比较序列和其它类型
6. 模块
6.1. 深入模块
6.1.1. 作为脚本来执行模块
6.1.2. 模块的搜索路径
6.1.3. “编译的” Python 文件
6.2. 标准模块
6.3. dir() 函数
6.4. 包
6.4.1. 从 * 导入包
6.4.2. 包内引用
6.4.3. 多重目录中的包
7. 输入和输出
7.1. 格式化输出
7.1.1. 旧式的字符串格式化
7.2. 文件读写
7.2.1. 文件对象方法
7.2.2. 使用 json 存储结构化数据
8. 错误和异常
8.1. 语法错误
8.2. 异常
8.3. 异常处理
8.4. 抛出异常
8.5. 用户自定义异常
8.6. 定义清理行为
8.7. 预定义清理行为
9. 类
9.1. 术语相关
9.2. Python 作用域和命名空间
9.2.1. 作用域和命名空间示例
9.3. 初识类
9.3.1. 类定义语法
9.3.2. 类对象
9.3.3. 实例对象
9.3.4. 方法对象
9.3.5. 类和实例变量
9.4. 一些说明
9.5. 继承
9.5.1. 多继承
9.6. 私有变量
9.7. 补充
9.8. 异常也是类
9.9. 迭代器
9.10. 生成器
9.11. 生成器表达式
10. Python 标准库概览
10.1. 操作系统接口
10.2. 文件通配符
10.3. 命令行参数
10.4. 错误输出重定向和程序终止
10.5. 字符串正则匹配
10.6. 数学
10.7. 互联网访问
10.8. 日期和时间
10.9. 数据压缩
10.10. 性能度量
10.11. 质量控制
10.12. “瑞士军刀”
11. 标准库浏览 – Part II
11.1. 输出格式
11.2. 模板
11.3. 使用二进制数据记录布局
11.4. 多线程
11.5. 日志
11.6. 弱引用
11.7. 列表工具
11.8. 十进制浮点数算法
12. 虚拟环境和包
12.1. 简介
12.2. 创建虚拟环境
12.3. 使用 pip 管理包
13. 接下来？
14. 交互式输入行编辑历史回溯
14.1. Tab 补全和历史记录
14.2. 其它交互式解释器
15. 浮点数算法：争议和限制
15.1. 表达错误
16. 附录
16.1. 交互模式
16.1.1. 错误处理
16.1.2. 可执行 Python 脚本
16.1.3. 交互式启动文件
16.1.4. 定制模块
Next 


### 使用easy_install,ipython报错

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
