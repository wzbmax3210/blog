---
title: "JS语法"
date: 2019-10-29T15:39:33+08:00
draft: false
---

### 表达式与语句

#### 表达式
- 1+2 表达式的值为3
- add(1,2)表达式的值为函数的返回值
- console.log表达式的值为函数本身
- console.log(1)表达式的值为undefined

#### 语句
var a = 1 是一个语句

> JS语法中大小写是敏感的
>
> 大部分空格没有实际意义

### 标识符
第一个字符可以是Unicode字母或$或_或中文接上述字符或数字，例如

- var _ = 1
- var $ = 2
- var 你好 = 'hello' 
- var $abc123

### if...else
```javascript
if (表达式) {
  语句
} else if (表达式) {
  语句
} else {
  语句
}
```

> {}在语句只有一句的时候可以省略，但是不建议这样做，使用最没有歧义的写法是程序员的戒律

### while for 循环语句
```javascript
while (表达式) {
  语句
}
``` 

1. 判断表达式的真假
2. 当表达式为真时执行语句，执行完再判断表示式真假
3. 表达式为假跳出循环执行后面的语句

```javascript
for (语句1;表达式2;语句3) {
  循环体
}
```

1. 执行语句1
2. 判断表达式2
3. 如果为真，执行循环体，然后执行语句3
4. 如果为假，直接跳出循环，执行后面的的语句

### break continue
放在循环体中，break退出所有循环，continue退出当前一次循环

### label
```javascript
foo: {
  console.log(1)
  break foo; //跳出foo代码块
  console.log('这行不会输出')
}
console.log(2)
```
```javascript
{
  foo: 1 //在chrome的控制台中被识别为对象而在firefox中被识别为代码块输出1
}
```
