---
title: mysql通过经纬度坐标获取距离并按距离从近到远排序
date: 2021-04-15 11:50:27
tags:
    - mysql
    - php
    - 经纬度
    - 排序
categories:
    - mysql
    - php
cover: /img/cover.jpg
---

> 记录一下mysql通过经纬度坐标获取距离并按距离从近到远排序实现功能

<!--more-->

-------

**代码展示**

```php
SELECT
*,
(6371 * acos(cos(radians({$lat})) * cos(radians(lat)) * cos(radians(lon) - radians({$lon})) + sin(radians({$lat})) * sin(radians(lat)))) AS distance
FROM table
HAVING distance &lt; 1
ORDER BY distance
LIMIT 1;
```

-------

**简要说明**

```
# 参数纬度，请替换成自己需要查询的纬度
{$lat}

# 参数经度，请替换成自己需要查询的经度
{$lon}

# 两个经纬度间的距离
(6371 * acos(cos(radians({$lat})) * cos(radians(lat)) * cos(radians(lon) - radians({$lon})) + sin(radians({$lat})) * sin(radians(lat))))  AS distance

# 查询的表名
table

# 筛选距离小于1km的数据(可不写)，如果没查到数据就是没有
HAVING distance < 1

# 根据距离远近来排序 默认升序 （可不写）
ORDER BY distance

# 显示前1条数据（可不写）
LIMIT 1
```

-------