### Web框架 ###

web应用程序框架，表示一个库和模块的集合，使Web应用程序开发人员能够编写应用程序，而不用担心协议，线程管理等细节。

---

### 1、Tornado ###

一个由FriendFeed开发的Python Web框架和异步网络库，采用非阻塞网络I/O模型，可以处理数以千计的网络连接。对于long polling、WebSockets和其他需要长时间实时连接的Apps，Tornado是一个理想的Web框架，它介于Django和Flask之间，能很好地处理C10K问题。



### 2、Socket ###

一个套接字通讯底层库，用于在服务器和客户端间建立TCP或UDP连接，通过连接发送请求与响应。

### 3、Django

Django 是一个开放源代码的 web 应用框架，由 Python 写成。Django采用了 MVC 的软件设计模式，即模型 M，视图 V 和控制器 C 。

Django 在Windows 上的安装，先需要有 Python 的环境，具体不在赘述。安装好 Python之后在 ```cmd``` 窗口使用 ```pip3 install django``` 即可。检查是否安装成功：

1.  可以打开 Python 的环境 ```import django``` ，使用 ```print(django.get_version())``` 函数查看版本。
2.  可以在编辑器里使用同样的方法查看版本。

这里有个问题，就是虚拟环境的问题，因为项目对应的 Django 版本可能不一样，如果再同一个环境中，安装另外版本的 Django 版本会覆盖之前安装的，所以对于需要安装不同版本的 Django 项目通常使用虚拟环境来处理。

---

### 4、Flask ###

在VScode中开启debug模式之后服务不会启动！暂时未解决。

在Pycharm中开启debug模式需要在设置中勾选FLASK_DEBUG。

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

`redirect`和`url_for`组合使用，`url_for()`函数接受一个函数名为第一个参数，以及一个或者多个关键字参数。跳转到某个函数。示例代码：

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

`http`协议是网络通信中数据通信的基础，默认的情况下，Flask路由响应的是GET请求。可以通过`route()`装饰器提供的方法参数来改变这个选项。如下：

```python
@app.route('/login/', methods=["POST", "GET"])
def login():
    if request.method == 'POST': # 第一次编写的时候此处有问题。
        user = request.form['nm'] # 第一次编写的时候此处有问题。
        return redirect(url_for('success', name=user))
    else:
        user = request.args.get('nm')
        return redirect(url_for('success', name=user))
```

在第一行的时候，使用方法参数改变默认的请求方法。需要另外一个`html`表单文件来将输入的文本传输到URL中。

```html
<html>
   <body>
      <form action = "http://localhost:5000/login" method = "post">
         <p>Enter Name:</p>
         <p><input type = "text" name = "nm" /></p>
         <p><input type = "submit" value = "submit" /></p>
      </form>
   </body>
</html>
```

先开启路由服务，然后在浏览器中打开`html`脚本文件，输入文本点击提交，会跳转到服务中的URL显示函数中的内容。

##### 模板 #####

使用Python代码来生成HTML文件很麻烦，尤其是需要放置数据变量和Python的语言元素的时候，这时候需要从HTML中转义。可以利用Flask中的jinja2末班引擎。通过使用`render_template()`函数呈现HTML文件。在这里遇到了一个问题，在URL地址的地方少写了一个参数，导致网页一直显示的是404，需要在URL地址中多添加一个参数。如下：

```python
@app.route('/hello/<user>')
def index(user):
    # user = 'www.baidu.com'
    return render_template('index.html', name = user)
    # return 'hello'
-----------------------------------------------------------------
# 以下为HTML的测试代码。
<!doctype html>

  <h1>Hello {{ name }}!</h1>
-----------------------------------------------------------------
{{ }}用于表达式可以打印到输出模板。
{%...%}用于语句，比如if...else
{#...#} 用于在模板中的注释。
#...### 用于行语句。
```

在添加参数的时候，如果是`int`则仅仅只是42即可，如果是`float`则需要输入42.0才能识别出来。

##### 静态文件 #####

在Flask项目中static文件夹中存放的就是静态文件，通常包括JavaScript文件和一些支持网页显示样式的CSS文件。这些静态文件都是从static文件夹中加载出来的。可以在HTML脚本中加载一个简单的js文件。如下：

```html
# hello.html
<html>
   <head>
      <script type = "text/javascript" 
         src = "{{ url_for('static', filename = 'hello.js') }}" ></script>
   </head>
   <body>
      <input type = "button" onclick = "sayHello()" value = "Say Hello" />
   </body>
</html>
```

```javascript
# htllo.js
function sayHello() {
   alert("Hello World")
}
```

此时还需要开启一个服务，同之前一样。

##### Request对象 #####

来自客户端网页的数据作为全局对象被发送到服务器，为了处理请求数据，需要导入Request模块。Request对象的重要属性如下：

-   **Form** - 它是一个字典对象，包含表单参数及其值的键和值对。
-   **args** - 解析查询字符串的内容，它是问号（？）之后的URL的一部分。
-   **Cookies** - 保存Cookie名称和值的字典对象。
-   **files** - 与上传文件有关的数据。
-   **method** - 当前请求方法。

##### 将表单数据发送到模板 #####

表单：在HTML中，表单用于搜集不同类型的用户输入。而表单元素指不同类型的input元素，复选框，单选按钮和提交按钮等。使用表单的提交按钮之后会将数据放在URL中返回给服务器（form中action参数的服务器），然后由服务器判断之后再返回一个HTML页面，返回最终的结果。代码如下：

