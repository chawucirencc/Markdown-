## 一、语言特性
#### **1、Python语言和其他语言的区别** ： ####

Python是解释性语言，与编译型语言不同，相对来讲解释型语言的运行速度没有编译型语言快。另一方面Python的语法简单明了，
不需要声明变量的数据类型，而且Python的跨平台性很好、可以运行在Windows、Mac、Linux上面。

#### **2、简述解释型语言和编译型语言：** ####

编译型语言：在程序运行之前有一个专门的编译过程，把程序变异成机器语言的文件，再次运行时不需要重新翻译，直接使用翻译结果，效率高，依赖编译器。
解释型语言：不用预先进行编译，以文本的方式存储代码，在运行的时候需要先进行解释才能能运行。意思就是，每次重新运行的话就要重新解释，运行的效率较低。
动态语言：在代码运行的时候可以根据某些条件来改变自身的结构。可以引入其他的对象，代码，函数等。
静态语言：运行时代码结构不能被改变。
强类型语言：一个变量如果被指定某个数据类型，若不经过强制转换，那就永远是这个类型。
弱类型语言：数据类型可以被忽略。根据赋值的不同改变不同的数据类型。
动态类型语言（指数据结构）和动态语言（指代码结构）是不一样的。

***<u>在关于使用 `print()` 语句的时候，输出会造成大量的资源浪费，并且会拖慢程序的运行速度，所以，尽量不要频繁的使用 `print()` 可以通过一个小程序测试一下两者的用时的区别，大约相差了1000倍左右的时间。</u>***

**3、Python 的解释器种类以及相关特点？** 
解释器版本：
```Cpython``` 、```Ipython``` 、```PyPy```、```Jython```、```IronPython```。
```Ipython``` 基于```Cpython``` ，只是在交互方式上面做了优化，其他的功能和 ```Cpython``` 是一样的。
```Jython```是运行在```Java```平台上的解释器。``` IronPython``` 和 ```Jython``` 类似，只不过```IronPython```是运行在微软```.Net```平台上的```Python```解释器，可以直接把```Python代```码编译成```.Net```的字节码。

#### **4、说说你知道的Python3 和 Python2 之间的区别？** ####

* 在Python2中默认使用```asscii```编码，Python3默认使用UTF-8编码。
* 对于```print```，不再是语句，而是一个函数，可以接收多个参数。
* 字符串和编码问题，在py2中字符串和字节序列区分不明显（```str```代表字节序列，```unicode```代表文本字符串），而在py3中，对两者进行了严格的区分，```str```代表字符串，```byte```代表字节序列。
* 在py2中```True```和```False```是两个全局变量，分别为1和0.而在py3中，变成了两个关键字，不允许被重新赋值。
* py3中用 ```!=``` 替换了 ```<>``` 

#### **5、Python3 和 Python2 中 ```int```  和 ```long```  区别？** ####

在py3中不存在```long```类型，py2中的长整型被替换为普通的十进制整数。

#### **6、```xrange```  和 ```range``` 的区别？** ####

```xrange``` 的结果是一个生成器。```range```为一个普通对象，但是在py3中，两者进行了合并。

## 二、编码规范
#### **7、什么是 PEP8?** ####

可参考：https://zh-google-styleguide.readthedocs.io/en/latest/google-python-styleguide/python_language_rules/#lint
相当于```Python```增强规范，是一种编码规范，更容易被阅读。

#### **8、了解 Python 之禅么？** ####

在```Python``` 终端输入```import this```就可以看见。

####  **9、了解 docstring么？**  ####

```docstring``` 称为文档字符串，作为模块，函数，类或方法定义中的第一个语句出现。这样的docstring成为该对象的```__doc__```特殊属性。
为了保持一致性，务必要在```docstrings```周围使用三重引号。且分为单行和多行。

```Python
def name():
    """
    This is docstring！
    """
    return 0
```

#### **10、了解类型注解么？**  ####

因为在设置变量是不需要对变量声明类型，所以书写的时候会比较方便，但是在阅读的时候会造成一些问题，在众多的变量中有时候回不明白函数中参数的变量类型是什么，这时候使用类型注释会增强代码的可读性。

```Python
def name(x:int, y:int)->int:
    return x+y
```

#### **11、例举你知道 Python 对象的命名规范，例如方法或者类等。**  ####

```
module_name, package_name, ClassName, method_name, ExceptionName, function_name,
GLOBAL_VAR_NAME, instance_var_name, function_parameter_name, local_var_name.
```
如上所示。各个不同的类、方法、对象、以及包都按照相应的命名方法。

#### **12、Python 中的注释有几种？**  ####

单行注释方法：```# 这是单行注释``` 
多行注释：

```Python
"""
这是多行注释。
"""
```
多行注释用三个引号把要注释的内容括起来。

#### **13、如何优雅的给一个函数加注释？**  ####

个人觉得注释不要过多，不要讲每一行代码都干了什么，在关键的地方加上注释即可。比如比较复杂难懂的地方。如果要声明一个类或者一个函数的作用和功能，最好使用```docstring```注释。

#### **14、如何给变量加注释？**  ####

使用#即可，但是要保证全局的风格都是一致的。 

#### **15、Python 代码缩进中是否支持 Tab 键和空格混用？**  ####

不可以混用，在不同的```IDE```中对```Tab```键的定义是不一样的，有可能是4个字符的长度，也有可能是8个字符的长度。 

#### **16、是否可以在一句 import 中导入多个库?**  ####

可以，但是不推荐，而且尽量不使用```from * import modelname```，假如某个模块经常被使用，可以这样导入，推荐每行导入一个模块。 

#### **17、在给  ```Py```  文件命名的时候需要注意什么?** ####

命名的时候不要和模块的名字相同，否则在调用包的时候会出现错误。 

#### **18、例举几个规范 Python 代码风格的工具。**  ####

* ```Pylint``` -自动检测工具，```pip3 install pylint```可以安装。
* ```Black``` -自动优化工具， 
* PEP8


## 三、数据类型
#### **19、列举 Python 中的基本数据类型？** ####

* ```Number(数字)``` 
* ```String(字符串)``` 
* ```List(列表)``` 
* ```Tuple(元组)``` 
* ```Dictionary(字典)``` 

不可变数据： ```Number(数字)``` 、 ```String(字符串) ``` 、``` Tuple(元组) ``` 
可变数据：```List(列表)```、```Dictionary(字典)```、```Set(集合)```  

#### **20、如何区别可变数据类型和不可变数据类型？** ####

不可变数据类型不管有多少引用，其在内存中只占一块地方。然而可变数据类型，相同的数据在内存中的位置是不一样的。
变量都是内存中值的引用，区别在于引用的是同一块内存的值还是在一块新的内存中创建新的值。 

#### **21、将"hello world"转换为首字母大写"Hello World"？**  ####

