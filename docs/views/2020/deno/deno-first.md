---
title: deno-初探
date:  2020-06-01 16:48:55
tags:
 - deno
categories:
 - javascript
---

最近 deno 已经在社区里沸沸扬扬了，是时候开始跑一个 deno 的 demo 来了解 deno 到底能做什么
<!-- more -->

## 安装
根据[官网](https://deno.land/)的例子

```bash
Shell (Mac, Linux):
curl -fsSL https://deno.land/x/install/install.sh | sh
```

## deno run

可以是远程的文件，也可以和以前一样是本地的文件

`deno run https://deno.land/std/examples/welcome.ts`


## deno 特性

* 自带支持 ts
* 可以 run 远程文件或者远程版本库
* 是安全的，默认不支持 net/文件操作，需要显式的开启
* 自带支持 ES modules，而不支持 require 形式
* 支持 promise，async/await

## 权限
代码可能来自网络上的库，所以需要对网络权限和文件权限进行一些限制。从使用的角度来说就是显式的制定它有什么权限。

### 文件权限
* `deno run --allow-read=/usr ……`
* `deno run --allow-write ……`

### 网络权限
* `deno run --allow-net=github.com,deno.land fetch.ts`


## deno 的评价

* 每一点看过去好像没有什么东西，但是这个代表着新时代对 JS 做服务端的需求，也可以是一种语法糖，像 es6 一样，不断增加语法糖来减少编写次数以及避免编写错误。
* deno目前阶段还是偏向服务端，前端的一些工具库都不适用，不知道是什么原因，感觉回到了 14 年学习 node 时候的感觉