## 一、语言特性
**1、Python语言和其他语言的区别**</br>
Python是解释性语言，与编译型语言不同，相对来讲解释型语言的运行速度没有编译型语言快。另一方面Python的语法简单明了，
不需要声明变量的数据类型，而且Python的跨平台性很好、可以运行在Windows、Mac、Linux上面。

**2、简述解释型语言和编译型语言：**<br>
编译型语言：在程序运行之前有一个专门的编译过程，把程序变异成机器语言的文件，再次运行时不需要重新翻译，直接使用翻译结果，效率高，依赖编译器。
解释型语言：不用预先进行编译，以文本的方式存储代码，在运行的时候需要先进行解释才能能运行。意思就是，每次重新运行的话就要重新解释，运行的效率较低。
动态语言：在代码运行的时候可以根据某些条件来改变自身的结构。可以引入其他的对象，代码，函数等。
静态语言：运行时代码结构不能被改变。
强类型语言：一个变量如果被指定某个数据类型，若不经过强制转换，那就永远是这个类型。
弱类型语言：数据类型可以被忽略。根据赋值的不同改变不同的数据类型。
动态类型语言（指数据结构）和动态语言（指代码结构）是不一样的。<br><br>
**3、Python 的解释器种类以及相关特点？**<br>
解释器版本：
```Cpython``` 、```Ipython``` 、```PyPy```、```Jython```、```IronPython```。```Ipython``` 基于```Cpython``` ，只是在交互方式上面做了优化，其他的功能和 ```Cpython``` 是一样的。```Jython```是运行在```Java```平台上的解释器。``` IronPython``` 和 ```Jython``` 类似，只不过```IronPython```是运行在微软```.Net```平台上的```Python```解释器，可以直接把```Python代```码编译成```.Net```的字节码。

4、说说你知道的Python3 和 Python2 之间的区别？<br>
* 在Python2中默认使用asscii编码，Python3默认使用UTF-8编码。
* 对于```print```，不再是语句，而是一个函数，可以接收多个参数。
* 字符串和编码问题，在py2中字符串和字节序列区分不明显（```str```代表字节序列，```unicode```代表文本字符串），而在py3中，对两者进行了严格的区分，```str```代表字符串，```byte```代表字节序列。
* 在py2中```True```和```False```是两个全局变量，分别为1和0.而在py3中，变成了两个关键字，不允许被重新赋值。
* py3中用```!=```替换了```<>```

**5、Python3 和 Python2 中 int 和 long 区别？**<br>

在py3中不存在```long```类型，py2中的长整型被替换为普通的十进制整数。<br>

**6、xrange 和 range 的区别？**
```xrange``` 的结果是一个生成器。```range```为一个普通对象，但是在py3中，两者进行了合并。<br>

## 二、编码规范
**7、什么是 PEP8?**<br>
可参考：https://zh-google-styleguide.readthedocs.io/en/latest/google-python-styleguide/python_language_rules/#lint
相当于```Python```增强规范，是一种编码规范，更容易被阅读。<br>

**8、了解 Python 之禅么？**
在```Python``` 终端输入```import this```就可以看见。<br>
**9、了解 docstring么？**
```docstring``` 称为文档字符串，作为模块，函数，类或方法定义中的第一个语句出现。这样的docstring成为该对象的```__doc__```特殊属性。
为了保持一致性，务必要在```docstrings```周围使用三重引号。且分为单行和多行。
```
def name():
    """
    This is docstring！
    """
    return 0
``` 

**10、了解类型注解么？**
因为在设置变量是不需要对变量声明类型，所以书写的时候会比较方便，但是在阅读的时候会造成一些问题，在众多的变量中有时候回不明白函数中参数的变量类型是什么，这时候使用类型注释会增强代码的可读性。

```
def name(x:int, y:int)->int:
    return x+y
```

**11、例举你知道 Python 对象的命名规范，例如方法或者类等。**<br>
```
module_name, package_name, ClassName, method_name, ExceptionName, function_name,
GLOBAL_VAR_NAME, instance_var_name, function_parameter_name, local_var_name.
```
如上所示。各个不同的类、方法、对象、以及包都按照相应的命名方法。<br><br>

