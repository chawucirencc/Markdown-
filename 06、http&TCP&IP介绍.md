### 1、HTTP

HTTP 协议（无状态协议），超文本传输协议，应用层协议。

### 2、TCP/IP ###



### 3、Cookie&Session ###

参考：https://www.cnblogs.com/zhouhbing/p/4204132.html

Cookie通过在客户端记录信息确定用户信息，Session通过在服务端记录信息确定用户身份。Cookie弥补了HTTP无状态协议的不足，从服务器给每个客户端发送一个“通行证”用来确定用户的身份。

客户端向服务器发送请求，如果服务器需要记录当前用户的状态，那就需要给这个客户端发送一个Cookie，客户端则会把Cookie保存起来，当再次请求此服务器的时候，客户端会将Cookie一同发送给服务器，让服务器来判断用户的状态（服务器可以根据情况来修改Cookie）。

**Cookie不可以跨域名。** 

Cookie的周期（单位为秒）：1、maxage为正数，则在maxage的时间内Cookie一直有效，关闭网页重新打开依旧有效。2、maxage为负数，则说明当前的Cookie为临时的，不会被持久化，不会被保存起来。关闭浏览器之后此Cookie就消失了。

如果maxAge为0，则表示删除该Cookie。

**Session：**

Session通常是在服务端来记录用户的一种机制。相对Cookie比较简单，但是也相应增加了服务器的压力。**Session对象是在客户端第一次请求服务器的时候创建的**。一般用户的Session存储在服务端的内存中，为了防止内存溢出，长时间没有响应用户的Session会被删除。

