---
title: 相关说明
author: ''
date: '2022-01-18'
slug: ''
categories: []
tags: []
description: 建站相关的一些个人经验。
---

_推荐阅读_：[用 R 语言的 blogdown+hugo+netlify+github 建博客](https://cosx.org/2018/01/build-blog-with-blogdown-hugo-netlify-github/)

> **工具**：   
> 1.[R blogdown](https://bookdown.org/yihui/blogdown/)   
> 2.[hugo](https://gohugo.io/)   
> 3.[netlify](https://www.netlify.com/)   
> 4.[github](https://github.com/)    

> **主题**：   
> [hugo-prose](https://github.com/yihui/hugo-prose)   

## 如何插入图片

RStudio界面最上边，help的下面，有一个Addins（意为插件）按钮，Insert Image即可。

_示例：_

<img src="images/峨眉日出.JPG" alt="2021年5月2日峨眉山的日出" width="50%" height="50%"/>

## 如何插入音频

代码如下:
```
<audio id="audio" 
       controls="" 
       preload="none">
      <source id="mp3" src="https://music.163.com/song/media/outer/url?id=472045266.mp3">
</audio>
```

如果属性中添加了autoplay="true"，顾名思义，自动播放。

_示例：_

<audio id="audio" 
       controls="" 
       preload="none">
      <source id="mp3" src="https://music.163.com/song/media/outer/url?id=472045266.mp3">

## 如何插入视频

代码如下：
```
<iframe 
  src="//player.bilibili.com/player.html?aid=21202933&bvid=BV1TW411371E&cid=34820238&page=1&high_quality=1&danmaku=0"
  width="100%" height="475"
  scrolling="no" 
  border="0" 
  frameborder="no"
  framespacing="0" 
  allowfullscreen="true"
> </iframe>
```

\<iframe>\</iframe>为框架，表示引用另一个页面。

src为地址，获取bilibili视频地址只需点击分享，再点击“嵌入代码”，然后粘贴即可。  

需要注意的是，复制好的地址只到"&page=1"处，如果想默认高画质，就要加上"&high_quality=1"，如要默认隐藏弹幕，则要加"&danmaku=0"。  

其余代码为插入视频时的属性，width="100%"表示宽度占页面的100%，height="auto"表示自行调节高度，详请自行查阅资料。

_示例：_
<iframe 
  src="//player.bilibili.com/player.html?aid=883818925&bvid=BV1ZK4y1s7ir&cid=211762878&page=1&high_quality=1&danmaku=0"
  width="100%" height="475"
  scrolling="no" 
  border="0" 
  frameborder="no"
  framespacing="0" 
  allowfullscreen="true"
> </iframe>

