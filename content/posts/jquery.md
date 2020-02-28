---
title: "jQuery对象基本用法"
date: 2020-02-28T20:39:52+08:00
draft: false
---

### jQuery 如何获取元素

将一个选择表达式放进构造函数jQuery()中(简写为$())，得到被选中的元素

```javascript
$(document) //选择整个document对象
$('#test') //选择id为test的元素
$('.cls') //选择class为cls的元素
```

### jQuery 的链式操作是怎样的

由于操作dom对象只需要呈现网页上的结果，不需要获得什么返回值
所以jQuery将dom操作返回jQuery对象，这样就可以实现类似如下的链式操作

```javascript
$('#test').find('.children').addClass('mark')
```

### jQuery 如何创建元素

只需要将html元素写法的字符串传入jQuery对象即可

```javascript
$('<div class="div1">this is a div</div>')
$('ul').append('<li>item</li>')
```

### jQuery 如何移动元素

```text
　　.insertAfter()和.after()：在现存元素的外部，从后面插入元素

　　.insertBefore()和.before()：在现存元素的外部，从前面插入元素

　　.appendTo()和.append()：在现存元素的内部，从后面插入元素

　　.prependTo()和.prepend()：在现存元素的内部，从前面插入元素
```

会返回被操作的元素，例如
```javascript
$('div').after($('p')) //返回div元素
$('p').after($('div')) //返回p元素
```

### jQuery 如何修改元素的属性

常见的如

```text
　　.html() 取出或设置html内容

　　.text() 取出或设置text内容

　　.attr() 取出或设置某个属性的值

　　.width() 取出或设置某个元素的宽度

　　.height() 取出或设置某个元素的高度

　　.val() 取出某个表单元素的值
```
