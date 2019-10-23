---
title: "HTML入门笔记1"
date: 2019-10-23T15:59:12+08:00
draft: false
---

### 历史

>HTML的英文全称是 Hypertext Marked Language，即超文本标记语言。HTML是由Web的发明者 Tim Berners-Lee(李爵士)和同事 Daniel W. Connolly于1990年创立的一种标记语言——百度百科

### HTML起手式
```html
<!DOCTYPE html>
<html lang="zh-CN">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width,initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatiable" content="ie=edge" />
    <title>我的网页</title>
  </head>
  <body></body>
</html>
```

### 常用的表示章节的标签
- h1~h6
表示标题，h1字体最大，依次减少

- section
表示章节

- article
表示文章

- header
放在顶部的结构，比如顶部广告

- footer
放在底部的结构，比如版权声明

- main
主要内容

- aside
旁支内容

#### 示例
```html
<header>顶部广告</header>
<div>
<main>
  <h1>文章标题</h1>
  <section>
    <h2>第一章</h2> 
    <p>内容</p>
      <setion>
        <h3>1.1节</h3>
        <p>一段话</p>
      </setion>
      <setion>
        <h3>1.2节</h3>
        <p>一段话</p>
      </setion>
  </section>
</main>
<aside>
 参考资料123
</aside>
</div>
<footer>底部广告</footer>
```

### 全局属性
所有标签都有的属性

- class 标签类名

- contenteditable 标签内容可编辑

- hidden 隐藏标签

- id 标签id

- style 设置标签样式

- tabindex 规定元素的 tab 键控制次序(0是最后一个，-1表示不被tab访问)

- title 规定关于元素的额外信息，以弹框提示

### 常用的内容标签

- ol(order list) + li(list items)
有序列表

- ul(unordered) + li
无序列表

- dl + dt(term) + dd(description)
描述列表

- hr 
水平分割线

- br
换行

- strong
表示强调内容很重要

- em
表示强调语气很重要

- code
用于表示计算机源代码或者其他机器可以阅读的文本内容。

- pre
定义预格式化的文本。被包围在 pre 元素中的文本通常会保留空格和换行符。而文本也会呈现为等宽字体。

- quote
内联引用

- blockquote
块引用