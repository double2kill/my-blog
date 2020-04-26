---
title: knowJs
date: 2017-07-14 18:06:43
tags:
 - book
categories:
 - javascript
---

# 《你不知道的JS》的笔记

## 第一章 理解作用域

如`a = b`

LHS：就是指`a`(等号左边的部分)，简单来说就是，"a是什么东西，我要给你赋值了"。

RHS：就是指`b`(等号右边的部分)，"b的值是多少，我需要知道你的值"

LHS需要知道这个变量是否被申明，RHS需要这道这个变量的值，因此都需要找到它们。那么就需要作用域了。

如果在本级作用域没有找到这个变量，就去它的父级去找变量在哪或者是什么。这里可能会出现2种典型的情况。

1. 在场有很多相同的变量如`a`,那么就找离他最近的。（PS：最近的是最难确定是啥）

2. 一直往上都没有找到，它有可能在别的旁系兄弟那里，但是直系的作用域没有找到，就是认为没有。

特殊：不成功的LHS会在全局自动创建一个，不成功的RHS会抛出异常。如：

``` JavaScript
function foo(a){
  b = a;
}
foo(2);
console.log(b);  // b equals 2
```

``` JavaScript
function foo(a){
  console.log(a+b); // 在这里抛出异常
  b = a;
}
foo(2);
console.log("helloWorld");  // 这句不执行
```

<!-- more -->

## 第二章 词法作用域

### eval 欺骗

``` JavaScript
function foo(str, a) {
  eval( str ); //欺骗
  console.log(a, b);
}

var b = 2;

foo( "var b = 3;", 1); // 1, 3
```

### with 欺骗
``` JavaScript
function foo(obj ){
  with(obj){
    a = 2;
  }
}

var o1 = {
  a: 3
}

var o2 = {
  b: 3
}

foo(o1);
console.log( o1.a ); // 2

foo(o2);
console.log( o2.a ); // undefined
console.log( a ); // 2 —— 泄露到全局变量去了。
```

### 理解一下 IIFE
``` JavaScript
var a=(function(a){
  console.log(a); // undefined
  return 1;
})(a);

console.log(a); // 1
```

### let
let 将作用域定位为块级作用域(if/for产生的`{}`)，默认情况下函数的作用域为函数的作用域(function产生的`{}`)

``` JavaScript
var foo = true;
if (foo) {
var bar = foo * 2;
console.log( bar ); // bar = 2
} 
console.log( bar ); // 糟糕，bar = 2
```

``` JavaScript
var foo = true;
if (foo) {
let bar = foo * 2; // 将这个var改成let
console.log( bar ); // bar = 2
} 
console.log( bar ); // bar is not defined
```