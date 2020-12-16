#                                      git

## 介绍

Git 是一个开源的分布式版本控制系统，用于敏捷高效地处理任何或小或大的项目。

Git 是 Linus Torvalds 为了帮助管理 Linux 内核开发而开发的一个开放源码的版本控制软件

### 版本控制系统

代码管理工具：所谓版本控制系统，就是管理项目的源代码的各个的版本。

## 解决的问题

代码备份

问责

安全

找回历史版本

协同开发（代码合并)

## 常见版本控制系统

Git:	最牛，没有之一,因为他是一个分布式版本控制系统
Subversion(SVN):	很牛，但是它是一个集中式版本控制系统

### 分布式版本控制系统：





### 集中式版本控制系统:





## 下载与安装

 https://git-scm.com/downloads 



## 常用操作

```
初始化版本库
git init

设置用户
git config --global user.name "sun"
git config --global user.email "123@qq.com"

查看配置
git config --list

添加到暂存区
git add a.txt
git add .

添加到版本库
git commit -m "日志"

查看历史版本
git log				--当前版本以及当前版本以上的版本
git reflog          --所有的历史变更

回退版本
git reset --hard Head
git reset --hard abcd123  (指定版本号)
git reset --hard Head{2}  (指定版本--可以回退到任意版本)

撤销尚未add的内容
git checkout .

撤销add过的尚未commit内容回到未add状态
git reset Head .

撤销commit过的内容
没门儿

删除文件
git rm file				删除文件
git rm -r dir			删除目录
```

```
移动文件
git mv a.txt ./a/						将a.txt移动到a目录里面去

忽略文件
要在工作目录的根目录下，创建一个.gitignore文件,在里面编写你要忽略的文件或者是文件夹
		target          //忽略这个target目录
		angular.json    //忽略这个angular.json文件
		log/*           //忽略log下的所有文件
		css/*.css       //忽略css目录下的.css文件
```



## 远程仓库

通常情况下，我们希望回家了还能接着写代码，那么就需要将我们的项目备份到网络上，类似于百度云盘。比U

盘还好使。此时，我们就需要使用到远程仓库了(远程仓库通常是指云仓库)

常用的仓库，主要有两个，一个是国外的github，一个是国内的gitee.对于咱们来说，从速度上来讲，国内的占有巨大的优势，但是从项目托管数量上来讲，github占有绝对的优势。

```
关联远程仓库
git remote add origin https://github.com/mmsqc/ku8.git
git@gitee.com:mm_sqc/zuoye.git

创建远程仓库
new ->

推送内容到远程仓库
git push origin master
如若不行，先更新，再提交

从远程仓库拉取内容
git pull origin master

删除仓库
设置--》倒数第四个删除

从github上下载别人的项目
git clone https://github.com/jquery.git（github，码云)
```



## 分支操作



### 什么是分支

分支本质上是某个项目的一个备份，我们可以在这个备份的基础上进行二次开发，就称为项目的第二分支，我们的分支和项目的主干可以同时开发，互不干扰，最后又可以互相合并，达到提高项目进度的目的。而且方便与项目的管理。

### 分支操作

```
创建分支
git branch dev					创建dev分支

切换分支
git checkout dev

查看分支
git branch

合并分支
git merge dev 					把dev分支合并当前分支

删除分支
git branch -d dev				删除dev分支

代码冲突
解决代码冲突
```

## 配置公钥

### 生成公钥

要想生成公钥，需要使用ssh命令，我们就需要将git里面的usr/bin这个目录配置到环境变量当中。

将你要添加的目录路径添加到系统变量的path变量的值的最后，并与前面的值用;隔开。

生成公钥的命令

```
ssh-keygen -t rsa -C "xxxxx@xxxxx.com"  
```



在gitee上添加公钥，一定要添加个人公钥才有提交权限



在本地关联私钥，要将私钥放到当前用户的目录下面。

执行命令进行校验

```
ssh -T git@gitee.com
```

