### Linux

类 Unix 系统，基于 POSIX 和 UNIX 的多用户、多任务、支持多线程和多 CPU 的操作系统。基于 Linux 内核发行了很多版本。关于 Linux 和 Windows ：

|          | Windows | Linux |
| :------: | :-----: | :---: |
|   界面   |         |       |
| 驱动程序 |         |       |
|   使用   |         |       |
|   学习   |         |       |
|   软件   |         |       |

启动过程：1、内核的引导。2、运行```init``` 。3、系统初始化。4、建立终端。5、用户登录系统。

登录方式一般有 3 种：1、命令行登录。2、```ssh``` 登录。3、图形界面登录。

图形界面和文字界面的切换方式，默认登录的是第一个窗口，6 个窗口分别为 tty1...tty6。可以按下Ctrl+Alt+F1~F6切换到命令窗口。VMware中窗口的切换为Alt+Space+F1~F6。在登录文字命令窗口的时候，使用的用户名应该是管理员的名称，也就是在图形界面终端可以看到@符号前面的那个，并不是登录名称。

关机指令为：shutdown。可以 man shutdown 查看帮助文档。

sync 将数据由内存同步到硬盘中。

shutdown -h 10 ‘This server will shutdown after 10 mins’：计算机将在10分钟之后关机，并且会显示在用户的屏幕中。

shutdown -h now：立刻关机。

shutdown -h 20:00：会在20:00的时候关机。

shutdown -h +10：10分钟之后关机。

shutdown -r now：立刻重启。

shutdown -r +10:10分钟之后重启。

reboot：相当于shutdown -r now。

关于绝对路径和相对路径。绝对路径从根目录开始写起。

**常用的目录处理命令：参考：https://www.runoob.com/linux/linux-file-content-manage.html** 

*   ls：列出目录。

*   cd：切换目录。

*   ```pwd```：显示当前目录。

*   ```mkdir```：创建一个新的目录。

*   ```rmdir```：删除一个空目录。

*   ###### `cp`：复制文件或目录。 ######

*   `rm`：移除文件或目录。

*   `mv`：移动文件或目录，或者修改文件与目录的名称。

    可以使用 `man name` 来查看使用文档，如` man cp` 。

参数：

*   -a：全部的文件，包括隐藏文件。
*   -d：仅仅列出目录。
*   -l：列出长数据串，包括文件的属性和权限等数据。

**用户与用户组管理**

参考：https://www.runoob.com/linux/linux-user-manage.html



### Shell

Shell 既是一种命令语言，又是一种程序设计语言。Shell 是指一种应用程序，这个程序提供了一个界面，用户通过访问这个界面操作系统的内核服务。

shell script 是一种为shell编写的脚本程序。`bsah`是一种应用程序。两者实现了相同的功能。

shell变量：

**字符串：**

```shell
name1="bob"
name2="Jhon" # 字符串变量
echo $name2
echo ${name2}
echo ${#name2} # 获取字符串长度
echo ${name2:1:3} # 提取子字符串，类似于切片
```

单引号字符串里的所有字符都会照原样输出，而且单引号中的字符串是无效的。

双引号里可以有变量，也可以出现转义符。

花括号是为了帮助解释器识别变量的边界。

**数组：**

```shell
array_value=(value1 value2 value3)
${array_value[index]} # 读取数组的元素
echo ${array_value[@]} # 使用@可以获得数组的所有元素、
echo ${#array_value[@]} # 获取数组的长度，可以获得单个元素的长度。
echo ${#array_value[index]} # 获取单个元素的长度
$*和$@的区别：
$*把参数作为一个参数，$@把参数作为多个参数。
```

运算符：+、-、*、/、%、==、=(赋值)、!=。逻辑运算符：&&（AND）、||（OR）。

```shell
-z # 检测字符串长度是否为0，为0返回 true。[-z$a]
-n # 检测字符串长度是否为0，不为0返回 true。[-n$a]
str # 检测字符串是否为空，不为空返回 true。[$a]
```

流程控制：

```shell
if conditoin
then 
	command1
	command2
	command3
fi
# ----------------------------------------------
num1=$[2*3]
num2=$[1+5]
if test $[num1] -eq $[num2]
then
    echo '两个数字相等!'
else
    echo '两个数字不相等!'
fi	# 与test结合使用。
```

```shell
for var in item1 item2 ... itemN
do
	command1
	command2
	command3
done
# -----------------------------------------------
for loop in 1 2 3 4 5
do
    echo "The value is: $loop"
done
# -----------------------------------------------
while condition
do
	command
done
```

还有一种选择结构`case in`:

```shell
case value in
	1) echo "This is $value"
	;;
	2) echo "This is $value"
	;;
	3) echo "This is $value"
	;;
esac
```

shell 函数：

```shell
[ function ] funname[()]

{
	action;
	[return int;]
}
# ----------------------------
funtionname(){
	action
	return 0
}
```

### 常用命令 ###

```python
cd, ls, mkdir, touch, mv, cp, pwd, tree, rm, rm -rf, ps, ps -aux, kill, kill -9, ifconfig, cat, vi, less, more, find, find filename -type d, df -h, netstat -tln, netstat
cd /.
cd ..
# 有些命令包含一些参数。
```

参考： https://blog.csdn.net/ljianhui/article/details/11100625 

