## Git ##

进入目标文件夹右键选择Git Bash Here:

参考： https://www.cnblogs.com/sdcs/p/8270029.html 

```python
git init # 初始化文件夹，会创建一个.git的隐藏文件夹
git status # 查看当前的状态，可多次使用
git add . # 选择添加所有的文件到GitHub
git commit -m 'commit' # 提交命令，包含提交备注
# 然后需要将GitHub上面的项目地址复制下来，首先需要创建一个新的项目。具体不再陈述！创建好之后，执行下面的命令。
git remote add origin repositories_address(https://github.com/chawucirencc/Predicting-whether-a-telecommunications-company-is-losing-customers.git) # 将本地文件夹添加到新的项目当中。
git push -u origin master # 将本地文件夹同步推送到GitHub的项目当中。
# 在这里可能会出现一些报错，如果在GitHub创建新的项目的时候勾选了Readme init，那么会报一个如下图的错误。原因是英文本地文件夹内的文件和项目地址里的文件不对等，本地文件夹没有Readme.md文件。这时候要先使用下面的命令。
git pull --rebase origin master # 同步本地和项目地址。
git push -u origin master 

```

 ![img](https://images2017.cnblogs.com/blog/1271277/201801/1271277-20180111184048207-303862747.png) 

需要使用到GitHub的账号和密码。当果然如果初始化成功之后而且成功上传到GitHub，在vscode中会出现项目管理的文件夹，每次改动的话都会有提醒，而且还有对比和参照。也可以使用vscode同步更新GitHub上面的代码。

