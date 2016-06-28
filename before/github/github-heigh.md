# 本地仓库管理
---
注意：一下的命令都是在管理本地的代码库，这些修改和提交都是在本地操作，并没有操作远程的github代码库。

## git config
配置Git的时候，加上`--global`是针对当前用户起作用的，如果不加，那只针对当前的仓库起作用。
```bash
$ git config --global color.ui true  让git适当显示颜色
$ git config --global alias.st status  配置别名
```

## git status 
该命令可以让我们时刻掌握仓库当前的状态,比如哪些文件被修改了。
```bash
$ git status
```

## git diff 
查看github.md文件做了那些修改.
```bash
$ git diff github.md
```

## git add
向本地仓库中添加修改过的文件。这里只是标记哪些文件需要被提交，并不是真实提交到本地仓库，真实提交是git commit命令。
```bash
$ git add newfile.md    
或者    
$ git add ./*   
```

## git commit
将git add指定的文件提交的本地仓库中。
```bash
$ git commit -m "提示文本"
```

## git log
查看向远程github代码的递交记录，可以通过在提交时【git commit -m “提示文本”】中指定的提示文本来快速查看和定位历史版本，因此建议在git commit时一定要指定有意义的提示文本内容。
```bash
$ git log  详细的输出   
或者   
$ git log --pretty=oneline 简介的输出   
git log --graph --pretty=oneline --abbrev-commit 查看分支
```
## git reset
在各个提交的历史版本中跳转,可以通过git log查看提交时产生的commit id或者通过git reflog查看历史操作命令中的涉及的commit id。
```bash
$ git reset ea78643df
```

## git reflog
查看历史对版本库的操作记录,操作是指对github远程代码库的操作
```bash
$ git reflog
```

## git checkout
撤销最近一次commit的修改.`git checkout -- file`命令中的`--`很重要，没有`--`，就变成了“切换到另一个分支”的命令，我们在后面的分支管理中会再次遇到`git checkout`命令。`git checkout`其实是用版本库里的版本替换工作区的版本，无论工作区是修改还是删除，都可以“一键还原”。
```bash
$ git checkout -- github.md
```

## git rm
删除文件。只能删除本地版本库中的文件，使用git pull递交远程库时才会删除远程库中的文件。
```bash
$ git rm old.md
$ git commit -m "rm a file"
$ git push -u origin master
```


## git clone
将远程的仓库克隆到本地
```bash
$ git clone https://github.com/vinnyzhaowenyu/SystemAdmin.git
```

## git remote
将本地仓库关联到远程仓库，只需要关联一次即可。
```bash
$ git remote add origin  https://github.com/vinnyzhaowenyu/SystemAdmin.git
$ git remote 查看远程仓库信息，默认是origin，-v详细
```


# 远程管理
---
## git push
将本地仓库推送到远程Github仓库
```
$ git push -u origin master默认分支   
或者   
$ git push -u origin dev自己的分支   
```





