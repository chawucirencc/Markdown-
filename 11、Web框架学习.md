### Django

Django 是一个开放源代码的 web 应用框架，由 Python 写成。Django采用了 MVC 的软件设计模式，即模型 M，视图 V 和控制器 C 。

Django 在Windows 上的安装，先需要有 Python 的环境，具体不在赘述。安装好 Python之后在 ```cmd``` 窗口使用 ```pip3 install django``` 即可。检查是否安装成功：

1.  可以打开 Python 的环境 ```import django``` ，使用 ```print(django.get_version())``` 函数查看版本。
2.  可以在编辑器里使用同样的方法查看版本。

这里有个问题，就是虚拟环境的问题，因为项目对应的 Django 版本可能不一样，如果再同一个环境中，安装另外版本的 Django 版本会覆盖之前安装的，所以对于需要安装不同版本的 Django 项目通常使用虚拟环境来处理。

