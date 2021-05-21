---
title: Swar-Chia-Plot-Manager 绘图管理工具
tags:
  - chia
  - Swar-Chia-Plot-Manager
  - 绘图工具
  - 翻译文章
categories:
  - chia
cover: /img/chia/swar-chia-plot-manager.png
feature: false
date: 2021-05-21 11:03:52
preview:
---
> 以下内都为机翻，能看个大概，方便大家明白怎样配置使用就 OK 啦

<!--more-->

-------

# Swar's Chia Plot Manager 

#### 一个用于Chia绘图的绘图管理器: https://www.chia.net/

![绘图工具视图](/img/chia/swar-chia-plot-manager.png "视图")

-------

##### Development Version: v0.1.0

这是一个跨平台的Chia Plot Manager，可以在主要的操作系统上工作。这不是一个绘图器。这个库的目的是管理你的绘图，并用你配置的设置来启动新的绘图。每个人的系统都是独一无二的，所以定制是刻在这个库中的一个重要特征。

这个库很简单，容易使用，而且可靠，可以保持剧情的生成。

这个库已经在Windows和Linux上进行了测试。

## 特点

* 错开你的绘图，以便你的计算机资源可以避免高峰期。
* 允许有一个目标目录列表。
* 通过尽早开始新的地块，最大限度地利用临时空间的潜力。
* 同时运行最大数量的地块，以避免瓶颈或限制资源占用。
* 更加深入的活动情节屏幕。

-------

## 常见问题

##### 我可以重新加载我的配置吗？
* 是的，你的配置可以通过`python manager.py restart`命令来重新加载，或者你可以单独停止并重新启动管理器。请注意，你的作业数将被重置，临时目录2和目标目录的顺序也将被重置。
* 请注意，如果你改变作业的任何一个目录，会扰乱现有的作业，`manager`和`view`将无法识别旧的作业。如果你在改变作业目录的同时还有活动的绘图，请将当前作业的`max_plots`改为0，然后用新的目录做一个单独的作业。我**不建议**在绘图运行时改变目录。

##### 如果我停止绘图工具的工作，会不会扼杀我的作品？
* 不，进程是在后台启动的，它们不会杀死你现有的进程。如果你想杀死它们，你可以访问PID，用任务管理器（或适合你操作系统的软件）追踪它们，并手动杀死它们。请注意，你还必须删除.tmp文件。我不为你处理这个问题。

##### 如果我有一个列表，如何选择临时2和目的地？
* 它们是按顺序选择的。如果你有两个目录，第一个情节将选择第一个，第二个将选择第二个，而第三个情节将选择第一个。

##### 什么是`temporary2_destination_sync`？
* 一些用户喜欢选择总是拥有相同的临时2和目标目录。启用此设置将使temporary2总是被用作目标驱动器。如果你使用这个设置，你可以使用一个空的临时2目录列表。

##### 什么是适合我的设置的最佳配置？
* 请将此问题转发到Keybase或讨论标签。

-------

## 所有命令

##### 命令的使用实例

```shell
> python3 manager.py start

> python3 manager.py restart

> python3 manager.py stop

> python3 manager.py view

> python3 manager.py status

> python3 manager.py analyze_logs
```

### start

