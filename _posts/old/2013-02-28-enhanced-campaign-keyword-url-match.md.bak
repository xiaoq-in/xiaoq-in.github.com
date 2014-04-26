---
title: 增强型广告系列：关键词URL的设备匹配
author: 肖庆
layout: post
permalink: /google-adwords/enhanced-campaign-keyword-url-match/
ratings_users:
  - 0
ratings_score:
  - 0
ratings_average:
  - 0
views:
  - 2465
yourls_shorturl:
  - http://t.xiaoq.in/y
ta-thumbnail:
  - NoMediaFound
categories:
  - Google AdWords
tags:
  - 增强型广告系列
---
我们知道，在<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%a2%9e%e5%bc%ba%e5%9e%8b%e5%b9%bf%e5%91%8a%e7%b3%bb%e5%88%97/" title="查看增强型广告系列中的全部文章" target="_blank">增强型广告系列</a></span>中，我们无法排除PC的广告投放，可以通过设置低出价的方式排除移动广告的展示。对于拥有移动网站的广告主来说，这无疑带来了很多便利，因为我们可以在一个广告系列中就能跨屏进行广告投放，只需要设置不同的出价调整比例即可。

那么，假设我们在一个广告系列中同时投放PC和mobile的广告，给广告主带来的一个不利是，我们要么就只能在广告层级通过选择“设备偏好设置”中的“移动设备”来设置单独的移动设备URL，要么如果想设置关键词层级的URL，就无法根据设备设置不同的URL了。有些广告主可能会添加关键词层级的URL进行广告跟踪标识或做其他用途，这种情况下，就很难两全了。然而PC端的用户浏览习惯和移动设备的用户浏览习惯，很多广告主也分别建立了不同的针对性网站，如果想在关键词层次设置URL，同时该URL也是针对相应设备的，我们难道真的就素手无策么？

虽然不能直接设置，但是通过以下2种方法，我们可以很轻松地解决这个问题：

在网站的服务器端设置自动跳转，通过服务器设置或程序判断用户的访问设备，然后分别跳转到相对应的页面。这种做法，可以尝试用不同设备去访问下凤凰网等大型门户网站。对于一些网站，比如爱房网，他们还会设置一个中转的移动应用下载页面，用户可以选择下载或直接跳过。这对于app的推广是不错的。

另外一种方法就是通过AdWords的一个跟踪标记：<a title="Value Track" href="http://support.google.com/adwords/answer/2375447" target="_blank">Value Track</a>，其中有一个{device}的参数，通过这个参数，你可以对PC，平板电脑和移动设备分别设置不同的URL。比如：http://xiaoq.in/c/\*\\*\*；http://xiaoq.in/t/\*\*\*；http://xiaoq.in/m/\***。这种方法的前提是你在网站制作初期就做了一个类似的网站结构规划，或者你的网站可以根据这个参数做自动跳转。

这种方法还有一个参数也是可以利用的，那就是：{ifmobile:[value]}。不过，由于它只有if没有else，因此还需要做一个变通，即这样处理：http://xiaoq.in/{ifmobile:m/#}c/。当用户为PC访问时，URL是：http://xiaoq.in/c/，当用户为移动设备访问时，URL是：http://xiaoq.in/m/#c（#c是页面内一个不存在的锚文本标记）

当然，如果你只需进行简单的关键词跟踪，那么不妨尝试track value的另外一个参数，将ad copy中的URL写成：http://xiaoq.in/?keyword={keyword}&{matchtype}，不过，这种URL对于竞争对手也是可见的，有可能会让他们知道你的投放关键词及对应匹配方式。

以上这些小技巧，希望对你有所帮助，不过一定要记得检查跳转之后的URL是否正常，特别是如果你还使用了第三方跟踪工具或同时开启了“自动标记”，一不小心都404或503了，那就得不偿失了。

本文参考自：http://www.ppc-epiphany.com/2013/02/13/using-mobile-keyword-urls-in-enhanced-campaigns/。