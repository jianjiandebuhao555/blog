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

### 集群教程

> Chia允许你在每台矿机上只运行一个收割机（harvester）程序连接到集中的一个全节点钱包（重钱包full node）上进行挖矿，而不必在每台机器上都运行完整的重钱包。采用这种模式可以让你的系统更简单，使用更少的带宽、空间、CPU，也让你的钱包秘钥更安全。全节点钱包通过UPNP或手动NAT指向（8444端口）打通外网可以连接到更多的其他钱包节点，在挖矿时，它会让你的整体农场更快、更高效。

> 整个农场（矿场）的架构是由一台运行全节点钱包（重钱包full node）的主机和其他只运行收割机（harvester）的机器组成。其中只有你的全节点钱包主机器会连接到Chia网络，而其他运行收割机的矿机只需要连接你的全节点钱包即可。

![](/img/chia/11.jpg)

> 为了保证你的收割机和主机之间的通信安全，使用了TLS加密技术，全节点钱包主机将是签署所有证书的私人认证机构（CA）。每个收割机都必须有自己的签名证书，才能与你的全节点钱包正常通信。

> 全节点钱包的安装教程本文不作叙述，需要这方面教程的可以参考《Chia挖矿教程》一文

1、 首先需要从全节点钱包安装目录中将收割机（harvester）相关程序拷贝出来，通常在windows下安装的chia钱包路径为 `%LocalAppData%\chia-blockchain`，其中我们需要将 `%LocalAppData%\chia-blockchain\app-1.0.1\resources\app.asar.unpacked\daemon` 文件夹整体复制到U盘中(注意：app-1.0.1为你当前安装的chia版本号，不同版本改路径需要自行修改)

2、将全节点钱包配置目录中的CA证书 (`%USERPROFILE%\.chia\mainnet\config\ssl\ca`文件夹) 复制到U盘中

![](/img/chia/12.jpg)

3、将U盘中的daemon、ca两个文件夹复制到收割机的C盘中。

4、执行 `c:\daemon\chia.exeinit` 命令进行初始化，然后执行 `c:\daemon\chia.exeinit-cc:\ca` 命令进行CA证书授权，这样可以为不同的收割机授权唯一的通信证书来确保收割机和全节点钱包之间的通讯安全。

![](/img/chia/13.jpg)

5、执行 `c:\daemon\chia.exe.configure--set-farmer peer192.168.88.181:8447` 命令为收割机配置全节点钱包主机的IP地址其中192.168.88.181需要修改为你全节点钱包的实际IP地址。当然你也可以通过修改 `%USERPROFILE%\.chia\mainnet\config\config.yaml` 配置文件中的`harvester->farmer_peer->host`参数进行修改（不同版本配置文件格式可能略有不同，请仔细查找）具体见下图：

![](/img/chia/14.jpg)

![](/img/chia/15.jpg)

6、执行 `c:\daemon\chia.exeplotsadd-d` `D:\plots\` 命令添加农田文件所在目录 `D:\plots\` 。如有多个硬盘路径，可以根据自己矿机实际情况修改`D:\plots\`后多次运行本命令

7、执行 `startc:\daemon\chia.exestartharvester` 命令启动收割机程序

![](/img/chia/17.jpg)

8、其他收割机只需要重复以上2-7步操作即可。

9、在如果需要重启或者关闭收割机程序，可以执行 `c:\daemon\chia.exestopharvester` 命令，或者执行 `c:\daemon\chia.exestopall-d` 命令可以关闭本台收割机上运行的所有chia相关程序。

**注意：**

1、你的路由器开启UPNP或者手动NAT指向（8444端口）确保外网可以正常访问，这样可以让全节点钱包连接到更多的其他chia节点

2、需要确保全节点钱包的8447端口可以被其他机器正常访问（windows防火墙需要开启该端口）

-------

**`Chia`(奇亚)资料库**

[`Chia`(奇亚)官网](https://www.chia.net/)

[区块浏览器](https://www.chiaexplorer.com/)

[`Github`源码库](https://github.com/Chia-Network)

[技术绿皮书](https://www.chia.net/assets/ChiaGreenPaper.pdf)

-------