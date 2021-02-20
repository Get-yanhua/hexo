---
title: git命令
date: 2021-02-03 01:26:39
urlname: git
categories: 
    - GitHub
tags: 
    - Github
---

### 使用Git命令将本地代码提交到github代码仓库

```bash
git init
//初始化一个空的git仓库
git add .
//将文件夹中所有的文件都提交到暂存区中
git commit -m ‘添加一个描述’
//将暂存区的所有文件推到版本库

如果你在这里出现了错误，可能是需要添加配置信息，告诉git你是谁
git config --global user.name //你的账户名 

git config --global user.email  //你的邮箱
```

#### **commit命令**

```bash
配置结束后再执行commit命令
远程仓库的提交（第一次连接）
git remote add origin +仓库地址
git push -u origin master （空仓库加 -u）
//仓库关联

如果无法上传则可以使用强制上传命令
代码是 git push -f origin master
强制上传会清空整个仓库
```

#### **分支建立与切换**

```bash
git branch main
//建立一个名为main的分支
git checkout main
//切换到main分支
git branch -D mian
//命令则可以来强制删除我们这个分支
git branch
//命令来查看我们分支情况
```

### hexo生成静态网页

```bash
hexo cl&&hexo g
```

