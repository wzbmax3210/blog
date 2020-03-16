---
title: "Vue的两个版本"
date: 2020-03-16T11:41:08+08:00
draft: false
---

### Vue的两种版本

Vue官方给我们提供了两种版本来使用:
vue.js 完整版
vue.runtime.js 运行时版(非完整版)

vue.js提供了compiler模板的能力，这样可以将vue内置指令
v-if，v-for等和{{}}模板字符串能编译成浏览器所认识的html，
然后插入页面中渲染。

如：
```javascript
// html
<div id="app"></div>

// main.js
new Vue({
  el: "#app",
  template: `
    <div>{{ value }}</div>
  `,
  data: {
    value: 0
  },
})

//最后得到
<div id="app">0</div>
```

而vue.runtime.js则取消了compiler，体积减少了将近40%.
没有了compiler，vue.runtime.js提供render函数来返回html
如：
```javascript
new Vue({
  el: "#app",
  data: {
    value: 0
  },
  // h相当于提供了createElement的功能
  render(h) {
    h('div', this.value)
  }
})
```

但是在实际开发中我们用webpack的vue-loader将编写的html形式的代码
转换成render函数进行渲染，这样我们就能使用html编写的形式在体积小的运行时版本进行开发
