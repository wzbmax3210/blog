---
title: "JS 函数的执行时机"
date: 2019-12-02T14:12:31+08:00
draft: false
---

```javascript
let i = 0
for(i = 0; i<6; i++){
  setTimeout(()=>{
    console.log(i)
  },0)
}
```

> 以上代码的执行结果是什么？
> 
> 答案是6个6，而不是直觉上的0,1,2,3,4,5

由于JavaScript是单线程，settimeout属异步任务，要在同步任务执行完后才去执行，所以先执行for循环

而执行完以后i已经变成6，所以在最后执行settimeout时会答应6个6

在ES6中如果我们写成
```javascript
for(let i = 0; i<6; i++){
  setTimeout(()=>{
    console.log(i)
  },0)
}
```
则会打印出0,1,2,3,4,5

因为在let i = 0初始化写入for循环时，JavaScript会在每次循环时多创建一个临时的i，属于特别处理

我们还可以写成这样
```javascript
let i = 0
for(i = 0; i<6; i++){
  (function(i) {
    setTimeout(()=>{
      console.log(i)
    },0)
  })(i)
}
```
同样打印0,1,2,3,4,5
这里为每个回调函数构建单独的闭包作用域，这样返回的六个函数都有自己的独立闭包环境