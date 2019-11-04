## 一、基础
### 1、关于 HTML
（1）、HTML 超文本标记类语言，结构如下：
```html
HTML
<!DOCTYPE html>
<html lang="cn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
```
可以查看教程链接：https://www.w3school.com.cn/html/index.asp
主要是 HTML 中的标签属性值和各类属性的用法。

（2）、关于 XTML（可扩展超文本标记类语言），是更为纯净的 HTML 版本。
### 2、关于CSS
CSS 指层叠样式表，控制网页的样式。文件后缀名为 .css 。格式如下：
```css
body{
    background-color: blanchedalmond;
}
div{
    width: 200px;
    height: 200px;
    background-color: blueviolet;
    text-align: center;
}
```
在上面的 css 代码里面，不仅可以对一个 body 进行样式设置，还可以设置并列设置多个（称为选择器的分组），比如：
```css
body, h1, h2, h3{
    background-color: blanchedalmond;
}
```
这样，这4个节点就全部应用了括号里面的样式设置。

----
关于样式的继承：若对 body 进行样式设置，此样式会应用在 body 节点内部的所有文本内容上，假如在 body 内部的某些文本有自己的样式格式，则 body 的样式不会应用到此文本上面。

----
派生选择器：
```HTML
<body>
    <p><strong>Hello</strong></p>
    <ul>
        <li><strong>This is stro</strong></strong></li>
    </ul>
</body>
```
对于上面的代码，需要对```<li>``` 标签里的内容进行样式设置的话，需要使用派生选择器。在 css 文件中可以这样写：
```css
li strong{
    color: red
}
```
上面的代码就是派生选择器的用法。
还有 id 选择器（\#）、类选择器（.）、属性选择器（在 style 中设置属性名，在属性名中设置样式格式）如下：

```html
<!DOCTYPE html>
<html lang="cn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Document</title>
    <style type='text/css'>
        [title]{
            color: red
        }
        [title='t']{
            color: blue
        }
    </style>
</head>
<body>
    <p title="">This is a test P</P></p>
    <p title="t">This is a test P2</p>
    <p><strong>Hello</strong></p>
    <ul>
        <li><strong>This is stro</strong></strong></li>
    </ul>
</body>
</html>
```
上面为属性选择器的结构，对于属性 title 如果没有指定值，则在标签中无论使用什么值都可以，如果 title 有指定的值，需要在标签中让属性等于相应的值才可以应用到样式设置。
