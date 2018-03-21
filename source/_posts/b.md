---
title: Git分支管理
date: 2018-03-21 17:33:04
categories: Git
tags:
- "Git"
---
## Git鼓励大量使用分支：
1. 查看分支：git branch

1. 创建分支：git branch <name>
1. 切换分支：git checkout <name>
1. 创建+切换分支：git checkout -b <name>
1. 合并某分支到当前分支：git merge <name>
1. 删除分支：git branch -d <name>
## 多人协作
默认clone是克隆master分支
想在本地创建其他分支则用

```
git checkout -b beanch-name 主机名(origin)/branch-name
```
多人协作的工作模式通常是这样：

1. 首先，可以试图用git push origin branch-name推送自己的修改；

1. 如果推送失败，则因为远程分支比你的本地更新，需要先用git pull试图合并；

1. 如果合并有冲突，则解决冲突，并在本地提交；

1. 没有冲突或者解决掉冲突后，再用git push origin branch-name推送就能成功！

1. 如果git pull提示“no tracking information”，则说明本地分支和远程分支的链接关系没有创建，用命令
1. git branch --set-upstream branch-name origin/branch-name。

这就是多人协作的工作模式，一旦熟悉了，就非常简单。

## 小结
1. 查看远程库信息，使用git remote -v；

1. 本地新建的分支如果不推送到远程，对其他人就是不可见的；

1. 从本地推送分支，使用git push origin branch-name，如果推送失败，先用git pull抓取远程的新提交；

1. 在本地创建和远程分支对应的分支，使用git checkout -b branch-name origin/branch-name，本地和远程分支的名称最好一致；

1. 建立本地分支和远程分支的关联，使用git branch --set-upstream branch-name origin/branch-name；

1. 从远程抓取分支，使用git pull，如果有冲突，要先处理冲突。