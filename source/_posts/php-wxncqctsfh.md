---
title: PHP去掉微信昵称中特殊符号
date: 2021-04-15 11:53:13
tags:
    - php
    - 微信
    - 过滤
    - 特殊符号
categories:
    - php
cover: /img/cover.jpg
---

> 在处理微信用户数据入库的时候，由于表字段编码有所不同，会导致数据存库失败，有时候数据库处理也不方便，还是代码来的方便，代码下面附上

<!--more-->

-------

### 代码展示

```PHP
function remove_emoji($nickname) {
    $clean_text = "";
    // 匹配表情符号
    $regexEmoticons = '/[\x{1F600}-\x{1F64F}]/u';
    $clean_text = preg_replace($regexEmoticons, '', $nickname);

    // 杂项符号和象形文字的匹配。
    $regexSymbols = '/[\x{1F300}-\x{1F5FF}]/u';
    $clean_text = preg_replace($regexSymbols, '', $clean_text);

    // 匹配运输和地图符号
    $regexTransport = '/[\x{1F680}-\x{1F6FF}]/u';
    $clean_text = preg_replace($regexTransport, '', $clean_text);

    // 匹配杂项符号
    $regexMisc = '/[\x{2600}-\x{26FF}]/u';
    $clean_text = preg_replace($regexMisc, '', $clean_text);

    // 匹配装饰符
    $regexDingbats = '/[\x{2700}-\x{27BF}]/u';
    $clean_text = preg_replace($regexDingbats, '', $clean_text);

    return $clean_text;
}
```

-------