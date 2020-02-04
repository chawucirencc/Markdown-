### Web框架 ###

web应用程序框架，表示一个库和模块的集合，使Web应用程序开发人员能够编写应用程序，而不用担心协议，线程管理等细节。

---

### Django

Django 是一个开放源代码的 web 应用框架，由 Python 写成。Django采用了 MVC 的软件设计模式，即模型 M，视图 V 和控制器 C 。

Django 在Windows 上的安装，先需要有 Python 的环境，具体不在赘述。安装好 Python之后在 ```cmd``` 窗口使用 ```pip3 install django``` 即可。检查是否安装成功：

1.  可以打开 Python 的环境 ```import django``` ，使用 ```print(django.get_version())``` 函数查看版本。
2.  可以在编辑器里使用同样的方法查看版本。

这里有个问题，就是虚拟环境的问题，因为项目对应的 Django 版本可能不一样，如果再同一个环境中，安装另外版本的 Django 版本会覆盖之前安装的，所以对于需要安装不同版本的 Django 项目通常使用虚拟环境来处理。

---

### Flask ###

##### 基础 #####

Flask是用Python编写的一个轻量级的web应用框架，Flask基于Werkzeug WSGI工具包和Jinja2模板引擎。两者都是Pocco项目。Flask仅仅保留了程序的核心模块，而对于其他的功能都是通过添加扩展来实现的。

WSGI：Web Server Gateway Interface（Web服务器网关接口，WSGI）已被用作Python Web应用程序开发的标准。 WSGI是Web服务器和Web应用程序之间通用接口的规范。

Werkzeug:它是一个WSGI工具包，它实现了请求，响应对象和实用函数。 这使得能够在其上构建web框架。 Flask框架使用Werkzeug作为其基础之一。

jinja2:jinja2是Python的一个流行的模板引擎。Web模板系统将模板与特定数据源组合以呈现动态网页。

创建第一个应用

```python
from flask import Flask
app=Flask(__name__)


@app.route('/')
def hello_world():
    return 'hello world'


if __name__=='__main__':
    app.run()
```

运行之后会出现提示，出现网址和端口显示`hello world`。

Flask中的**route()**装饰器用于将URL绑定到函数，在第一个应用中就是绑定了hello_world()函数。

##### 变量规则 #####

变量规则可以在在函数中传入参数，在装饰器函数`route`中添加参数，单纯的`/`表示监听的端口和地址属于默认，不发生改变。

```python
@app.route('/hello/<name>')
def hello_name(name):
    return 'Hello %s' %name

@app.route('/show/<float:num>')
def show_num(num):
    return 'Number is %f' %num
```

这样监听的网址就发生了变化，`http://127.0.0.1:5000/hello/ces`，其中`hello`为绑定的函数名称（也是监听的URL网址的后缀），`ces`为函数中需要传入的参数。第二和绑定函数的网址（URL）就变成了`http://127.0.0.1:5000/show/12.00`同理，12.00就是传入函数的参数，最终是以浮点数显示出来的。如果URL地址输入错误会显示出404的页面。

##### Flask URL的构建 #####

`redirect`和`url_for`组合使用，`url_for()`函数接受一个函数名为第一个参数，以及一个或者多个关键字参数。示例代码：

```python
from flask import Flask, redirect, url_for
app = Flask(__name__)
@app.route('/admin')
def hello_admin():
   return 'Hello Admin'

@app.route('/guest/')
def hello_guest(guest):
   return 'Hello %s as Guest' % guest

@app.route('/user/')
def hello_user(name):
   if name =='admin':
      return redirect(url_for('hello_admin'))
   else:
      return redirect(url_for('hello_guest',guest = name))

if name == 'main':
   app.run(debug = True)
```

通过一个判断来选择函数，在上面的代码中存在一些问题，开启服务之后，在URL中添加变量部分，可能会显示404，可能的原因是`'/user/'`部分缺少一个参数，如果添加了参数之后判断的第二部分就不会执行，只会执行判断的前半部分。

##### HTTP方法 #####