```python
st = 'hello world'
st_s = st.split(' ')
print(list(x.capitalize() for x in st_s))
```
我觉得可以这么写。

#### **22、如何检测字符串中只含有数字?** ####

可以使用```isdigit()```的内置函数。 

#### **23、将字符串 ```"ilovechina"``` 进行反转?**  ####

（1）、

```python
st = 'hello world'
print(st[::-1])
```


（2）、 
```python
st = 'hello world'
def change_str(s):
    st_list = list(st)
    st_list.reverse()
    s = ''
    for i in st_list:
        s += i
    print(s)
change_str(st)
```
还有其他方法，暂时没写。

#### **24、Python 中的字符串格式化方式你知道哪些？** ####

1、

```Python
st = 'hello world'
print('%s' % st)

output：hello world
```
2、
```
st = 'hello world'
st_1 = 2
print('{0}{1}'.format(st, st_1))

output: hello world2
```
Python3中常用```format```格式化字符串，而且```{}```的索引要从0开始。否则会报错。 

#### **25、有一个字符串开头和末尾都有空格，比如 ```“ adabdw ”``` ,要求写一个函数把这个字符串的前后空格都去掉。**     ####

1、

```Python
s = ' adabdw '
print(s.strip())
output：adabdw
```

2、
```python
s = ' adabdw '
print(s.replace(' ', ''))
output：adabdw
```

#### **26、获取字符串”123456“最后的两个字符。**  ####

切片：

```Python
s = '123456'
print(s[-2:])
output：56
```

#### **27、一个编码为 GBK 的字符串 S，要将其转成 UTF-8 编码的字符串，应如何操作？**  ####

首先```encode```将字符串编码为```bytes```,```decode```将```bytes```解码成 `str` 。 
可以先将```GBK```解码成```Unicode```，再编码成```UTF-8```。 

