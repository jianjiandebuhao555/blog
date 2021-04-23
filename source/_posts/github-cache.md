---
title: 解决 "The file will have its original line endings in your working directory"
tags:
  - github
  - 问题解决
categories:
  - github
cover: /img/cover.jpg
feature: false
date: 2021-04-23 10:25:17
preview:
---

> 当通过 `git clone` 后的代码 `git push` 到自己 `github` 仓库有时候就会出现 `The file will have its original line endings in your working directory` 问题，接下来看看应该如何解决！

<!--more-->

-------

> 解决方法如下：

```shell

git rm -r --cached .

git config core.autocrlf false

git add .

```

** `.` 代表当前目录里所有文件夹及文件，但是也会自动过滤掉 `.gitignore` 文件中配置的对象 **

-------