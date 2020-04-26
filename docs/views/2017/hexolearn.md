---
title: 学习hexo笔记
date: 2017-07-07 9:50:45
tags:
 - hexo 
categories:
 - javascript
---

# 很久不用hexo遇到的问题
## 2017-07-06 19:56:45

从github上面把自己的hexo文件下载回来发现，4000端口打开后无法访问，即白屏情况，其原因一定是装了福昕阅读器，使用`hexo server -p 8080`即可解决



# 配置hexo主题
## 2017-7-7 09:58:57

默认界面不好看，于是打算更换theme，去[**主题官网**](https://hexo.io/themes/)找到next主题好看，在各个技术博客里面看到也是说next主题好看，所以直接选定next主题。

配置方法：
1. 前往[**next版本**](https://github.com/iissnan/hexo-theme-next/releases)，下载最新版本的主题
2. 将其解压至文件目录的`themes`文件夹，并改名为`next`
3. 在配置文件`_config.yml`中，修改`theme`字段为`next`
4. *详细配置方法可以查看[**安装 NexT**](http://theme-next.iissnan.com/getting-started.html)*


# 配置next主题和菜单等
## 2017-7-7 10:40:21

修改next文件夹中的主题设置文件`_config.yml`，修改方法查阅[设置next主题菜单](http://theme-next.iissnan.com/getting-started.html#menu-settings)


# 文本居中引用代码
## 2017-7-7 11:10:04

{% centerquote %}露娜：见过我家那只可爱的宠物吗，它的名字叫大白{% endcenterquote %}

实现的代码如下：

``` markdown
<!-- HTML方式: 直接在 Markdown 文件中编写 HTML 来调用 -->
<!-- 其中 class="blockquote-center" 是必须的 -->
<blockquote class="blockquote-center">露娜：曾经与我的兄长较量过了吗</blockquote>
<!-- 标签 方式，要求版本在0.4.5或以上 -->
{% centerquote %}露娜：别在来不及的时候后悔{% endcenterquote %}
<!-- 标签别名 -->
{% cq %} 露娜：意志很犀利嘛，可惜比不过我的剑刃{% endcq %}
```

# 突破容器宽度限制的图片
## 2017-7-7 11:20:26
![An image](/liuchen-large.jpg)

# 设置阅读全文
## 2017-7-7 11:32:12

建议采用`<!-- more -->`手动截断
<!-- more -->