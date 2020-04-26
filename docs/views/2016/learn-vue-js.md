---
title: learn vue.js
date: 2016-08-04 19:40:07
tags:
 - vue
categories:
 - javascript

---

## 安装

```
npm install vue
```

## 条件渲染 v-if
`<p v-if='something'>你好</p>`
用v-if可以根据变量true或者false添加内容，
v-else需要紧跟着v-if或者v-show，建议添加一个v-if并使用"!变量"来实现else的效果

## 列表渲染 v-for
`<li v-for='item in 变量（通常应该含有s）'>`
另有一个特殊变量`$index`为索引，设置序号的时候很实用。
可以使用`$key`来访问json数据的key值，和`value`获得其值。
如果想要生成 1 - n 的 i ，则可以使用`<div v-for='i in 10'></div>`

## 模板渲染
如果需要渲染的内容是整块代码，则可以使用template。
``` 
<template v-if='XXX'>
    <a>fjsdlk</a> 
    <li>jdksl</li>
</template>```
