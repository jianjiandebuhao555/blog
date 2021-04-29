---
title: KMS 密钥激活
tags:
  - KMS
  - 教程
categories:
  - KMS
cover: /img/cover.jpg
feature: false
date: 2021-04-28 18:58:58
preview:
---

> `Windows` `KMS` 密钥激活教程收集

<!--more-->

-------

### 激活步骤

1、右键开始图标，选择 `Windows PowerShell`(管理员)，或者命令提示符(管理员)

![]('/img/Windows/Windows PowerShell.png')

2、依次执行下面的命令

```shell

# 安装 Windows 密钥
slmgr /ipk 秘钥

# 设置 KMS 服务器
slmgr /skms zh.us.to

# 激活 Windows 系统
slmgr /ato

# 查询激活状态，
slmgr /xpr

```

| 操作系统 | 秘钥 |
|:-------:|:-------:|
| Windows Server 2019 | WMDGN-G9PQG-XVVXX-R3X43-63DFG |

** `KMS` 激活一般180天，到期后再次操作进行激活**

3、如果执行上面还是没有办法激活，那就进入设置里面找到激活，更换新的秘钥试一试

| 操作系统 | 秘钥 |
|:-------:|:-------:|
| Windows Server 2019 | N69G4-B89J2-4G8F4-WWYCC-J464C |

-------