---
title: 简单的个人博客部署白嫖教程
tags:
  - github
  - hexo
  - vercel
  - 教程
  - 个人博客
categories:
  - 教程
cover: /img/cover.jpg
feature: false
date: 2021-04-23 10:42:41
preview:
---

> 这是一个 [`github`](https://github.com/) + [`hexo`](https://hexo.io/zh-cn/) + [`vercel`](https://vercel.com/) 部署简单个人博客白嫖教程

> 当前教程为 `Windows` 操作系统下的，其它操作系统参考即可，不能保证后期破图，所以教程为文字教程不带图

<!--more-->

-------

> 首先我们需要准备一个 `github` 账户，绑定的邮箱不推荐使用 `QQ邮箱` ，以免导致后续部署出现问题！当然已经绑定 `QQ邮箱` 还是可以进入 `github` `Settings` 里添加新的绑定邮箱后将它设置为默认即可

> 使用 `github` -> `new repository` 来创建一个新的项目

> 本地电脑安装上 `git` 后，使用 `Git Bash Here` 安装 `Hexo`

```shell

# 全局安装
npm install -g hexo-cli

# 初始化 hexo 目录
hexo init name # name 为名称，自定义即可

```

> `hexo` 个人博客就初始化完毕，接下来使用  `git push` 提交到 `github` 仓库中

```shell

cd name

git init

git add .

git commit -m "初始化"

git branch -M main

git remote add origin https://github.com/****/****.git

git push -u origin main

```

> 接下来就到 `vercel` 部署托管，
> 使用 `github` 账号授权登录，
> `New Project` 创建一个新项目，
> 会有 `Import Git Repository` 和 `Clone Template` 两个
> 在 `Import Git Repository` 中会有我们 `github` 仓库里创建的项目
> 选择我们作为 `hexo` 仓库的项目，点击 `Import` 按钮
> 选择 `github` 账号名称后面的 `Select`，第一个是团队的貌似需要付费使用
> `PROJECT NAME` 自行输入名称
> `FRAMEWORK PRESET` 选择 `Hexo`
> 点击 `Deploy` 下一步耐心等待部署完成就OK啦

> 以后只需要对 `hexo` `name` 项目进行修改添加等操作后 `git push` 提交到 `github` 仓库中就不需要任何其它操作，`vercel` 会自动更新部署的

> `vercel` 也支持解析域名，在 `Project` 点击 `Settings` 后选择 `Domains` 里进行添加并到域名平台进行解析即可

-------