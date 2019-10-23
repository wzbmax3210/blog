---
title: "HTML常用标签"
date: 2019-10-23T17:06:01+08:00
draft: false
---

### `<a>`
***
#### 作用
- 跳转外部页面
- 跳转内部锚点
- 跳转到邮箱或者电话

#### 属性

#### href取值
- 表示http路径`/a/b/c`(根目录是http服务的目录) 以及  `a/b/c`<br>
- 锚点 `#` 跳到顶部 `#id` 跳到对应id的标签<br>
- 伪协议
1. `javascript:;` 用处：解决点击页面不刷新不变化的需求<br>
2. 邮箱 `mailto:test@gmail.com`
3. 电话 `tel:13111111111`

#### target取值
- `_blank` 新页面打开
- `_top` iframe打开顶部
- `_self` 本页打开
- `_parent` iframe上一层打开
- `xxx` 打开一个xxx的页面(window.name = xxx)，打开iframe name为xxx的页面

#### download
作用：不是打开页面，而是下载页面<br>
问题：不是所有浏览器支持，手机浏览器支持程度最差

### `<table>`
***
#### 相关的标签
- `<thead>`
- `<tbody>`
- `<tfoot>`
- `<tr>`(table row)
- `<td>`(table data)
- `<th>`(table head)

#### 相关的样式
- `table-layout`设置表格布局算法 `auto` 浏览器自动 `fixed` 等宽
- `border-spacing`表格边框间隙
- `border-collapse` `collapse`合并表格边框

### `<img>`
***
#### 作用
发出get请求，展示一张图片

#### 属性
- alt 图片加载失败的文字提示
- height 图片展示高度
- width 图片展示宽度
- src 图片获取地址

#### 事件
- onload
- onerror

#### 响应式图片
设置`max-width`为100%

### `<form>`
***
#### 作用
发get或post请求，然后刷新页面

#### 属性
- action 提交的地址
- method 提交的方法(post/get)
- autocomplete 输入建议(历史账号)
- target 到哪个页面刷新

#### 事件
- onsubmit

### `<input>`
***
#### 作用
让用户输入内容

#### 属性
- 类型 type:button/checkbox/password/number/email/file/hidden/radio/search/submit/tel/text/reset
- 其他 name/autofocus/checked/disabled/maxlength/pattern/value/placeholder

#### 事件
- onchange
- onfocus
- onblur

#### 注意事项
- 一般不监听input的click事件(focus)
- form里面的input要有name
- form里面要放一个type=submit才能触发submit事件