![](https://user-gold-cdn.xitu.io/2019/8/26/16ccc8dbd188f51a?w=733&h=384&f=png&s=30952)
```s.decode('gbk').encode('utf-8')```   

#### **28、```s="info:xiaoZhang 33 shandong"```,用正则切分字符串输出 ```['info', 'xiaoZhang', '33', 'shandong']``` ？**  ####

```python
s = "info:xiaoZhang 33 shandong"
print(re.split(r" |:", s))
print(re.split(r":| ", s))
```

两种正则表达式最后输出的结果都是一样的。 

#### **27-1、怎样将字符串转换为小写？**  ####

```python
s = 'ABCDE'
print(s.lower())

output：abcde
```

```
s.upper() # 将字符串中的小写字母转换为大写
s.lower() # 将字符串中的大写字母转换为小写
str.capitalize() # 把第一个字母转化为大写字母，其余小写
str.title() # 把每个单词的第一个字母转化为大写，其余小写 
```

#### **28-1、单引号、双引号、三引号的区别？**  ####

在作为字符串变量的时候是没有区别的。如果引号之内还包含引号，那么外层的引号建议使用双引号。三引号的话可以作为多行注释或者多行字符串。 

#### **29、```a = "你好     中国  "```,去除多余空格只留一个空格。**  ####

```python
a = "你好     中国  "
print(re.sub(r" +", " ", a))
```

列表：

#### **30、已知 ``` AList = [1,2,3,1,2]``` ,对 ``` AList```  列表元素去重，写出具体过程。** ####

1、

```python
AList = [1, 2, 3, 1, 2]
print(list(set(AList)))
```

2、

```python
AList = [1, 2, 3, 1, 2]
blist = []
for i in AList:
    if i not in blist:
        blist.append(i)
print(blist)
```

#### **31、如何实现 "1,2,3" 变成 ["1","2","3"]？** ####

1、

```python
a = "1,2,3"
print(a.split(','))
```

2、
```python
a = "1,2,3"
b = []
for i in a:
    if i not in ', .':
        b.append(i)
print(b)
```

#### **32、给定两个 list，A 和 B，找出相同元素和不同元素。** ####

1、

```python
a = [1, 3, 4, 5, 9, 0]
b = [2, 3, 5, 7, 0]
same = []
diff = []
for i in a:
    if i in b:
        same.append(i)
    else:
        diff.append(i)

print(same)
print(diff)
```

2、修改之后。
```python
a = [1, 3, 4, 5, 9, 0]
b = [2, 3, 5, 7, 0]
same = []
diff = []
for i in a:
    if i in b:
        same.append(i)
        b.remove(i)
    else:
        diff.append(i)

print(same)
print(diff)
print(b)
```

这个方法可以找出```a```列表中和```b```列表相同和不同的元素。 

**33、[[1,2],[3,4],[5,6]]一行代码展开该列表，得出[1,2,3,4,5,6]？**

1、

```python
a = [[1, 2], [3, 4], [5, 6]]
print([x for i in a for x in i])
```

2、

```python
a = [[1, 2], [3, 4], [5, 6]]
s = []
for i in a:
    for j in i:
        s.append(j)
print(s)
```

#### **34、合并列表[1,5,7,9]和[2,2,6,8]。** ####

1、

```python
a = [1, 5, 7, 9]
b = [2, 2, 6, 8]
a.extend(b)
print(a)
```

2、
```python
a = [1, 5, 7, 9]
b = [2, 2, 6, 8]
for i in b:
    a.append(i)
print(a)
```
3、
```python
a = [1, 5, 7, 9]
b = [2, 2, 6, 8]
print(a+b)
```
#### **35、如何打乱一个列表的元素？**  ####

```python
a = list(range(20))
random.shuffle(a)
print(a)
```
每次打乱的顺序都不一样。  

字典：

#### **36、字典操作中 del 和 pop 有什么区别？**  ####

```pop``` :可以返回被删除的值。

```python
a = {'name': 'joy', 'age': 19, 'class': '2'}
print(a.pop('name'))
```
```del``` ：直接删除值，不返回。
```python
a = {'name': 'joy', 'age': 19, 'class': '2'}
del a['name']
print(a)
```
两段代码的结果是一样的。 

#### **37、按照字典的内的年龄排序。**  ####

```python
d1 = [
    {'name':'alice', 'age':38},
    {'name':'bob', 'age':18},
    {'name':'Carl', 'age':28},
]
```
可以这么写：
```python
d1 = [
    {'name':'alice', 'age':38},
    {'name':'bob', 'age':18},
    {'name':'Carl', 'age':28},
]
d1.sort(key=lambda k: k['age'])
print(d1)

output： [{'name': 'bob', 'age': 18}, {'name': 'Carl', 'age': 28}, {'name': 'alice', 'age': 38}]
```
使用```lambda```函数可以解决这个问题。 

```python
d1.sort(key=d1['age']) # 这么写会报错。
```
#### **38、请合并下面两个字典 a = {"A":1,"B":2},b = {"C":3,"D":4}。**  ####

1、使用```update```方法。

```python
a = {"A": 1, "B": 2}
b = {"C": 3, "D": 4}
print(a.update(b))
print(a)
```
2、应该称为构造函数法。可阅读性差，而且当```key```不是字符串的时候可能会报错。
```python
a = {"A": 1, "B": 2}
b = {"C": 3, "D": 4}
c = dict(a, **b)
print(c)
```
随后可以用生成式的方法合并两个字典，或者使用传统的方法。  

#### **39、如何使用生成式的方式生成一个字典，写一段功能代码。** ####

```python
b = {k: v for (k, v) in iterable}
```
其中```iterable```为可迭代对象，包括元组，字典。称为字典生成式。  

#### **40、如何把元组("a","b")和元组(1,2)，变为字典{"a":1,"b":2}**   ####

1、```zip```函数。

```python
a = ("a", "b")
b = (1,2)
c = dict(zip(a, b))
print(c)
```
2、匿名函数。
```python
a = ("a", "b")
b = (1,2)
c = dict(map(lambda x, y:[x, y], a, b))
print(c)
```
****
#### **41、Python 常用的数据结构的类型及其特性？** ####

```python
A：{1:0,2:0,3:0}
B：{"a":0, "b":0, "c":0}
C: {(1,2):0, (2,3):0}
D: {[1,2]:0, [2,3]:0}
```
列表不可以作为字典的键名。 

参考链接：https://blog.csdn.net/u014453898/article/details/56486519  

#### **42、如何将元组("A","B")和元组(1,2),合并成字典{"A":1,"B":2}？**  ####

参考40. 

#### **43、Python 里面如何实现 tuple 和 list 的转换？**  ####

```python
a = [1, 2, 3, 4]
b = tuple(a)
print(type(b))
# 列表转元组
c = (3, 4, 5, 6)
d = list(c)
print(type(d))
# 元组转列表
```
#### **44、我们知道对于列表可以使用切片操作进行部分元素的选择，那么如何对生成器类型的对象实现相同的功能呢？**  ####

首先应该将其实例化。

```python
a = [x for x in range(10)]
print(a)
```
这样```a```就是一个列表，同样可以进行切片操作。 

#### **45、请将 ```[i for i in range(3)]``` 改成生成器？**  ####

将```[]```改成```()```。

```python
a = (i for i in range(3))
print(a)

output：<generator object <genexpr> at 0x00000125DC9BFCF0>
```
生成器类型。 

#### **46、a="hello"和 b="你好"编码成 bytes 类型。**  ####

```python
a = "hello"
b = "你好"
print(type(a.encode()))
print(type(b.encode()))
```
#### **47、下面的代码输出结果是什么？** ####

```python
a = (1,2,3,[4,5,6,7],8)
a[2] = 2
```
上面的代码会报错，因为元组是一个不可变类型。其中的数据不可被修改，(可以索引，但是不能修改) 

#### **48、下面的代码输出的结果是什么?**  ####

```python
a = (1,2,3,[4,5,6,7],8)
a[5] = 2
```
这里元组```a```的第3个索引是一个列表，所以使用```a[3][1]```可以索引出列表中的5，而这个列表中的数据是可以修改的。 
## 四、操作类
#### **49、Python 交换两个变量的值。**  ####

1、交换两个变量的值。

```python
a = 1
b = 2
c = a
a = b
b = c
print(a)
print(b)
```
2、
```python
a = 1
b = 2
a = a + b
b = a - b
a = a - b
print(a)
print(b)
```
#### **50、在读文件操作的时候会使用 ```read、readline```  或者 ```readlines``` ，简述它们各自的特点。**  ####

1、```read()```方法： 
特点：读取整个文件，会将读取的内容放在一个字符串当中。 
劣势：当文件特别大的时候比较占内存，在大于内存的时候会无法使用这个函数。 
2、```readline()```方法： 
特点： ```readline()``` 方法每次读取一行；返回的是一个字符串对象，保持当前行的内存. 
缺点：比 ```readlines``` 慢得多。 
3、```readlines()```方法： 
特点：一次性读取整个文件；自动将文件内容分析成一个行的列表。 ```readlines()``` 读取所有行然后把它们作为一个字符串列表返回。  

#### **51、 ```json```  序列化时，可以处理的数据类型有哪些？如何定制支持 datetime 类型？**  ####

```JSON``` 序列化：将```Python```内置的数据类型序列化为```json```格式，用来做数据存储或者数据交换。 
基本内置的数据类型都可以，```dict```,```str```,```list```等。 
对于要支持```datetime```格式的话需要自定义一个类。

```python
class CJsonEncoder(json.JSONEncoder):

    def default(self, obj):
        if isinstance(obj, datetime):
            return obj.strftime('%Y-%m-%d %H:%M:%S')
        elif isinstance(obj, date):
            return obj.strftime('%Y-%m-%d')
        else:
            return json.JSONEncoder.default(self, obj)
```
如果不想定义类，直接在我们获取的date或者datetime对象后面用上```strftime```方法进行格式化也可以。 
参考：https://cloud.tencent.com/developer/article/1098709   

#### **52、 ```json```  序列化时，默认遇到中文会转换成  ```unicode``` ，如果想要保留中文怎么办？**  ####

```python
def xml_to_json(file_path):
    str_xml = open(file_path, encoding='utf-8')
    all_xml_str = str_xml.read()
    con_json = xmltodict.parse(all_xml_str, encoding='utf-8')
    str_json = json.loads(json.dumps(con_json, ensure_ascii=False))
    return str_json
```

这个个函数可以将```xml```格式的文件转换成```json```。 
其中，```dump```和```dumps```都是实现了序列化。```load```和```loads```都实现了反序列化。中文会转成```unicode```，在序列化的函数内加上一个参数```ensure_ascii=False```就可以保留中文。 
参考：https://www.cnblogs.com/bigtreei/p/10466518.html  

53、有两个磁盘文件 A 和 B，各存放一行字母，要求把这两个文件中的信息合并(按字母顺序排列)，输出到一个新文件 C 中。 
先读取文件，存入变。将两个字符串相加，然后对 C 字符串进行排序。 
```python
s = 'cdabvf'
s_list = list(s)
s_list.sort()
print(s_list)
print(''.join(s_list))
```
可以先将字符串转为列表，但是当字符串数量很大的时候，转成列表之后会消耗很多的系统资源。 
还可以使用匿名函数的解法。 

#### **54、如果当前的日期为 20190530，要求写一个函数输出 N 天后的日期，(比如 N 为 2，则输出 20190601)。**  ####

```python
def get_day(n):
    now_time = datetime.datetime.now()
    d = now_time + datetime.timedelta(n)
    print("{0}天后的日期是:{1}".format(n, str(d)[:11]))

get_day(100)
```
这样的输出格式为```2019-08-08```，而且是利用了类型转化加切片。
```python
def get_day(n):
    if type(n) is int:
        now_time = datetime.datetime.now()
        print("今天是{0}".format(str(now_time).replace('-', '')[:9]))
        d = now_time + datetime.timedelta(n)
        if n > 0:
            print("{0}天后的日期是:{1}".format(n, str(d).replace(r'-', '')[:9]))
        elif n == 0:
            print("就是今天哦！")
        else:
            print("{0}天前的日期是:{1}".format(n*-1, str(d).replace(r'-', '')[:9]))
    else:
        print("输入的不是整数.")

get_day(1)
```
稍作修改之后就可以了。 

#### **55、写一个函数，接收整数参数 n，返回一个函数，函数的功能是把函数的参数和 n 相乘并把结果返回。**  ####

类似于一个闭包函数，闭包的讲解参考： 
https://foofish.net/python-closure.html 
https://www.cnblogs.com/Lin-Yi/p/7305364.html 

```python
def f1(n):
    def f2(*args):
        s = 10
        return s * n
    return f2
print(f1(2)())
```

返回内层函数，然后调用内层函数。  

#### **56、下面代码会存在什么问题，如何改进？**  ####

```python
def strappend(num):
    str='first'
    for i in range(num):
        str+=str(i)
    return str
```

1、对于变量的命名不应该使用保留字```str```，在 IDE 中会出现如下提示：会出现不能调用的情况。

![](https://user-gold-cdn.xitu.io/2019/8/28/16cd6e39c99cb7f6?w=812&h=193&f=png&s=27593)

2、其实对于```num```有可能为其他类型，或者说为负数，都会造成代码运行失败。返回值也是```str```，还是和保留的关键字重名了。 

#### **57、一行代码输出 1-100 之间的所有偶数。**  ####

1、使用列表生成式可以实现：

```python
print([i for i in range(0, 100, 2)])
```
2、直接使用```range```也可以实现。
```python
print(list(range(0, 101, 2)))
```
58、with 语句的作用，写一段代码？ 

with 在 Python 3.5 的时候加入到 Python 中，用来代替```try...except...finally```。

with 常用在对于文件的操作中：

```python
with open("filename") as f:
    # do something
    f.readline()
    f.close()
```
#### **59、python 字典和 ``` json```  字符串相互转化方法。**  ####

在 51 题关于```json```序列化的问题中，参考 51。 

#### **60、请写一个 Python 逻辑，计算一个文件中的大写字母数量**。  ####

参考：https://www.cnblogs.com/stono/p/9102043.html 
```file_path``` 为文件路径，暂时不完善。

```python
def coune(file_path):
    res = open(file_path)
    res_l = res.read()
    counter = 0
    up = []
    for i in res_l:
        if i.isupper() == True:
            up.append(i)
            counter += 1
    print(up)
    print(counter)

coune(file_path)
```
## 五、高级特效 ##

#### **70、函数装饰器有什么作用？请列举说明？**  ####

在原有功能不改变，或者不修改任何代码的情况下，给原有的功能添加新的功能。它经常用于有切面需求的场景，比如：插入日志、性能测试、事务处理、缓存、权限校验等场景，装饰器是解决这类问题的绝佳设计。概括的讲，装饰器的作用就是为已经存在的对象添加额外的功能。 
参考：https://foofish.net/python-decorator.html 

#### **71、Python 垃圾回收机制？**  ####

参考：https://testerhome.com/topics/16556  
https://www.cnblogs.com/Xjng/p/5128269.html  

#### **72、魔法函数 call怎么使用?**  ####

```__call__``` 的作用就是让一个类也可以像一个函数一样可以拿来调用。 
参考：http://www.langzi.fun/Python%E9%AD%94%E6%B3%95%E5%87%BD%E6%95%B0.html  

#### **73、如何判断一个对象是函数还是方法？**  ####

一般情况下，函数和方法似乎分界不明确。一般来讲，与类实例绑定的函数称为方法，与类实例不绑定的函数就称为函数。可参考：https://www.cnblogs.com/blackmatrix/p/6847313.html  

#### **74、```@classmethod``` 和 ```@staticmethod```  用法和区别？**  ####

分别为类方法和静态方法： 
```@staticmethod``` 不需要表示自身对象的self和自身类的 ```cls``` 参数，就跟使用函数一样。
```@classmethod``` 也不需要 self 参数，但第一个参数需要是表示自身类的 ```cls``` 参数。 
参考：https://blog.csdn.net/handsomekang/article/details/9615239  

#### **75、Python 中的接口如何实现？**  ####

接口只是定义了一些方法，而没有去实现，多用于程序设计时。只是设计需要什么样的功能，但是并没有实现任何功能，有些功能需要被另外的 B 类继承之后，由 B 类重写方法来实现相应的功能。 
遵循：开放封闭原则，依赖导致原则，接口隔离原则，继承多态。 
参考：https://blog.csdn.net/weixin_42181824/article/details/81874725   

#### **76、Python 中的反射了解么?**   ####

其实，反射就是通过字符串的形式，导入模块；通过字符串的形式，去模块寻找指定函数，并执行。利用字符串的形式去对象（模块）中操作（查找/获取/删除/添加）成员，一种基于字符串的事件驱动！ 
参考：https://www.cnblogs.com/vipchenwei/p/6991209.html  

#### **77、```metaclass``` 作用？以及应用场景？**  ####

参考：https://www.cnblogs.com/JetpropelledSnake/p/9094103.html  
元类，在 Python 2.2 中引入，它的作用是定制类的创建行为。（Python 中一切皆对象，包括类。） 
type 函数的特点，接受参数，并且返回参数的类型。另一方面， type 还可以动态的创建一个类，

```python
# type(类名, 父类的元组（针对继承的情况，可以为空），包含属性的字典（名称和值）)
```
在使用 class 的时候在内部就是这种操作。而 type 函数实际就是一个元类，是在背后用来创建类的元类。关于 ```metaclass``` 属性，可以在类中添加这个属性。比如：
```python
class Foo(object):
    __metaclass__ = something
```
在创建 Foo 类的时候，开始并没有在内存中创建，而是先在类定义内搜索 ```__metaclss__``` 属性，如果有那就用它来创建这个类，如果没有找到，那就是用 type 来创建这个类。如果有继承，那就会在父类中寻找，其次就是会在模块级别寻找。这样会使 

#### **78、```hasattr() getattr() setattr()``` 的用法？**  ####

```hasattr()``` : 用于判断对象是否包含相应的属性。```hasattr(object, name)``` ，其中 object 为对象名， name 为属性名称。如果有该属性返回 True，否则返回 False。 
```getattr()``` ：用于返回一个对象的属性值。```getattr(boject, name, default)```，其中 object 为对象名，name 为属性名，default 为默认值。假如所 get 的属性不存在，则将 default 的值赋给 name 属性。 
```setattr()``` ：用于设置一个属性，对应 ```getattr()``` ，但是所设置的的属性不一定存在。```setattr(object, name, value)```，object 为对象名，name 为属性名，value 为属性值。如果属性本来存在，那么使用这个函数之后的 value 会覆盖之前属性的值。 

#### **79、请列举你知道的 Python 的魔法方法及用途。**  ####

参考：https://www.cnblogs.com/seablog/p/7173107.html  
```__init__``` ：构造器，当一个实例被创建之后调用的初始化方法。 
```__del__``` ：析构器，当一个实例被销毁的时候调用的方法。 
```__call__``` ：允许一个类的实例像函数一样被调用。 
链接中有很多的魔法方法... 

#### **80、如何知道一个 Python 对象的类型？**  ####

使用 type 函数，```type(value)``` 为查看 value 的类型，包括基本的数据类型，函数方法，也包括类的类型。 

#### **81、Python 的传参是传值还是传址？**  ####

传值和传址都不是非常准确，在 Python 中所有东西都是对象，变量是不存在类型的，使用 type 函数查看的其实是那个对象值的类型，而非变量的类型。 
参考：https://foofish.net/python-function-args.html  

#### **82、Python 中的元类 ```(metaclass)``` 使用举例？** ####

pass  

#### **83、简述 any()和 all()方法?**   ####

```any()``` ：Python 2.5 以上版本可用。any() 函数用于判断给定的可迭代参数 ```iterable``` 是否全部为 False，则返回 False，如果有一个为 True，则返回 True。元素除了是 0、空、FALSE 外都算 TRUE。```any(iterable)``` ```iTerable``` 为可迭代对象。 
```all()``` ：Python 2.5 以上版本可用。all() 函数用于判断给定的可迭代参数``` iterable``` 中的所有元素是否都为 TRUE，如果是返回 True，否则返回 False。元素除了是 0、空、None、False 外都算 True。用法同上。 

#### **84、filter 方法求出列表所有奇数并构造新列表，a =  [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]。**  ####

filter 方法用于过滤序列，过滤掉不符合条件的元素，返回一个符合条件的序列。该接收两个参数，第一个为函数，第二个为序列，序列的每个元素作为参数传递给函数进行判，然后返回 True 或 False，最后将返回 True 的元素放到新列表中。 
**在 Python 2.7 中返回列表，在Python 3 中返回一个迭代器对象。**  
```filter(function, ieerable)``` ，function 为判断函数，```iterable``` 为可迭代对象。 
1、定义一般函数。

```python
a = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
def change(n):
    return n % 2 == 0
print(list(filter(change, a)))
```
2、使用 lambda 函数。

```python
a = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
print(list(filter(lambda x: x % 2 == 0, a)))
```
#### **85、什么是猴子补丁？**  ####

即在运行时对方法 / 类 / 属性 / 功能进行修改，把新的代码作为解决方案代替原有的程序，也就是为其打上补丁。

```python
class Foo(object):
    def fun1(self):
        print('This is fun1')

def fun2(**args):
    print('Thsi is fun2')

def fun3(**args):
    print('This is fun3')

f = Foo()
f.fun1 = fun2
print(f.fun1())
f.fun1 = fun3
print(f.fun1())
```
通过代码可以看见，类外的方法 fun2 和 fun3 可以通过赋值覆盖掉类内的方法 fun1 。在使用的时候也容易出问题： 
* 当进行版本更新变化的时候，很容易对补丁做出破坏
* 不知情的情况下对一个位置打两个补丁会造成替换，补丁替换补丁。
* 对于不知道有补丁的人来说可能会对出现的某些情况感到困惑

#### **86、在 Python 中是如何管理内存的？**  ####

在 Python 中，对象和引用分离，```a = 1```，a 就是引用，1 就是对象，通过```id()``` 可以查看对象 1 在内存中的地址。

```python
a = 1
b = 1
print(id(a))
print(id(b))
```
#### **87、当退出 Python 时是否释放所有内存分配？** ####



### 正则表达式： ###

#### **88、使用正则表达式匹配出 `<html><h1>www.baidu.com</html>` 中的地址** ####

```reStructuredText
[a-z]+.[a-z]+.[a-z]+
```

可以匹配出网址。

a="张明 98 分"，用 `re.sub`，将 98 替换为 100。

```python
def regular():
    a = "张明 98 分"
    result = re.sub('[0-9]+', '100', a)
    print(result)
```

上面会将 98 替换成 100。

#### **89、正则表达式匹配中`(.*)`和`(.*?)`匹配区别？** ####

一个是贪婪匹配，一个是非贪婪匹配。贪婪匹配会尽可能的匹配出更多的东西，非贪婪匹配则是尽可能匹配少的东西，满足条件即可。

#### **90、写一段匹配邮箱的正则表达式** ####

```
[0-9A-Za-z]+@[0-9a-zA-Z]+.[a-z]+
```

上面的正则可以匹配出邮箱。

## 六、其他内容 ##

#### **91、解释一下 python 中 pass 语句的作用？** ####

pass 语句主要是占位符，保持代码结构的完整性，使得代码能顺利的运行下去。

#### **92、简述你对 input()函数的理解** ####

在 Python3 中，合并成为了一个 `input()` 函数。但是接收到的内容是作为字符串传入的，如果需要传入数字，则需要进行类型转换。

#### **93、python 中的 is 和==**  ####

== 作为判断相等符号，只是判断两个变量的值是否想等，并不会判断两个变量的数据类型。而 is 不仅会判断两者的值，还会判断两个的数据类型是否想等，如果不同，则会返回 `false`。

#### **94、Python 中的作用域** ####

*大致分为 4 种：L （Local） 局部作用域 、E （Enclosing） 闭包函数外的函数中 、G （Global） 全局作用域 、B （Built-in） 内建作用域。* 

#### **95、三元运算写法和应用场景？** ####

```python
result = value1 if condition else value2
```

意思是：如果 `condition` 为真，则返回 `value1` 否则返回 `value2` 。

三元运算符可以节省代码量，使代码更加简洁，增加可读性。在一些简单的场景可以省去 `if...else...` 的判断语句。

#### **96、了解 enumerate 么？** ####

`enumerate` 是 Python 的内建对象，常常用在循环当中，传入可迭代对象。

```python
b = ['a', 'b', 'c']
for i, j in enumerate(b):
    print(i, ':', j)
```

返回结果是，一个索引和一个列表里面的内容。

#### **97、列举 5 个 Python 中的标准模块** ####

`os, sys, math, re, datetime, itertools, pathlib, random` 等。

#### **98、如何在函数中设置一个全局变量**  ####

在作用域的问题中，全局变量可以设置在最顶层。第二种方法是在一个地方使用 `globe` 关键字声明。

#### **99、`pathlib` 的用法举例** ####

参考：https://www.dongwm.com/post/use-pathlib/

用法更加简洁。

#### **100、Python 中的异常处理，写一个简单的应用场景** ####

代码结构如下：（函数形式）

```python
def catch_error():
    try:
        pass
    except Exception as e:
        print(e)
```

在 pass 那里写可能出错的代码。如果出现异常，则会将错误信息输出。

#### **101、Python 中递归的最大次数，那如何突破呢？**  ####

针对计算机的环境不一样，最大的递归深度也是不一样的，我本机的最大递归深度为 1000 次左右。

```python
import sys
sys.setrecursionlimit(2000)
```

上面可以使得最大的递归次数达到 2000 次。

#### **102、什么是面向对象的 `mro`**  ####

因为 Python 支持多重继承，那么方法解析顺序 `MRO（Method Resoluthion Order）` ，就出现了。

*这时有两种MRO的方法：*

1. 如果是经典类MRO为DFS（深度优先搜索（子节点顺序：从左到右））。
2. 如果是新式类MRO为BFS（广度优先搜索（子节点顺序：从左到右））。

参考：https://blog.csdn.net/weixin_40907382/article/details/80277152

#### **103、`isinstance` 作用以及应用场景？** ####

```python
isinstance(object, classinfo)
```

判断 `object` 是不是 `classinfo` 的类型。

实例：

```python
def isins():
    """
    isinstance 的用法...
    """
    a = 2
    print(isinstance(a, int))
```

上面是函数形式，下面输出结果会是 True。

#### **104、什么是断言？应用场景？** ####

断言，`assert` ，结构如下：

```python
assert expression
```

断言会在程序遇到错误的时候暂停运行，同时弹出报错窗口，前提是 `expression` 为 false。

#### **105、lambda 表达式格式以及应用场景？** ####

lambda 作为一个表达式，定义了一个匿名函数，lambda 简化了函数定义的书写形式。

```python
def lamda(x):
    """
    lambda 匿名函数的使用...
    """
    result = lambda x: x ** 2
    print(result(x))
```

上面为函数形式的 lambda 匿名函数。输出的结果为 x 的平方。lambda 配合 `map()` 函数可以达到很好的效果，简洁了代码，提高了代码的可读性。

#### **106、新式类和旧式类的区别**  ####

1.  新式类对象可以直接通过 `__class__` 属性获取自身类型: type。

2.   继承搜索的顺序发生了改变,经典类多继承属性搜索顺序: 先深入继承树左侧，再返回，开始找右侧;新式类多继承属性搜索顺序: 先水平搜索，然后再向上移动。

3.   新式类增加了`__slots__` 内置属性, 可以把实例属性的种类锁定到 `__slots__` 规定的范围之中。

4.  新式类增加了`__getattribute__` 方法。

    参考：https://blog.csdn.net/u010066807/article/details/46896835

#### **107、`dir()` 是干什么用的？** ####

`dir()`   函数不带参数时，返回当前范围内的变量、方法和定义的类型列表；带参数时，返回参数的属性、方法列表。如果参数包含方法`__dir__()`，该方法将被调用。如果参数不包含`__dir__()` ，该方法将最大限度地收集参数信息。

使用方法如下：传入一个对象，这个对象可以使用的方法！

```python
dir(object)
```

实例：

```python
def dir_method():
    """
    dir() 内置函数的使用方法...
    """
    a = []
    b = 1
    print(dir(b))
    print(dir(a))
```

返回的是一个列表，内容为本对象可以调用的方法。

#### **108、一个包里有三个模块，demo1.py, demo2.py, demo3.py，但使用 from tools import *导入模块时，如何保证只有 demo1、demo3 被导入了。**  ####



#### **109、列举 5 个 Python 中的异常类型以及其含义**  ####

1.   `SyntaxError  Python` 语法错误

2.   `RuntimeError`  一般的运行时错误

3.   `TypeError`	对类型无效的操作

4.   `IndentationError`	缩进错误

5.   `ValueError	` 传入无效的参数

    除此之外，还包括超出索引范围，类型错误，未定义变量之类的错误。

#### **110、110. `copy` 和 `deepcopy` 的区别是什么？**  ####

参考：https://www.cnblogs.com/shiyublog/p/11078313.html

浅拷贝不会重新划一块内存，而是指向同一块内存，相当于同一块内存中的对象有两个名字，其中一个名字让这个对象改变的时候，另一个名字指的内容也发生了改变。

深拷贝就是在内存中重新划一块地方给新的变量，新旧互不影响。

#### **111、代码中经常遇到的`*args`, **`kwargs` 含义及用法。** ####

前者将传入的参数打包成元组传递给函数中使用，后者将传入的参数打包成字典，传递到函数中使用。通过 `type()` 函数可以查看两个参数的类型，前者为 `tuple` ，后者为 `dict` 。

#### **112、Python 中会有函数或成员变量包含单下划线前缀和结尾，和双下划线前缀结尾，区别是什么? **  ####

一般来讲，下划线开头的变量名都有特殊含义，所以一般情况下不建议使用下划线开头的变量名。

参考：https://zhuanlan.zhihu.com/p/36173202

1.   单下划线开头：这类变量名或者方法仅仅供内部使用。
2.   单下划线结尾：用来避免与 Python 的关键字进行冲突。
3.   双下划线开头：双下划线前缀会导致Python解释器重写属性名称，以避免子类中的命名冲突。
4.   前后单下划线：这类方法通常被称为魔法方法。

![preview](https://pic3.zhimg.com/v2-cbc5c6037101c7d33cf0acd9f00a8cfa_r.jpg)

#### **113、`w、a+、wb ` 文件写入模式的区别** ####

参考：https://blog.csdn.net/qq_32648375/article/details/83342094

#### **114、举例 sort 和 sorted 的区别**  ####

sort 只是应用在 list 上的方法，（就地排序无返回值）。

sorted 是内建函数，可对所有可迭代的对象进行排序操作，（返回新的list）。

#### **115、什么是负索引？**  ####

在一个可迭代对象里，内容和索引是一一对应的，索引从 0 开始。那么负索引就是 -1，-2，等等，意味着从末尾索引到第一个内容。

#### **116、`pprint`  模块是干什么的？** ####

 `print()` 和 `pprint()` 都是 python 的打印模块，功能基本一样，唯一的区别就是 `pprint()` 模块打印出来的数据结构更加完整，每行为一个数据结构，更加方便阅读打印输出结果。特别是对于特别长的数据打印，print()输出结果都在一行，不方便查看，而 `pprint()` 采用分行打印输出，所以对于数据结构比较复杂、数据长度较长的数据，适合采用 `pprint()` 打印方式。

原文链接：https://blog.csdn.net/qq_24185239/article/details/80977556

#### **117、解释一下 Python 中的赋值运算符**  ####

#### **118、解释一下 Python 中的逻辑运算符**  ####

#### **119、讲讲 Python 中的位运算符**  ####

参考：https://www.cnblogs.com/z-x-y/p/9909772.html

#### **120、在 Python 中如何使用多进制数字？**  ####

参考：https://www.cnblogs.com/z-x-y/p/9909821.html

#### **121、怎样声明多个变量并赋值？**  ####

```python
a, b = 1, 2
```

## 七、算法数据结构 ##

#### 122、已知： ####

```python
AList = [1,2,3]
BSet = {1,2,3}
```

**(1) 从 `AList`  和 `BSet` 中 查找 4，最坏时间复杂度那个大？**

**(2) 从 `AList` 和 `BSet` 中 插入 4，最坏时间复杂度那个大？** 

```python
def time_complex():
    """
    时间复杂度.....
    """
    t1 = time.time()
    a = [1, 2, 3, 4]
    b = {1, 2, 3, 4}
    # a.append(5)
    b.add(5)
    print(b)
    t2 = time.time() - t1
    print(t2)
```

#### **123、用 Python 实现一个二分查找的函数** ####

部分代码如下：

```python
def find_fun_num(l: list, n):
    """
    二分算法.....

    """
    if isinstance(l, list):
        if len(l) != 0:
            l.sort()
            # print(len(l))
            mid = Decimal(3)
            mid = mid.quantize(Decimal('0'), rounding=ROUND_HALF_UP)    # 消除逢5不进的情况。
            if l[mid] == n:
                return n
            
        else:
            print("列表长度为0：")
    else:
        print("l 不是列表")
```

上面的代码不完整，只是进行到了一点点。

#### **124、python 单例模式的实现方法** ####

 

#### **125、使用 Python 实现一个斐波那契数列**   ####

```python
def fib(n):
    """
    斐波那契数列...
    """
    a, b = 0, 1
    for i in range(n):
        a, b = b, a + b
        print(a)
```

上面代码简单的实现了斐波那契数列。

#### **126、找出列表中的重复数字**  ####

一种比较简单的方法：使用内置模块可以快速找到。

```python
from collections import Counter

l = [1, 2, 12, 14, 54, 9, 0, 10, 12, 11]
res = Counter(l)
print(res[12])
print(type(res))
```

另外一种就是自己写一个函数实现这个功能。

```python
def find_same_num(l: list):
    """
    查找列表中重复的数字...
    """
    same_number = {}
    if isinstance(l, list):
        for i in l:
            same_number[i] = l.count(i)
    else:
        print("l不是列表")
    print(same_number)
```

另一种方法：

```python
def find_same_num(l: list):
    """
    查找列表中重复的数字...
    """
    new_ls = []
    same_number = []
    if isinstance(l, list):
        for i in l:
            if i not in new_ls:
                new_ls.append(i)
            else:
                same_number.append(i)
    else:
        print("l不是列表")
    print('重复的内容有:',same_number)
```

这种方法其实不是很完善，而且比较冗余，能查出来是哪些内容重复了，但是不太方便统计出重复了多少次。需要另外编写函数给其调用。

#### **127、找出列表中的单个数字**  ####

```python
def find_num_one(l: list):
    """
    查找列表中的单位数数字.....
    """
    if isinstance(l, list):
        for i in l:
            # print(i)
            if len(str(i)) == 1:
                print(i)
    else:
        print("l is not list type")
```

上面同样是函数形式的，因为一个函数实现一个功能，比较整体。这个是遍历列表中的每个元素，判断每个元素的长度来判断是不是单个字符的。

#### **128、写一个冒泡排序**  ####

```python
def bubble_sort(l: list):
    """
    冒泡排序.....
    """
    if isinstance(l, list):
        for i in range(len(l)-1):
            for j in range(len(l) - 1):
                if l[j] > l[j + 1]:
                    l[j], l[j + 1] = l[j+1], l[j]
    else:
        print("l is not list type")
    print(l) 
```

参考自网上的版本。使用两层循环，减少循环次数可以一定程度上节省资源。

#### **129、写一个快速排序**  ####

#### **130、写一个拓扑排序** ####

#### **131. python 实现一个二进制计算**  ####

#### **132、有一组“+”和“-”符号，要求将“+”排到左边，“-”排到右边，写出具体的实现方法。**  ####

```python
def change_add(s: str):
    """
    改变 + - 的位置。
    """
    ad = ''
    le = ''
    for i in s:
        if i == '+':
            ad += i
        else:
            le += i
    result = ad + le
    print(result)
```

定义两个字符串，将 + 和 - 分别添加到两个字符串当中，然后将两个字符串相加。

#### **133、单链表反转**  ####

#### **134、交叉链表求交点**  ####

#### **135、用队列实现栈** ####

#### **136、找出数据流的中位数** ####

#### **137、二叉搜索树中第 K 小的元素** ####

## 八、爬虫相关 ##

#### **138、在 requests 模块中，`requests.content` 和 `requests.text` 什么区别**  ####

两者返回结果的编码不同。`requests.text` 返回的是 `Unicode` 编码，`requests.content` 返回的是 `bytes` 编码，也就是 2 进制编码。

如果想保存文本，使用 text ，如果想保存图片或者其他格式，使用 content 。

#### **139、简要写一下 `lxml` 模块的使用方法框架**  ####

```python
import lxml
from lxml import etree
```

加载模块，作为网页解析的核心，性能也是比较好的。当然，也可以从 `lxml` 中导入 `etree` 模块，这样就可以使用 `Xpath` 选择器进行提取数据。

#### **140、说一说 `scrapy` 的工作流程**  ####

参考 `scrapy` 文件。

#### **141、`scrapy` 的去重原理** ####

对于每一个`url`的请求，调度器都会根据请求得相关信息加密（类似于MD5）得到一个指纹信息，并且将指纹信息和自己维护的一个集合中的`url`指纹信息进行比对，如果集合中已经存在这个指纹，就代表出现重复请求，就不再将这个Request放入队列中。如果集合中没有存在这个指纹，就将这个Request对象放入队列中，等待被调度。

一般在request请求的参数中加入`dont_filter=False`可以关闭去重，方便重复爬取同一网站下不同页面的信息。也可以通过修改爬取规则如`start_url`等或自定义爬取`url`作为请求的参数以避免不必要的去重。

#### **142、`scrapy` 中间件有几种类，你用过哪些中间件**  ####

下载中间件（Downloader Middleware）和爬虫中间件（Spider Middleware）

#### **143、你写爬虫的时候都遇到过什么？反爬虫措施，你是怎么解决的**  ####

1.   模拟登录的问题，登录状态需要使用`cookies` 。一般可以先手动操作登录之后，记录 `cookies` 将其作为 `headers` 的一个参数传给请求。第二种方法可以自动获取 `cookies` 然后作为独立的参数传给下一次请求。
2.   IP 被禁止的问题，如果一个 IP 在过短的时间内访问一个网站很多次，那么很有可能被判定成为机器人，然后 IP 就被禁止访问了。
3.   编码问题，这个问题主要出现在需要打印网页源代码和保存文件或者文本数据的时候。

#### **144、为什么会用到代理？**  ####

代理可以很好的隐藏自己的 IP 地址，不至于让自己的 IP 被封禁，以至于爬虫不能进行下去。

#### **145、代理失效了怎么处理？** ####

 代理失效的话一般有两种情况，第一就是 这个代理被封了，第二个就是代理服务器的问题。需要检测的话可以使用正在使用的代理访问其他网站，如果可以正常访问那就证明这个代理在所需要爬取的网站被封禁了。需要更换更加隐秘的代理。

#### **146、列出你知道 header 的内容以及信息**  ####

1.   UA：浏览器标识。

2.   `cookies` ：用户登录标识。

3.   `method`：请求方法，主要为 `get` 和 `post` 。

    需要注意的的是，`headers` 分为两个，一个是 `request headers` 另外一个是 `response headers` ，这两个一个是给服务器发送数据的请求头，一个是从服务器返回数据的头部信息。

#### **147、说一说打开浏览器访问` www.baidu.com `获取到结果，整个流程。**   ####

参考：https://blog.csdn.net/yonggeit/article/details/72857630

#### **148、爬取速度过快出现了验证码怎么处理。**  ####

一般来讲，验证码的类型也有很多种。在爬取的时候最好实用时间延时，间隔几秒访问一次，这样可以一定程度上防止出现验证码，但是如果真的出现了，那还是需要进行破解的。破解方法暂不介绍！

#### **149、`scrapy` 和 `scrapy-redis` 有什么区别？为什么选择 `redis` 数据库？** ####

 `scrapy` 是一个**爬虫框架**，本身不支持分布式爬虫。然而 `scrapy-redis` 是运行在框架上面的**组件**，不是框架。可以使得原本的框架支持分布式，算是对原本框架的补充。

*选择`redis` 的原因因为，`redis`支持主从同步，而且数据都是缓存在内存中的，所以基于`redis`的分布式爬虫，对请求和数据的高频读取效率非常高。*

#### **150、分布式爬虫主要解决什么问题**  ####

首先，如果不是分布式的爬虫，如果有1000条 URL 那么会按照次序一个个进行爬取，这样的效率是很低的。而且每次爬取的结果的存储也是一个问题，需要大量的I/O计算。**分布式** 的话，首先解决的是爬取效率低的问题，可以将 URL 分在几台机器上，或者几个项目文件中，然后分别进行爬取。第二个是对于大量的 I/O 计算可以在不同的几台机器上共同进行，实现了真正的并行，效率会提高很多。

#### **151、写爬虫是用多进程好？还是多线程好？为什么？** ####

首先要知道，爬虫程序是一个 I/O 集群型的，需要大量的 I/O 计算。对于需要大量写入的程序，多线程是个更好的选择。对于多进程来讲，多进程可以同时执行几个程序，最好的情况是多进程下面开多个线程。

#### **152、解析网页的解析器使用最多的是哪几个**  ####

`lxml` 应该是比较方便的，可以使用在 `BeautifulSoup` 中，也可以单独拿出来使用 `etree` 来解析网页，然后使用`Xpath` 提取数据。

具体可以参考`BeautifulSoup` 的官方文档。其中讲解了各个解析器之间的优劣。

#### **153、需要登录的网页，如何解决同时限制 `ip`, `cookie`, `session`（其中有一些是动态生成的）在不使用动态爬取的情况下？**  ####

遇到动态生成的 `cookies` 的情况就不能复制 `cookies` 作为一个变量了，需要使用下面的方法获取 `cookies`。

```python
r = requests.get(url=url_1, headers=headers, timeout=3)
cookie = r.cookies # 获取网站的cooKies
```

#### **154、验证码的解决（简单的：对图像做处理后可以得到的，困难的：验证码是点击，拖动等动态进行的？）**  ####



#### **155、使用最多的数据库（`mysql`，`mongodb`，`redis` 等），对他的理解？**   ####

`mysql` 是关系型数据库的一种，后面两种是非关系型数据库。对应在数据库中就是一个个表，满足关系型数据库的 ACID 基本原则。

`mongodb` 和 `redis` 是非关系型数据库，也就是 NoSQL。不仅仅是数据库。用过 `redis` ，它是通过键和值对应来存储数据，一个键对应一个数据，这个数据可以是字符串类型，列表类型，集合类型等等。

## 九、网络编程 ##

#### **156、TCP 和 UDP 的区别？**  ####

参考：

https://blog.csdn.net/Li_Ning_/article/details/52117463 

https://zhuanlan.zhihu.com/p/24860273

TCP/IP协议是一个协议簇。里面包括很多协议的，UDP只是其中的一个， 之所以命名为TCP/IP协议，因为TCP、IP协议是两个很重要的协议，就用他两命名了。

TCP/IP协议集包括应用层,传输层，网络层，网络访问层。

#### **157、简要介绍三次握手和四次挥手** ####

 

#### **158、什么是粘包？socket 中造成粘包的原因是什么？哪些情况会发生粘包现象？**  ####



## 十、并发 ##

#### **159、举例说明 `conccurent.future` 的中线程池的用法**  ####



#### **160、说一说多线程，多进程和协程的区别。**  ####

参见文件 12。

关于进程、线程、协程的关系：https://www.cnblogs.com/lxmhhy/p/6041001.html

协程又叫微线程，子程序或者成为函数，在所有语言中都是层级调用的，比如A调用B，B在执行过程中又调用了C，C执行完毕返回，B执行完毕返回，最后是A执行完毕。

所以子程序调用是通过栈实现的，一个线程就是执行一个子程序。

子程序调用总是一个入口，一次返回，调用顺序是明确的。而协程的调用和子程序不同。

协程看上去也是子程序，但执行过程中，在子程序内部可中断，然后转而执行别的子程序，在适当的时候再返回来接着执行。

#### **161、简述 GIL**  ####

全局解释器锁（GIL）：

参考：https://blog.csdn.net/SQA_STAR/article/details/81037781 

#### **162、进程之间如何通信**  ####



#### **163、IO 多路复用的作用？**   ####



#### **164、`select`、`poll`、`epoll` 模型的区别？**   ####



#### **165、什么是并发和并行？解释什么是异步非阻塞？****  ####

参见文件12 。

#### **168、`threading.local` 的作用？**  ####



## 十一、Git ##

#### **169、说说你知道的 git 命令**  ####

参考：http://www.phpernote.com/linux/1362.html

包括问题170。

```
git pull 
git add 
git push 
```

#### **170、git 如何查看某次提交修改的内容x**  ####