**12、Python 中的注释有几种？**<br>
单行注释方法：```# 这是单行注释```
多行注释：
```
"""
这是多行注释。
"""
```
多行注释用三个引号把要注释的内容括起来。<br>

**13、如何优雅的给一个函数加注释？**
个人觉得注释不要过多，不要讲每一行代码都干了什么，在关键的地方加上注释即可。比如比较复杂难懂的地方。如果要声明一个类或者一个函数的作用和功能，最好使用```docstring```注释。<br>

**14、如何给变量加注释？**<br>
使用#即可，但是要保证全局的风格都是一致的。<br>

**15、Python 代码缩进中是否支持 Tab 键和空格混用？**<br>
不可以混用，在不同的```IDE```中对```Tab```键的定义是不一样的，有可能是4个字符的长度，也有可能是8个字符的长度。<br>

**16、是否可以在一句 import 中导入多个库?**
可以，但是不推荐，而且尽量不使用```from * import modelname```，假如某个模块经常被使用，可以这样导入，推荐每行导入一个模块。<br>

**17、在给 Py 文件命名的时候需要注意什么?**
命名的时候不要和模块的名字相同，否则在调用包的时候会出现错误。<br>

**18、例举几个规范 Python 代码风格的工具。**
* Pylint-自动检测工具，```pip3 install pylint```可以安装。
* Black-自动优化工具，<br>
* PEP8


## 三、数据类型
**19、列举 Python 中的基本数据类型？**
* ```Number(数字)```<br>
* ```String(字符串)```<br>
* ```List(列表)```<br>
* ```Tuple(元组)```<br>
* ```Dictionary(字典)```<br>

不可变数据： ```Number(数字)``` 、 ```String(字符串) ``` 、``` Tuple(元组) ``` 
可变数据：```List(列表)```、```Dictionary(字典)```、```Set(集合)``` <br>

**20、如何区别可变数据类型和不可变数据类型？**
不可变数据类型不管有多少引用，其在内存中只占一块地方。然而可变数据类型，相同的数据在内存中的位置是不一样的。
变量都是内存中值的引用，区别在于引用的是同一块内存的值还是在一块新的内存中创建新的值。<br>

**21、将"hello world"转换为首字母大写"Hello World"？**<br>
```
st = 'hello world'
st_s = st.split(' ')
print(list(x.capitalize() for x in st_s))
```
我觉得可以这么写。

**22、如何检测字符串中只含有数字?**
可以使用```isdigit()```的内置函数。<br>

**23、将字符串"ilovechina"进行反转?**<br>
（1）、
<pre>
st = 'hello world'
print(st[::-1])
</pre>


（2）、<br>
<pre>
st = 'hello world'
def change_str(s):
    st_list = list(st)
    st_list.reverse()
    s = ''
    for i in st_list:
        s += i
    print(s)
change_str(st)
</pre>
还有其他方法，暂时没写。

**24、Python 中的字符串格式化方式你知道哪些？**
1、
<pre>
st = 'hello world'
print('%s' % st)

output：hello world
</pre>
2、
<pre>
st = 'hello world'
st_1 = 2
print('{0}{1}'.format(st, st_1))

output: hello world2
</pre>
Python3中常用```format```格式化字符串，而且```{}```的索引要从0开始。否则会报错。<br>
<br>


25、有一个字符串开头和末尾都有空格，比如“ adabdw ”,要求写一个函数把这个字符串的前后空格都去掉。  <br> 
1、
<pre>
s = ' adabdw '
print(s.strip())
output：adabdw
</pre>

2、
<pre>
s = ' adabdw '
print(s.replace(' ', ''))

output：adabdw
</pre>

**26、获取字符串”123456“最后的两个字符。**<br>
切片：
<pre>
s = '123456'
print(s[-2:])

output：56
</pre>

