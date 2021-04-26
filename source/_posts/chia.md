---
title: chia
tags:
  - chia
  - 教程
categories:
  - chia
cover: /img/chia/chia_logo.svg
feature: false
date: 2021-04-25 20:58:58
preview:
---

> `Chia`(奇亚)于2017年8月注册成立，旨在开发一个改进的区块链和智能交易平台。我们正在构建`Chia`网络，以改善全球金融和支付系统。`Chia`将成为第一个企业级数字货币。Chia使用的是比特币以来第一个新的中本聪共识算法。它被称为 "空间和时间证明"（`Proof of Space and Time`），是由目前最优秀的网络协议工程师、`BitTorrent`的发明者`Bram Cohen`创建的。`Chialisp`是`Chia`新推出的智能交易编程语言，功能强大、易于审核、安全。目前可供参考的智能交易有：原子交换、授权收款人、可恢复钱包、多重签名钱包和限价钱包。

<!--more-->

![`chia`](/img/chia/0.png)

-------

### `Chia`(奇亚)参数

> - 名称：`Chia`
> - 中文名称：奇亚
> - 缩写：`XCH`
> - 是否`ICO`：否
> - 是否预挖：2100万个作为战略储备，详情查看商业白皮书
> - 每块收益：每10分钟64个`Chia`奖励
> - 减半策略：3年一减半，第十三年起每10分钟4`Chia`

### 和传统挖矿的区别

> 与`BTC`、`ETH`采用工作量证明（`POW`）不同的是，`Chia`(奇亚)采用"空间和时间证明"（`Proof of Space and Time`），利用存储设备（电脑、服务器、`NAS`、树莓派）中的剩余存储空间进行挖矿。

> 在开始挖矿之前需要在闲置硬盘空间进行播种（`plots`），然后农民（`farmer`）在已经播种好的`P盘`文件（`plots files`）上寻找最佳爆块答案。`Chia`硬盘挖矿的本质就是先将加密数据写入硬盘（`plots`过程），然后挖矿程序在P盘文件中寻找最优答案（`farmer`过程），所以你的`P`盘文件总容量相对于全网容量占比越高，越容易爆块，对应的挖矿收益也越高。

> 播种的过程需要占用`CPU`、内存（每个P盘线程默认需要`4G`内存空间）和硬盘临时空间（生成`K = 32`规格的播种文件大概需要占用`332G`临时空间）。因此播种（`Plots`）的过程建议采用性能较好的`CPU`、`16G`以上内存和固态硬盘（建议合计`2T`以上的`M2.NVME`协议`SSD`）

-------

### 挖矿教程

1、下载最新版`Chia-Blockchain`重钱包。
- [官方下载地址](https://github.com/Chia-Network/chia-blockchain/releases)

![](/img/chia/1.png)

2、以管理员身份运行安装程序

![](/img/chia/2.png)

3、安装完成后`Chia`重钱包将会自动运行，首次运行需要创建一个新的秘钥

![](/img/chia/3.png)

![秘钥生成中](/img/chia/4.png)

4、备份助记词，建议用截图的方式进行妥善保存。助记词是恢复钱包的重要途径之一，因此非常重要，千万不要遗失或者泄露给他人。

![](/img/chia/5.png)

5、备份好助记词以后，点击下一步钱包即可顺利运行。

![](/img/chia/6.png)

6、点击左侧`Plots`菜单进入`P`盘管理界面，在P盘管理界面点击 “`ADD A LOT`”按钮创建一个P盘任务

![](/img/chia/7.png)

7、`P`盘文件格式选择`K=32`，新手第一次播种`P`盘文件数量建议选择`1`，临时存储空间选择`SSD`固态硬盘（`1`个`P`盘线程需要占用`332G`的临时空间，空间太小会造成播种失败），最终`P`盘文件存放路径可以选择机械硬盘的分区，`K=32`规格的`P`盘文件最终会占用`101.4G`硬盘空间。

![](/img/chia/8.png)

8、P盘完成且钱包区块更新至最新后，就开启了挖矿之旅。

![](/img/chia/9.png)

![](/img/chia/10.png)

-------

**`Chia`(奇亚)资料库**

[`Chia`(奇亚)官网](https://www.chia.net/)

[区块浏览器](https://www.chiaexplorer.com/)

[`Github`源码库](https://github.com/Chia-Network)

[技术绿皮书](https://www.chia.net/assets/ChiaGreenPaper.pdf)

-------