```python
@app.route('/')
def student():
    return render_template('students.html')


@app.route('/result', methods=['GET', 'POST'])
def res():
    # result={'Name':'Job', 'Physics':99, 'chemistry':99, 'Mathematics':90}
    # result=[1, 2, 0, 3, 4]
    if request.method == 'POST':
        result=request.form
        return render_template('result.html', result=result)
    # return render_template('result.html', result=result)
    # 注释的代码为测试用、
```

```html
# result.html
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Result</title>
</head>
<body>
    {% for key, value in result.items() %}
        {{ key }}<br>
        {{ value }}<br>
    {% endfor %}
</body>
</html>
----------------------------------------------------------------------------
# students.html
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>
<body>
    <form action="http://127.0.0.1:5000/result", method="POST">
        <p>Name <input type = "text" name = "Name" /></p>
        <p>Physics <input type = "text" name = "Physics" /></p>
        <p>Chemistry <input type = "text" name = "chemistry" /></p>
        <p>Maths <input type ="text" name = "Mathematics" /></p>
        <p><input type = "submit" value = "submit" /></p>
    </form>
</body>
</html>
# form作为表单部分收集用户输入的数据。
```

在获取表单的数据和请求方式的时候需要使用`request`模块，可以直接获取到请求方式和数据。使用flash模块将返回的消息放在网页上面，首先需要在HTML写出一个for循环来接收后端传来的消息，使用`get_flashed_messages()`来接收消息。如下：

```html
<!doctype html>
<html>
  <form method="POST">
    <p>用户名：<input type="text" name="name"></p>
    <p>密码：<input type="password" name="password"></p>
    <p>确认密码：<input type="password" name="password2"></p>
    <p><input type="submit" name="提交"></p>
    {% for message in get_flashed_messages() %}
        {{ message }}
    {% endfor %}
  </form>
</hr>
</html>
```

语句部分就是用来显示消息的。很重要的一点就是需要在开头的时候写一个`app.secret_key='secret_key'`这个语句来进行加密，否则会报错！另外就是flash显示的编码问题，在py3中编码问题得到了很大的解决，如果是py2的环境，flash需要这样写`flash(u'****')`来解决编码问题。

##### Flask WTF（WTForms） #####

需要先安装`flask-WTF`模块，`pip3 install flask-WTF`。需要载入基类`FlaskForm`，还有表单模块`wtforms`，还需要使用`secret_key`（必不可少）。需要在HTML网页。代码如下：

```html
# index.html
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <title>index</title>
</head>
<body>
<form method="POST">
    {{ form.username.label }}{{ form.username }}
    {{ form.password.label }}{{ form.password }}
    {{ form.password2.label }}{{ form.password2 }}
    {{ form.submit }}
</form>
</body>
</html>
```

```python
# app.py
from flask import Flask, render_template
from flask_wtf import FlaskForm
from wtforms import StringField, PasswordField, SubmitField

app = Flask(__name__)
app.secret_key = 'secret_key'

class LoginForm(FlaskForm):
    username = StringField('用户名：')
    password = PasswordField('密码：')
    password2 = PasswordField('确认密码：')
    submit = SubmitField('提交')


@app.route('/', methods=['GET', 'POST'])
def hello_world():
    login = LoginForm()
    return render_template('index.html', form=login)


if __name__ == '__main__':
    app.run()
```

简单地使用WTF来实现一个用户名密码的界面。在使用WTF框架创建输入表单的时候，还会自动创建CSRF令牌的隐藏字段，这是为了防止跨站请求伪造攻击。这里还没有使用验证函数。使用验证函数需要先导入模块:

```python
from wtforms.validators import DataRequired, EqualTo

class LoginForm(FlaskForm):
    username = StringField('用户名：', validators=[DataRequired()])
    password = PasswordField('密码：', validators=[DataRequired()])
    password2 = PasswordField('确认密码：', validators=[DataRequired(), EqualTo('password')])
    submit = SubmitField('提交')
```

对上面的类做了相应的优化。添加了一些验证函数。注：在Pycharm中Flask项目如果需要开启debug模式需要在设置中勾选到FLASK_DEBUG。

##### Flask使用数据库 #####

首先需要安装`flask_sqlalchemy`模块。`pip3 insatll flask_sqlalchemy`安装扩展，这个扩展是针对关系型数据库来使用的，然后用下面的两段代码来配置和连接数据库。参考：https://www.cnblogs.com/Sunzz/p/10979970.html，这个扩展是使用ORM对象映射来操作数据库，可以不用写一般的SQL语句。但是在性能上会造成一些损失。

```python
pip3 insatll flask_sqlalchemy # 安装扩展
app.config['SQLALCHEMY_DATABASE_URI'] = 'mysql://root:password@localhost:3306/database_name' # 配置MySQL数据库
app.config['SQLALCHEMY_TRACK_MODIFICATIONS'] = False
```

在上面的配置代码中，数据库类型://管理员用户名//密码@端口地址:端口号/数据库名。

关于数据的增删改查，如果是新的数据库，那还需要在MySQL中新建一个数据库才能使用，如果是已经存在的数据库，而且数据库中也已经存在表了。那么就不用新建了，只需要在代码中创建一个实例，然后字段需要和已经存在的表中的字段相同，然后再在路由中执行查询，如下代码：

```python
# 创建表（已存在的表）
class Test(db.Model):
    __tablename__ = 'courses'
    id = db.Column(db.Integer, primary_key=True)
    student = db.Column()
    cl = db.Column()
    score = db.Column(db.Integer, unique=True)

    def __repr__(self):
        return 'OK!'
    
@app.route('/sql', methods=['GET', 'POST'])
def flask_sql():
    data = Test.query.all()
    print(data)
    return 'success'
```

创建新表和上面的代码类似。

关于数据库中的关系引用：写在一的一方，在另外一个模型（表）中使用反向引用，`backref`。

待续....