这个命令将在后台启动管理器。一旦你启动它，它就会一直运行，除非所有工作都完成了`max_plots'或者出现了错误。错误将被记录在创建的`debug.log`文件中。

### stop

这个命令将终止后台的管理器。它不会停止正在运行的绘图，只会停止新绘图的创建。

### restart

该命令将按顺序运行启动和停止。

### view

这个命令将显示你可以用来跟踪你的运行图的视图。它将每隔X秒更新一次，由你的`config.yaml`定义。

### status

该命令将对视图进行一次快照。它不会循环。

### analyze_logs

这个命令将分析你的日志文件夹中所有已完成的绘图日志，并为你的计算机配置计算出适当的权重和线端。只需在你的`config.yaml`中的`progress`部分填入返回的值。这只影响进度条。

## Installation

这个库的安装是很简单的。我在下面附上了详细的说明，应该可以帮助你开始安装。

#### 注意：如果`python`不工作，请尝试`python3`。

1. 下载并安装Python 3.7或更高版本: https://www.python.org/
2. `git clone` 这个[Swar-Chia-Plot-Manager](https://github.com/swar/Swar-Chia-Plot-Manager)或下载[源码](https://github.com/swar/Swar-Chia-Plot-Manager/releases)。
3. 打开CommandPrompt / PowerShell / Terminal，`cd`进入主库文件夹。
   * 例子: `cd C:\Users\Swar\Documents\Swar-Chia-Plot-Manager`
4. 可选：为 Python 创建一个虚拟环境。如果你用Python做其他事情，建议这样做。
	1. 创建一个新的Python环境: `python -m venv venv`
	   * 第二个`venv`可以重命名为你想要的任何东西。我更喜欢`venv`，因为它是一个标准。
	2. 激活虚拟环境。这必须在*每一次*你打开新窗口时进行。
	   * Windows: `venv\Scripts\activate`
	   * Linux: `. ./venv/bin/activate` or `source ./venv/bin/activate`
	   * Mac OS: `/Applications/Chia.app/Contents/Resources/app.asar.unpacked/daemon/chia`
	3. 通过看到"(venv) "前缀来确认它已经激活。前缀将根据你给它起的名字而改变。
5. 安装所需的模块: `pip install -r requirements.txt`
	* 如果你打算使用 "Notifications "或 "Prometheus"，那么运行以下程序来安装所需模块: `pip install -r requirements-notification.txt`
6. 复制`config.yaml.default`并在同一目录下命名为`config.yaml`。
7. 按照你自己的个人设置编辑和设置config.yaml。下面有更多关于这方面的帮助。
	* 你还需要添加`chia_location`! 这应该指向你的chia可执行文件。
9. 运行管理器：`python manager.py start`。
   * 这将在后台启动一个进程，根据你输入的设置来管理地块。
10. 运行视图。`python manager.py view`。
   * 这将循环查看屏幕上有关活动地块的详细信息。

-------

## 配置

这个库的配置对每个终端用户来说都是独一无二的。`config.yaml`文件是配置的所在。

这个情节管理器是基于工作的想法而工作的。每项工作都有自己的设置，你可以对其进行配置和定制。没有两个驱动器是独一无二的，所以这将为你自己的限制和要求提供灵活性。

### chia_location

这是 chia 官方 P 图可执行文件 chia.exe 所在的文件目录.

* Windows: `C:\Users\<USERNAME>\AppData\Local\chia-blockchain\app-1.1.2\resources\app.asar.unpacked\daemon\chia.exe`
* Linux: `/usr/lib/chia-blockchain/resources/app.asar.unpacked/daemon/chia`
* Another Linux: `/home/swar/chia-blockchain/venv/bin/chia`

### 管理设置

这些是只由绘制管理器使用的配置设置。

* `check_interval` - 在检查是否有新任务开始之前的等待秒数。
* `log_level` - 保持在 ERROR 上，只在有错误时记录。把它改为 INFO，以便看到更详细的日志记录。警告:INFO 会写下大量的信息。

### 日志

* `folder_path` - 这是你的日志文件的文件夹，用于保存绘图日志。

### 视图

这些是视图将使用的设置

* `check_interval` - 更新视图前的等待秒数。
* `datetime_format` - 视图中希望显示的日期时间格式。格式化见这里：https://docs.python.org/3/library/datetime.html#strftime-and-strptime-format-codes
* `include_seconds_for_phase` - 时间转换格式是否包括秒。
* `include_drive_info` - 是否会显示驱动器相关信息。
* `include_cpu` - 是否显示CPU的相关信息。
* `include_ram` - 是否显示RAM的相关信息。
* `include_plot_stats` - 是否会显示绘图统计相关信息。

### 通知设置

这些是不同的设置，以便在绘图管理器启动和绘图完成时发送通知。

### 仪表

启用 Prometheus 收集指标的设置。 

* `prometheus_enabled` - 如果启用，将收集指标，并启动一个HTTP服务器，为Prometheus提供指标。
* `prometheus_port` - HTTP服务器端口。

收集到的指标清单

- **chia_running_plots**: 一个[Gauge](https://prometheus.io/docs/concepts/metric_types/#gauge)可以看到目前有多少块地正在被创建。
- **chia_completed_plots**: A [Counter](https://prometheus.io/docs/concepts/metric_types/#counter)为完成的地块。

### 进展

* `phase_line_end` - 这些设置将用于决定各个阶段在进度条中的结束时间。它应该反映出该阶段结束的线，这样进度计算就可以使用该信息与现有的日志文件来计算进度百分比。
* `phase_weight` - 这些是在进度计算中分配给各个阶段的权重,通常情况下，第1和第3阶段是最长的阶段，所以它们应该比其他阶段拥有更多的权重。

### 全局
* `max_concurrent` - 你的系统可以运行的最大绘图数量,管理器在一段时间内启动的地块总数不会超过这个数量。
* `max_for_phase_1` - 你的系统在第一阶段可以运行的最大绘图数量。
* `minimum_minutes_between_jobs` - 开始一个新的绘图工作前的最小分钟数，这可以防止多个工作在完全相同的时间开始。这将缓解目标驱动器上的拥挤情况。设置为0表示禁用。

### 任务

每个工作必须有独特的临时目录。

这些是每个任务使用的设置，请注意，你可以有多个任务，每个任务都应该是YAML格式的，这样才能正确配置。这里几乎所有的值都将被传递到Chia可执行文件中。

点击这里参考更多关于Chia CLI的详情：https://github.com/Chia-Network/chia-blockchain/wiki/CLI-Commands-Reference

* `name` - 这是任务的名字。
* `max_plots` - 这是在管理器的一次运行中，任务的最大数量。任何重新启动管理器的操作都会重置这个变量，它在这里只是为了帮助你在这段时间内的绘图。
* [OPTIONAL]`farmer_public_key` - 你的 chia 耕种公钥。如果没有提供，它将不会把这个变量传给 chia 执行程序，从而导致你的默认密钥被使用。只有当你在一台没有你的证书的机器上设置了 chia 时才需要这个。
* [OPTIONAL]`pool_public_key` - 你的池公钥。与上述信息相同。
* `temporary_directory` - 可以是一个单一的值或一个值的列表。这是将进行绘图的地方。如果你提供的是一个列表，它将逐个循环浏览每个驱动器。
* [OPTIONAL]`temporary2_directory` - 可以是一个单一的值或一个值的列表。这是一个可选的参数，在你想使用Chia绘图的temporary2目录功能时使用。
* `destination_directory` - 可以是一个单一的值或一个值的列表。这是绘图完成后将被转移到的最终目录。如果你提供一个列表，它将逐一循环浏览每个驱动器。
* `size` - 这指的是绘图的k大小。你可以在这里输入32、33、34、35......
* `bitfield` - 这指的是你是否想在你的绘图中使用bitfield通常情况下，推荐使用 true
* `threads` - 这是将分配给绘图仪的线程数。只有第1阶段使用1个以上的线程。
* `buckets` - 要使用的桶的数量。Chia 提供的默认值是128。
* `memory_buffer` - 你想分配给进程的内存量。
* `max_concurrent` - 该工作在任何时候拥有的最大数量的地块。
* `max_concurrent_with_start_early` - 在任何时候，包括提前开始的阶段，这项工作要拥有的最大数量的地块。
* `initial_delay_minutes` - 这是在启动第一项工作时使用的初始延迟。它只考虑一次。如果你重新启动管理器，它仍然会坚持这个值。
* `stagger_minutes` - 在这项工作的下一个情节被启动之前，需要等待的分钟数。如果你想让你的地块在并发限制允许的情况下立即被启动，你甚至可以把它设置为零。
* `max_for_phase_1` - 这个任务在第1阶段的最大绘图数量。
* `concurrency_start_early_phase` - 你想提前启动一个绘图的阶段。建议使用4。
* `concurrency_start_early_phase_delay` - 当检测到提前开始阶段时，在新的绘图被启动之前的最大等待分钟数。
* `temporary2_destination_sync` - 这个字段将始终提交目标目录作为temporary2目录。这两个目录将是同步的。
* `exclude_final_directory` - 是否跳过向收割机添加`目的地目录'以进行耕作
* `skip_full_destinations` - 启用该功能后，它将计算所有正在运行的绘图和未来绘图的大小，以确定驱动器上是否有足够的空间来启动作业。如果没有，它将跳过这个目标，进入下一个目标。一旦所有的都满了，它将禁用作业。
* `unix_process_priority` - 仅限UNIX。这是地块生成时将被赋予的优先级。UNIX值必须在-20和19之间。该值越高，进程的优先级越低。
* `windows_process_priority` - 仅限Windows。这是地块生成时将被赋予的优先权。窗口值不同，应该设置为以下值之一：
	* 16384 `低于正常优先级`
	* 32    `正常优先级`
	* 32768 `高于正常优先级`
	* 128   `高优先级类`
	* 256   `实时性_优先级_类别`
* `enable_cpu_affinity` - 启用或禁用绘图进程的cpu亲和性。当排除一个或两个线程的绘图过程时，绘图和收割的系统可能会看到收割机或节点性能的改善。
* `cpu_affinity` - 为进程分配的cpu（或线程）的列表。默认例子假设你有一个超线程的4核CPU（8个逻辑核心）。这个配置将限制绘图进程使用逻辑核心0-5，把逻辑核心6和7留给其他进程（6个受限，2个自由）。

-------