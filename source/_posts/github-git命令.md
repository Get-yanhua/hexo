---
title: github git命令
date: 2021-02-03 01:26:39
urlname: github_git
categories: 
    - Github
tags: 
    - Github
---

## 使用Git命令将本地代码提交到github代码仓库

```bash
git init
//初始化一个空的git仓库
git add .
//将文件夹中所有的文件都提交到暂存区中
git commit -m ‘添加一个描述’
//将暂存区的所有文件推到版本库
```

##### 如果你在这里出现了错误，可能是需要添加配置信息，告诉git你是谁

```bash
git config --global user.name 你的账户名 

git config --global user.email  你的邮箱
```

##### **配置结束后再执行commit命令**

```bash
远程仓库的提交（第一次连接）
git remote add origin +你刚刚复制的地址
git push -u origin master （空仓库加 -u）
//仓库关联
```

**生成静态页面**

```bash
hexo cl&&hexo g
```

**切换github分支**

```bash
git checkout master
```

