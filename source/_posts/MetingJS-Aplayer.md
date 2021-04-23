---
title: Aplayer搭配MetingJS音乐插件的使用
date: 2021-04-15 15:09:08
tags:
    - Aplayer
    - MetingJS
    - 插件
categories:
    - web
cover: /img/cover.jpg
---

> Aplayer官网文档：https://aplayer.js.org/
> Metingjs官网文档：https://github.com/metowolf/MetingJS
> Aplayer是一个功能强大的HTML5音乐播放器，Metingjs基于Aplayer插件封装好的插件，开箱即用。

<!--more-->

-------

##### MetingJS 的简单使用

```html

<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8" />
		<title></title>	
	<!-- require APlayer -->
	<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/aplayer/dist/APlayer.min.css">
	<script src="https://cdn.jsdelivr.net/npm/aplayer/dist/APlayer.min.js"></script>
	<!-- require MetingJS -->
	<script src="https://cdn.jsdelivr.net/npm/meting@2.0.1/dist/Meting.min.js"></script>
	</head>
	<body>

	<meting-js server="netease" type="playlist" id="60198"></meting-js>
		
	</body>
</html>

```

-------

##### 简要解释

```markdown

解析：server="netease" type="playlist" id="60198"

server指音乐平台，netease指网易云音乐， type类型，playlist列表，id指歌曲的i或者专辑或列表外链id
因此重点在于指定平台，指定外链id

```

-------

##### 配置选项说明

| 选项 | 默认 | 描述 |
|:------:|:------:|:------:|
| id(编号) | require | 歌曲ID/播放列表ID/专辑ID/搜索关键字 |
| server(平台) | require | 音乐平台：netease，tencent，kugou，xiami，baidu |
| type（类型） | require | song，playlist，album，search，artist |
| auto（支持类种类） | options | 音乐链接，支持：netease，tencent，xiami |
| fixed（固定模式） | false | 启用固定模式，默认false |
| mini（迷你模式） | false | 启用迷你模式,默认false |
| autoplay（自动播放） | false | 音频自动播放，默认false |
| theme(主题颜色) | #2980b9 | 默认#2980b9 |
| loop（循环） | all | 播放器循环播放，值：“all”，one”，“none” |
| order(顺序) | list | 播放器播放顺序，值：“list”，“random” |
| preload(加载) | auto | 值：“none”，“metadata”，“'auto” |
| volume（声量） | 0.7 | 默认音量，请注意播放器会记住用户设置，用户自己设置音量后默认音量将不起作用 |
| mutex（限制） | true | 防止同时播放多个玩家，在该玩家开始播放时暂停其他玩家 |
| lrc-type（歌词） | 0 | 歌词显示 |
| list-folded（列表折叠） | false | 指示列表是否应该首先折叠 |
| list-max-height（最大高度） | 340px | 列出最大高度 |
| storage-name（储存名称） | metingjs | 存储播放器设置的localStorage键 |

-------