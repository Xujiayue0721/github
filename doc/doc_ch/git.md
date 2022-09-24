- [1. git branch](#1-git-branch)
- [2. git push](#2-git-push)
- [3. git remote](#3-git-remote)
- [4. git checkout](#4-git-checkout)
- [通用例子](#通用例子)

## 1. git branch

```python
$ git branch # 查看本地分支名称

$ git branch -r # 查看所有远程分支的名称

$ git branch -a # 查看所有的本地和远程分支
```

> git branch -vv 或 git branch -vva 看到详细的信息，如正在使用的本地或远程分支、提交 ID 和提交信息等.

```python
$ git branch xxx # 创建分支xxx

$ git branch -d xxx # 删除本地分支xxx
```

## 2. git push

```python
$ git push <远程主机名> <本地分支名>:<远程分支名>
# 本地分支是指将要被推送到远端的分支，而远程分支是指推送的目标分支

$ git push origin master
# 省略远程分支名，则表示将本地分支推送与之存在”追踪关系”的远程分支(通常两者同名)
# 如果该远程分支不存在，则会被新建

$ git push origin :master
# 省略本地分支名，则表示删除指定的远程分支
# 等同于
$ git push origin --delete master
# 表示删除origin主机的master分支

$ git push --all origin
# 将本地的所有分支都推送到远程主机
```

## 3. git remote

```python
$ git remote  -v
origin  git@xxxx/jingwei.git (fetch)
origin  git@xxxx/jingwei.git (push)
# 本地分支是指将要被推送到远端的分支，而远程分支是指推送的目标分支
```

## 4. git checkout

```python
$ git checkout xxx
# 切换到分支xxx
```

## 通用例子

```python
$git clone <远程Arepository> #克隆你fork出来的分支
 
$git remote add <远程Brepository标签> git@github.com:XXXX/ceph.git #添加远程Brepository标签
 
$git pull <远程B厂库标签> master:master  #从远程Brepository的master分支拉取最新objects合并到本地master分支
 
$git checkout YYYY #切换到要修改的分支上
 
$git branch develop; git checkout develop #在当前分支的基础上创建一个开发分支，并切换到该分支上，你将在该分支上coding
 
coding...... #在工作区coding
 
$git add .#将修改保存到索引区
 
$git commit -a #将修改提交到本地分区
 
$git push origin my_test:my_test #将本地分支my_test提交到远程A repository的my_test分支上
```