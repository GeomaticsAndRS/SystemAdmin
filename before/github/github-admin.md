# 管理员管理
---
## 创建一个新分支，并切换到该分支
git checkout 功能包含了创建一个分支，切换到一个分支，这两个功能是可以分开的
```bash
$ git checkout -b newDev
```

## 创建一个分支
git branch能够创建一个新的分支方便用户使用。git branch不接参数默认显示所有分支，当前分支会使用`*`号标记出来.
```bash
$ git branch newDev 创建分支
$ git branch -d newDev 删除分支
```

## 切换到一个分支
git checkout 可以切换到一个分支
```bash
$ git checkout newDev
```

## 合并分支
git merge合并分支.
```bash
$ git merge newDev 快速合并
git merge --no-ff -m "merge with no-ff" dev  禁用快速合并，保留合并记录
```

## 保存当前分支快照
 git stash 能保存当前分支一个快照，在处理其他紧急情况时非常方便。
  ```bash
  $ git stash 保存当前工作区状态并隐藏
  $ git stash list 显示隐藏的工作区列表
  $ git stash apply 恢复隐藏工作区，保留原隐藏内容
  $ git stash pop 恢复隐藏工作区，删除原隐藏内容
   ```
