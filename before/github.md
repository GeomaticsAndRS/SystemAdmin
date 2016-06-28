# Github基础
---
![git-tutorial](http://www.liaoxuefeng.com/files/attachments/0013848605496402772ffdb6ab448deb7eef7baa124171b000/0)

## 概念
- Git是分布式版本控制系统。   
- Linus在1991年创建了开源的Linux，到2002年提交的Linux代码量已经非常庞大，而且BitMover公司收回了BitMover的免费使用权，因此Linus花了两周时间自己用C写了一个分布式版本控制系统，这就是Git！
- 相比SVN这种集中式版本控制系统，Git这种分布式版本控制系统具有极大的优势。使用Git的用户可以不需要连接网络也可以工作使用；由于分布式的特性，其安全性极高；而且还有很强大的分支管理功能、快速、简单等特性。
- Git详细教程：http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000

## 安装Git
#### Linux平台
```bash
yum install git -y
sudo apt-get install git -y
```
#### Windows平台
Windows平台安装需要基础shell环境，常用的是cygwin，目前有集成环境。下载Windows平台安装包，根据提示完成安装。
> 下载地址： https://git-for-windows.github.io/

### Mac平台
- 从AppStore安装Xcode，Xcode集成了Git，不过默认没有安装，你需要运行Xcode，选择菜单“Xcode”->“Preferences”，在弹出窗口中找到“Downloads”，选择“Command Line Tools”，点“Install”就可以完成安装了。

## 配置
**1.注册Github账号**
> 官网地址：https://github.com/   

**2.配置本地用户信息**
因为Git是分布式版本控制系统，所以，每个机器都必须自报家门：你的名字和Email地址。
```bash
$ git config --global user.name "Github注册的用户名"
$ git config --global user.email "Github注册的邮箱"
```
- 注意`git config`命令的`--global`参数，用了这个参数，表示你这台机器上所有的Git仓库都会使用这个配置，当然也可以对某个仓库指定不同的用户名和Email地址。

**3.SSH免密码登陆**
如果不上传公钥实现免密码登陆，每次提交代码时都要输入密码很麻烦。在shell中生成ssh公钥然后上传到Github。
> Github SSH秘钥管理：https://github.com/settings/keys

## 基本流程
**1.选择一个合适的地方，创建一个空目录。**
创建的只是一个普通的目录，如果作为git管理厂库需要第二步操作。
```bash
$ mkdir learngit
$ cd learngit
$ pwd
/Users/michael/learngit
```
**2.通过`git init`命令把这个目录变成Git可以管理的仓库。**
git init将当前这个目录变成git管理的仓库，在当前目录中会有一个隐藏的.git目录，git就是通过这个隐藏目录来管理当前项目的。
```bash
$ git init
Initialized empty Git repository in /Users/michael/learngit/.git/
```
**3.编写项目并上传到Github**
```bash
$ vim monitor.sh
$ git add monitor.sh
$ git commit -m "add a new file"
$ git remote add origin https://github.com/组织名称/项目名称.git
$ git push -u origin master
```

