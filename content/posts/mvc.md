---
title: "浅析Mvc"
date: 2020-03-13T10:14:38+08:00
draft: false
---

MVC是一种组织代码的形式，将数据相关放在Model中，
将视图相关放入View中，将操作和连接M和V放入Controller中。
比如在编写后端时，一般将数据库的表映射和主键等相关信息放在Model中，
然后View层放入前端模板文件，Controller梳理数据逻辑然后发送到View层。
一般来说这种编写代码方式在讲前后端分离的现在已经没多少人用了。

而前端处理数据又越来越多，所以我们现在可以将MVC的理念放在前端中。

### MVC三个对象

我们可以将MVC抽象成三个对象

```javascript
const model = {
  create() {},
  delete() {},
  update() {},
  get() {}
}
```

```javascript
const view = {
  el: '指定标签',
  render() {}
}
```

```javascript
const controller = {
  init() {}
  //可以在这做初始化和绑定事件等动作
}
```

主要的逻辑是数据发生变化时render()重新渲染视图
主要的问题是如何监听数据变化，我们可以用到一种EventBus的概念

```javascript
import $ from 'jquery'
const eventBus = $({})
```

因为jquery对象同时拥有监听和触发事件的方法，我们可以这样
在Model中触发自定义事件

```javascript
model.udpate() {
  //修改数据后
  eventBus.trigger('changeData')
}
```

我们就可以在Controller中监听到

 ```javascript
controller.init() {
  eventBus.on('changeData', () => {
    view.render()
  })
}
```

### 表驱动编程

我们可以将数组、对象、Map等作为表进行查询等操作省去了switch或者无数个ifelse的操作
比如

```javascript
function getChineseWeekByDate(date) {
    const numWeekDay = date.getDay();
    const weekArr = ['周日', '周一','周二','周三','周四','周五','周六'];
    return weekArr[numWeekDay] ||  '';
}
```

### 模块化

推荐文章[前端模块化详解](https://segmentfault.com/a/1190000017466120#item-3-8)
