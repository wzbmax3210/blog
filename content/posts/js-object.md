---
title: "Js Object"
date: 2019-11-14T09:13:14+08:00
draft: false
---

### 声明对象的两种用法

1.简写写法
```javascript
let obj = {a: 1}
```

2.正式写法
```javascript
let obj = new Object({a: 1})
```

### 如何删除对象的属性

```javascript
delete obj.xxx
delete obj['xxx']
```

> 将属性值设为undefined并不等同于删除属性
>
> 用`xxx in obj`来判断obj是否含xxx属性，包括原形属性
> 也可以用`obj.hasOwnProperty`来判断，只判断非原型属性

### 如何查看对象的属性

1. 查看自身所有的属性用`Object.keys(obj)`，它将返回对象自身属性名的数组

2. 查看自身+公有属性（prototype）用`console.dir(obj)`

### 如何修改或增加对象的属性

1. 直接赋值
```javascript
let obj = {name: 'abc'}
obj.name = 'xxx' // name是字符串
obj['name'] = 'xxx' //name是字符串
obj['na' + 'me'] = 'xxx'

let key = 'name'
obj[key] = 'xxx' //使用变量属性时要用中括号的写法
```

2. 批量赋值
使用`Object.assign(obj, {a: 1, b: 2})`
