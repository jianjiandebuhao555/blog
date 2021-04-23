---
title: Hello World
date: 2021-04-15 09:33:35
tags:
    - hello
categories:
    - hello
cover: /img/cover.jpg
---

> 简单写作基本语法说明

<!--more-->

-------

# 标题

```markdown
# H1
## H2
### H3
#### H4
##### H5
###### H6
```

# H1

## H2

### H3

#### H4

##### H5

###### H6

-------

# 段落

```markdown
这是一个段落。
我还是这一段的一部分。

新的一段。
```

这是一个段落。
我还是这一段的一部分。

新的一段。

-------

# 图片

```markdown
网络图片

![网络图片](https://i.loli.net/2019/04/13/5cb1d33cf0ee6.jpg)

本地图片

![本地图片](/img/zhifeiji.gif)

```

网络图片

![网络图片](https://i.loli.net/2019/04/13/5cb1d33cf0ee6.jpg)

本地图片

![本地图片](/img/zhifeiji.gif)

-------

# 引用

```markdown
> 这是一个块的引用
```

> 是一个块的引用

-------

# 代码块

``````markdown
```javascript
// Fenced **with** highlighting
function doIt() {
    for (var i = 1; i <= slen ; i^^) {
        setTimeout("document.z.textdisplay.value = newMake()", i*300);
        setTimeout("window.status = newMake()", i*300);
    }
}
```
``````

```javascript
function doIt() {
    for (var i = 1; i <= slen ; i^^) {
        setTimeout("document.z.textdisplay.value = newMake()", i*300);
        setTimeout("window.status = newMake()", i*300);
    }
}
```

-------

# 表格

```markdown
| Colors        | Fruits          | Vegetable         |
| ------------- |:---------------:| -----------------:|
| Red           | *Apple*         | [Pepper](#Tables) |
| ~~Orange~~    | Oranges         | **Carrot**        |
| Green         | ~~***Pears***~~ | Spinach           |
```

| Colors        | Fruits          | Vegetable         |
| ------------- |:---------------:| -----------------:|
| Red           | *Apple*         | [Pepper](#Tables) |
| ~~Orange~~    | Oranges         | **Carrot**        |
| Green         | ~~***Pears***~~ | Spinach           |

-------

# 列表类型

#### 有序列表

```markdown
1. First item
2. Second item
3. Third item
```

1. First item
2. Second item
3. Third item

#### 无序列表

```markdown
- First item
- Second item
- Third item
```

- First item
- Second item
- Third item

-------

# 公式

```
$$
evidence\_{i}=\sum\_{j}W\_{ij}x\_{j}+b\_{i}
$$

$$
AveP = \int_0^1 p(r) dr
$$

When $a \ne 0$, there are two solutions to \(ax^2 + bx + c = 0\) and they are
$$x = {-b \pm \sqrt{b^2-4ac} \over 2a}.$$
```

$$
evidence\_{i}=\sum\_{j}W\_{ij}x\_{j}+b\_{i}
$$

$$
AveP = \int_0^1 p(r) dr
$$

当 $a \ne 0$, \(ax^2 + bx + c = 0\) 有两个解，它们是
<!-- When $a \ne 0$, there are two solutions to \(ax^2 + bx + c = 0\) and they are -->
$$x = {-b \pm \sqrt{b^2-4ac} \over 2a}.$$

-------

#### 表情

测试`emoji`表情 .
:smile:
:see_no_evil:
:smile_cat:
:watermelon:

-------