---
title: "CSS动画"
date: 2019-10-28T17:47:02+08:00
draft: false
---

### 浏览器渲染过程
在说CSS动画之前我们先来看下浏览器的简单渲染过程

1. 根据HTML构建HTML树(DOM)
2. 根据CSS构建CSS树(CSSOM)
3. 两棵树合并成Render Tree
![render tree](/images/css-animation/render-tree.jpg)
4. 然后进行Layout布局(文档流、盒模型、计算大小与位置)
5. Paint绘制(边框颜色、文字颜色、阴影等)
6. Composite合成(根据层叠关系展示画面)

### JS更新样式
一般来说我们用JS来更新样式，有三种更新方式
![render tree](/images/css-animation/update-styles.jpg)
如图所示
1. 整个渲染过程要重新走一遍，如`div.remove()`
2. 跳过layout过程，一般是修改颜色的操作。
3. 跳过layout和paint过程，比如我们要提到的css动画中改变transform

> 每个属性的修改触发的流程都不一样，具体可以查看[Css Triggers](https://csstriggers.com/)

***

### CSS动画
介绍CSS动画前先介绍transform

主要的作用是允许我们对元素进行旋转、缩放、移动或倾斜

transform 有四个常用功能

1. 位移translate
2. 缩放scale
3. 旋转rotate
4. 倾斜skew

具体用法查看[transform MDN](https://developer.mozilla.org/zh-CN/docs/Web/CSS/transform)

> 需要注意的是inline元素不支持transform，所以我们需要先将元素变成block元素

一般CSS动画中有两种做法

### transition(过渡)
作用主要是补充中间帧，用法是transition:属性名 时长 过渡方式 延迟

- 属性名指规定设置过渡效果的css属性名称，如width，height(值为none时，没有属性会获得过渡效果，值为all时，所有属性都将获得过渡效果，多个属性用逗号隔开)
- 时长指过渡完所需要的时间，如.5s，200ms
- 过渡方式指类似动画效果，如linear线性过渡
- 延迟指多少秒后触发动画，如.5s，200ms

具体用法查看[transition MDN](https://developer.mozilla.org/zh-CN/docs/Web/CSS/transform)

> 不是所有属性都能过渡的，如display从block到none是没有过渡效果的。

下面是用transform + transition制作的[红心动画hover效果](http://baldjs.top/future/css/heartbeat/transition.html)

### animation + keyframes
keyframes主要两种写法

```css
@keyframes animationName {
    from {
        transform: translateX(0%);
    }

    to {
            transform: translateX(100%);
    }
}
```

```css
@keyframes animationName {
    0% {
        transform: translateX(0%);
    }

    50% {
        transform: translateX(50%);
    }

    100% {
            transform: translateX(100%);
    }
}
```

具体用法查看[@keyframes MDN](https://developer.mozilla.org/zh-CN/docs/Web/CSS/@keyframes)

animation语法：

animation:动画名(@keyframes中定义)|过渡方式|延迟|次数|方向|填充模式|是否暂停

- 过渡方式，延迟同transition
- 次数指动画的循环次数(infinite无限循环)
- 方向有reverse(从终点往起点)|alternate(从起点到终点往返)|alternate-reverse(从终点到起点往返)
- 填充模式none|forwards(在终点停止)
- 是否暂停paused|running

具体用法查看[animation MDN](https://developer.mozilla.org/zh-CN/docs/Web/CSS/animation)

下面是用@keyframes + animation制作的[红心动画效果](http://baldjs.top/future/css/heartbeat/animation.html)
