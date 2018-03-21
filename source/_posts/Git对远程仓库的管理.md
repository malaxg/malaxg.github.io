---
title: Git对远程仓库的管理（CRUD）
date: 2018-03-21 13:16:49
categories: Git
tags:
- "GitHub仓库"
---
1、查看当前git仓库所连接的远程github仓库地址

```
git remote -v
```
2、关联github仓库

```
git remote add [short-name] git@github.com:malaxg/malaxg.github.io.git
```
3、重命名远程仓库

```
git remote rename <old-remote-name> <new-remote-name>
```
4、修改远程仓库

```
git remote set-url --push [remote-name] [newUrl]
```
5、删除远程仓库

```
git remote rm [remote-name]
```
