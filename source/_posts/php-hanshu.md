---
title: PHP相关函数调用说明
date: 2021-04-15 11:51:59
tags:
    - php
    - 函数
categories:
    - php
cover: /img/cover.jpg
---

> 日常PHP项目开发中，总会需要调用到PHP相关的函数，我们不可能每一个都能记住的，所以就使用一个，就记录一下，也方便自己以后查找！

<!--more-->

-------

### strip_tags()

```PHP

# 从字符串中去除 HTML 和 PHP 标记

strip_tags(string $str [, string $allowable_tags ]);

# 第一个参数为必须的，也就是要去除 `HTML` 和 `PHP` 标记的源数据，第二个参数是可选的，表示不需要过滤的标记。

```

-------

### uniqid()

```PHP

# 函数基于以微秒计的当前时间，生成一个唯一的 ID

uniqid(prefix, more_entropy);

# 如果 `prefix` 参数为空，则返回的字符串有 13 个字符串长。如果 `more_entropy` 参数设置为 `true`，则是 `23` 个字符串长。
# 如果 `more_entropy` 参数设置为 `true`，则在返回值的末尾添加额外的熵（使用组合线形同余数生成程序），这样可以结果的唯一性更好。

```

-------

### strlen()

```PHP

# 函数返回字符串的长度

strlen(string $str);

# string $str 必需。指定被填充的字符串，

```

-------

### mb_strlen()

```PHP

# 函数返回中文字符串的长度

mb_strlen(string  $str [, string $encoding = mb_internal_encoding() ]);

# string $str 必需。指定被填充的字符串
# string $pad_str 可选。字符编码。如果省略，则使用内部字符编码。

```

-------

### str_pad()

```PHP

# 将字符串填充成指定长度的字符串

str_pad(string $str, int $len, string $pad_str, string $pad_type);

# string $str 必需。指定被填充的字符串
# int $len 指定被填充的字符串的长度，如果值为负数或小于字符串的长度则不填充
# string $pad_str 要填充的字符串
# int $pad_type 指定填充的方向 `STR_PAD_RIGHT` (右), `STR_PAD_LEFT` (左)或 `STR_PAD_BOTH` (前面两者)

```

-------

### str_split()

```PHP

# 将字符串分割为数组

str_split(string $str,int $len);

# string $str 必需。规定要分割的字符串。
# int $len 可选。规定每个数组元素的长度。默认是 1。

```

-------