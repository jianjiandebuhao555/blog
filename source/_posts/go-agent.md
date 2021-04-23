---
title: Golang 安装模块不成功？代理搞定一切
date: 2021-04-15 11:33:35
tags:
    - Golang
    - 代理
    - 模块
    - 教程
categories:
    - Golang
cover: /img/cover.jpg
---

> 我们使用 Golang 进行编程，往往需要引入第三方模块等，但是直接使用 `go get ...` 往往会超时等问题，下面我们就解决掉这个方法，同其它编程语言一样，通过开启代理进行提高下载效率及速度，这样往后的下载就会变得无比快的。

<!--more-->

-------

##### 教程

> **如果您使用的 Go 版本是 1.13 及以上 （推荐）**

```shell
$ go env -w GO111MODULE=on
$ go env -w GOPROXY=https://goproxy.io,direct
$ 
$ # 设置不走 proxy 的私有仓库，多个用逗号相隔（可选）
$ go env -w GOPRIVATE=*.corp.example.com
$ 
$ # 设置不走 proxy 的私有组织（可选）
$ go env -w GOPRIVATE=example.com/org_name
```

> 设置完上面几个环境变量后，您的 `go` 命令将从公共代理镜像中快速拉取您所需的依赖代码了。[私有库的支持请看这里](https://goproxy.io/zh/docs/goproxyio-private.html)。

-------

> **如果您使用的 Go 版本是 1.12 及以下**

> *Bash (Linux or macOS) [Linux 和 MacOS 系统]*

```shell
$ # 启用 Go Modules 功能
$ export GO111MODULE=on
$ # 配置 GOPROXY 环境变量
$ export GOPROXY=https://goproxy.io
```

> 或者，根据 [文档](https://goproxy.io/zh/docs/getting-started.html) 可以把上面的命令写到.profile或.bash_profile文件中长期生效。

> *PowerShell (Windows) [Windows 系统]*

```shell
$ # 启用 Go Modules 功能
$ env:GO111MODULE="on"
$ # 配置 GOPROXY 环境变量
$ env:GOPROXY="https://goproxy.io"
```

> 现在，当你构建或运行你的应用时，Go 将会通过 goproxy.io 获取依赖。更多信息请查看  [使用指引](https://goproxy.io/zh/docs/getting-started.html)。

> 一个全球代理，为 Go 模块而生  [Goproxy](https://goproxy.io/zh/)

-------