**27、一个编码为 GBK 的字符串 S，要将其转成 UTF-8 编码的字符串，应如何操作？**<br>
首先```encode```将字符串编码为```bytes```,```decode```将```bytes```解码成str。<br>
可以先将```GBK```解码成```Unicode```，再编码成```UTF-8```。<br>

![](https://user-gold-cdn.xitu.io/2019/8/26/16ccc8dbd188f51a?w=733&h=384&f=png&s=30952)
```s.decode('gbk').encode('utf-8')```  <br>

**28、```s="info:xiaoZhang 33 shandong"```,用正则切分字符串输出['info', 'xiaoZhang', '33', 'shandong']？**<br>

<pre>
s = "info:xiaoZhang 33 shandong"
print(re.split(r" |:", s))
print(re.split(r":| ", s))
</pre>

两种正则表达式最后输出的结果都是一样的。<br>

**27-1、怎样将字符串转换为小写？**<br>

<pre>
s = 'ABCDE'
print(s.lower())

output：abcde
</pre>

<pre>
s.upper() # 将字符串中的小写字母转换为大写
s.lower() # 将字符串中的大写字母转换为小写
str.capitalize() # 把第一个字母转化为大写字母，其余小写
str.title() # 把每个单词的第一个字母转化为大写，其余小写 
</pre>

**28-1、单引号、双引号、三引号的区别？**<br>
在作为字符串变量的时候是没有区别的。如果引号之内还包含引号，那么外层的引号建议使用双引号。三引号的话可以作为多行注释或者多行字符串。<br>

**29、```a = "你好     中国  "```,去除多余空格只留一个空格。**<br>
<pre>
a = "你好     中国  "
print(re.sub(r" +", " ", a))
</pre>

列表：
**30、已知 AList = [1,2,3,1,2],对 AList 列表元素去重，写出具体过程。**
1、
<pre>
AList = [1, 2, 3, 1, 2]
print(list(set(AList)))
</pre>

2、
<pre>
AList = [1, 2, 3, 1, 2]
blist = []
for i in AList:
    if i not in blist:
        blist.append(i)
print(blist)
</pre>

**31、如何实现 "1,2,3" 变成 ["1","2","3"]？**
1、
<pre>
a = "1,2,3"
print(a.split(','))
</pre>

2、
<pre>
a = "1,2,3"
b = []
for i in a:
    if i not in ', .':
        b.append(i)
print(b)
</pre>

**32、给定两个 list，A 和 B，找出相同元素和不同元素。**
1、
<pre>
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
</pre>

2、修改之后。
<pre>
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
</pre>

这个方法可以找出```a```列表中和```b```列表相同和不同的元素。<br>
**33、[[1,2],[3,4],[5,6]]一行代码展开该列表，得出[1,2,3,4,5,6]？**
1、
<pre>
a = [[1, 2], [3, 4], [5, 6]]
print([x for i in a for x in i])
</pre>

2、
<pre>
a = [[1, 2], [3, 4], [5, 6]]
s = []
for i in a:
    for j in i:
        s.append(j)
print(s)
</pre>

**34、合并列表[1,5,7,9]和[2,2,6,8]。**
1、
<pre>
a = [1, 5, 7, 9]
b = [2, 2, 6, 8]
a.extend(b)
print(a)
</pre>

2、
```
a = [1, 5, 7, 9]
b = [2, 2, 6, 8]
for i in b:
    a.append(i)
print(a)
```
3、
```
a = [1, 5, 7, 9]
b = [2, 2, 6, 8]
print(a+b)
```
**35、如何打乱一个列表的元素？**<br>
```
a = list(range(20))
random.shuffle(a)
print(a)
```
每次打乱的顺序都不一样。<br><br>

字典：
**36、字典操作中 del 和 pop 有什么区别？**<br>
```pop``` :可以返回被删除的值。
```
a = {'name': 'joy', 'age': 19, 'class': '2'}
print(a.pop('name'))
```
```del``` ：直接删除值，不返回。
```
a = {'name': 'joy', 'age': 19, 'class': '2'}
del a['name']
print(a)
```
两段代码的结果是一样的。<br>

**37、按照字典的内的年龄排序。** 
```
d1 = [
    {'name':'alice', 'age':38},
    {'name':'bob', 'age':18},
    {'name':'Carl', 'age':28},
]
```
可以这么写：
```
d1 = [
    {'name':'alice', 'age':38},
    {'name':'bob', 'age':18},
    {'name':'Carl', 'age':28},
]
d1.sort(key=lambda k: k['age'])
print(d1)


output： [{'name': 'bob', 'age': 18}, {'name': 'Carl', 'age': 28}, {'name': 'alice', 'age': 38}]
```
使用```lambda```函数可以解决这个问题。<br>

```
d1.sort(key=d1['age']) # 这么写会报错。
```
**38、请合并下面两个字典 a = {"A":1,"B":2},b = {"C":3,"D":4}。** <br>
1、使用```update```方法。
```
a = {"A": 1, "B": 2}
b = {"C": 3, "D": 4}
print(a.update(b))
print(a)
```
2、应该称为构造函数法。可阅读性差，而且当```key```不是字符串的时候可能会报错。
```
a = {"A": 1, "B": 2}
b = {"C": 3, "D": 4}
c = dict(a, **b)
print(c)
```
随后可以用生成式的方法合并两个字典，或者使用传统的方法。<br><br>

**39、如何使用生成式的方式生成一个字典，写一段功能代码。**
```
b = {k: v for (k, v) in iterable}
```
其中```iterable```为可迭代对象，包括元组，字典。称为字典生成式。<br><br>

**40、如何把元组("a","b")和元组(1,2)，变为字典{"a":1,"b":2}**<br>
1、```zip```函数。
```
a = ("a", "b")
b = (1,2)
c = dict(zip(a, b))
print(c)
```
2、匿名函数。
```
a = ("a", "b")
b = (1,2)
c = dict(map(lambda x, y:[x, y], a, b))
print(c)
```
****
41、Python 常用的数据结构的类型及其特性？
```
A：{1:0,2:0,3:0}
B：{"a":0, "b":0, "c":0}
C: {(1,2):0, (2,3):0}
D: {[1,2]:0, [2,3]:0}
```
列表不可以作为字典的键名。<br>
参考链接：https://blog.csdn.net/u014453898/article/details/56486519 <br>

42、如何将元组("A","B")和元组(1,2),合并成字典{"A":1,"B":2}？<br>
参考40.<br>

43、Python 里面如何实现 tuple 和 list 的转换？<br>

```
a = [1, 2, 3, 4]
b = tuple(a)
print(type(b))
# 列表转元组
c = (3, 4, 5, 6)
d = list(c)
print(type(d))
# 元组转列表
```
44、我们知道对于列表可以使用切片操作进行部分元素的选择，那么如何对生成器类型的对象实现相同的功能呢？<br>
首先应该将其实例化。
```
a = [x for x in range(10)]
print(a)
```
这样```a```就是一个列表，同样可以进行切片操作。<br>

45、请将[i for i in range(3)]改成生成器？<br>
将```[]```改成```()```。
```
a = (i for i in range(3))
print(a)

output：<generator object <genexpr> at 0x00000125DC9BFCF0>
```
生成器类型。<br>
46、a="hello"和 b="你好"编码成 bytes 类型。<br>
```
a = "hello"
b = "你好"
print(type(a.encode()))
print(type(b.encode()))
```
47、下面的代码输出结果是什么？
```
a = (1,2,3,[4,5,6,7],8)
a[2] = 2
```
上面的代码会报错，因为元组是一个不可变类型。其中的数据不可被修改，(可以索引，但是不能修改)<br>

48、下面的代码输出的结果是什么?<br>
```
a = (1,2,3,[4,5,6,7],8)
a[5] = 2
```
这里元组```a```的第3个索引是一个列表，所以使用```a[3][1]```可以索引出列表中的5，而这个列表中的数据是可以修改的。<br>
## 四、操作类题目
49、Python 交换两个变量的值。<br>
1、交换两个变量的值。
```
a = 1
b = 2
c = a
a = b
b = c
print(a)
print(b)
```
2、
```
a = 1
b = 2
a = a + b
b = a - b
a = a - b
print(a)
print(b)
```
50、在读文件操作的时候会使用 read、readline 或者 readlines，简述它们各自的特点。<br>
1、```read()```方法：<br>
特点：读取整个文件，会将读取的内容放在一个字符串当中。<br>
劣势：当文件特别大的时候比较占内存，在大于内存的时候会无法使用这个函数。<br>
2、```readline()```方法：<br>
特点：readline()方法每次读取一行；返回的是一个字符串对象，保持当前行的内存.<br>
缺点：比readlines慢得多。<br>
3、```readlines()```方法：<br>
特点：一次性读取整个文件；自动将文件内容分析成一个行的列表。readlines()读取所有行然后把它们作为一个字符串列表返回。<br><br>

51、json 序列化时，可以处理的数据类型有哪些？如何定制支持 datetime 类型？<br>
```JSON``` 序列化：将```Python```内置的数据类型序列化为```json```格式，用来做数据存储或者数据交换。<br>
基本内置的数据类型都可以，```dict```,```str```,```list```等。<br>
对于要支持```datetime```格式的话需要自定义一个类。
```
class CJsonEncoder(json.JSONEncoder):

    def default(self, obj):
        if isinstance(obj, datetime):
            return obj.strftime('%Y-%m-%d %H:%M:%S')
        elif isinstance(obj, date):
            return obj.strftime('%Y-%m-%d')
        else:
            return json.JSONEncoder.default(self, obj)
```
如果不想定义类，直接在我们获取的date或者datetime对象后面用上```strftime```方法进行格式化也可以。<br>
参考：https://cloud.tencent.com/developer/article/1098709 <br><br>
52、json 序列化时，默认遇到中文会转换成 unicode，如果想要保留中文怎么办？<br>
<pre>
def xml_to_json(file_path):
    str_xml = open(file_path, encoding='utf-8')
    all_xml_str = str_xml.read()
    con_json = xmltodict.parse(all_xml_str, encoding='utf-8')
    str_json = json.loads(json.dumps(con_json, ensure_ascii=False))
    return str_json
</pre>

这个个函数可以将```xml```格式的文件转换成```json```。<br>
其中，```dump```和```dumps```都是实现了序列化。```load```和```loads```都实现了反序列化。中文会转成```unicode```，在序列化的函数内加上一个参数```ensure_ascii=False```就可以保留中文。<br>
参考：https://www.cnblogs.com/bigtreei/p/10466518.html<br><br>

53、有两个磁盘文件 A 和 B，各存放一行字母，要求把这两个文件中的信息合并(按字母顺序排列)，输出到一个新文件 C 中。<br>
先读取文件，存入变。将两个字符串相加，然后对 C 字符串进行排序。<br>
<pre>
s = 'cdabvf'
s_list = list(s)
s_list.sort()
print(s_list)
print(''.join(s_list))
</pre>
可以先将字符串转为列表，但是当字符串数量很大的时候，转成列表之后会消耗很多的系统资源。<br>
还可以使用匿名函数的解法。<br>

54、如果当前的日期为 20190530，要求写一个函数输出 N 天后的日期，(比如 N 为 2，则输出 20190601)。<br>
<pre>
def get_day(n):
    now_time = datetime.datetime.now()
    d = now_time + datetime.timedelta(n)
    print("{0}天后的日期是:{1}".format(n, str(d)[:11]))

get_day(100)
</pre>
这样的输出格式为```2019-08-08```，而且是利用了类型转化加切片。
```
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
稍作修改之后就可以了。<br>

55、写一个函数，接收整数参数 n，返回一个函数，函数的功能是把函数的参数和 n 相乘并把结果返回。<br>
类似于一个闭包函数，闭包的讲解参考：<br>
https://foofish.net/python-closure.html<br>
https://www.cnblogs.com/Lin-Yi/p/7305364.html<br>
<pre>
def f1(n):
    def f2(*args):
        s = 10
        return s * n
    return f2
print(f1(2)())
</pre>

返回内层函数，然后调用内层函数。<br><br>

56、下面代码会存在什么问题，如何改进？<br>
<pre>
def strappend(num):
    str='first'
    for i in range(num):
        str+=str(i)
    return str
</pre>

1、对于变量的命名不应该使用保留字```str```，在 IDE 中会出现如下提示：会出现不能调用的情况。

![](https://user-gold-cdn.xitu.io/2019/8/28/16cd6e39c99cb7f6?w=812&h=193&f=png&s=27593)

2、其实对于```num```有可能为其他类型，或者说为负数，都会造成代码运行失败。返回值也是```str```，还是和保留的关键字重名了。<br><br>

57、一行代码输出 1-100 之间的所有偶数。<br>
1、使用列表生成式可以实现：
```
print([i for i in range(0, 100, 2)])
```
2、直接使用```range```也可以实现。
```
print(list(range(0, 101, 2)))
```
58、with 语句的作用，写一段代码？<br>
with 在 py 3.5 的时候加入到 Python 中，用来代替```try...except...finally```。
with 常用在对于文件的操作中，
```
with open("filename") as f:
    # do something
    f.readline()
    f.close()
```
59、python 字典和 json 字符串相互转化方法。<br>
在 51 题关于```json```序列化的问题中，参考 51。<br>

60、请写一个 Python 逻辑，计算一个文件中的大写字母数量。<br>
参考：https://www.cnblogs.com/stono/p/9102043.html<br>
```file_path``` 为文件路径，暂时不完善。
```
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
## 五、高级特效
70、函数装饰器有什么作用？请列举说明？<br>
在原有功能不改变，或者不修改任何代码的情况下，给原有的功能添加新的功能。它经常用于有切面需求的场景，比如：插入日志、性能测试、事务处理、缓存、权限校验等场景，装饰器是解决这类问题的绝佳设计。概括的讲，装饰器的作用就是为已经存在的对象添加额外的功能。<br>
参考：https://foofish.net/python-decorator.html<br>

71、Python 垃圾回收机制？<br>
参考：https://testerhome.com/topics/16556 <br>
https://www.cnblogs.com/Xjng/p/5128269.html <br>

72、魔法函数 __call__怎么使用?<br>
```__call__``` 的作用就是让一个类也可以像一个函数一样可以拿来调用。<br>
参考：http://www.langzi.fun/Python%E9%AD%94%E6%B3%95%E5%87%BD%E6%95%B0.html <br>

73、如何判断一个对象是函数还是方法？<br>
一般情况下，函数和方法似乎分界不明确。一般来讲，与类实例绑定的函数称为方法，与类实例不绑定的函数就称为函数。可参考：https://www.cnblogs.com/blackmatrix/p/6847313.html <br>

74、@classmethod 和@staticmethod 用法和区别？<br>
分别为类方法和静态方法：<br>
```@staticmethod``` 不需要表示自身对象的self和自身类的cls参数，就跟使用函数一样。
```@classmethod``` 也不需要 self 参数，但第一个参数需要是表示自身类的cls参数。<br>
参考：https://blog.csdn.net/handsomekang/article/details/9615239 <br>

75、Python 中的接口如何实现？<br>
接口只是定义了一些方法，而没有去实现，多用于程序设计时。只是设计需要什么样的功能，但是并没有实现任何功能，有些功能需要被另外的 B 类继承之后，由 B 类重写方法来实现相应的功能。<br>
遵循：开放封闭原则，依赖导致原则，接口隔离原则，继承多态。<br>
参考：https://blog.csdn.net/weixin_42181824/article/details/81874725 <br><br>

76、Python 中的反射了解么? <br>
其实，反射就是通过字符串的形式，导入模块；通过字符串的形式，去模块寻找指定函数，并执行。利用字符串的形式去对象（模块）中操作（查找/获取/删除/添加）成员，一种基于字符串的事件驱动！<br>
参考：https://www.cnblogs.com/vipchenwei/p/6991209.html <br>

77、metaclass 作用？以及应用场景？<br>
