---
title: 点击次数、访问次数、访问者人数、浏览量和唯一身份浏览量有何区别？
author: 肖庆
layout: post
permalink: /google-analytics/the-difference-between-clicks-visits-visitors-pageviews-and-unique-pageviews/
sina_t:
  - 'true'
ratings_users:
  - 1
ratings_score:
  - 5
ratings_average:
  - 5
views:
  - 792
yourls_shorturl:
  - http://t.xiaoq.in/14
ta-thumbnail:
  - NoMediaFound
categories:
  - Google Analytics
tags:
  - 浏览量和唯一身份浏览量
  - 点击次数
  - 访问次数
  - 访问者人数
---
本文转载自<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>帮助中心：<a title="点击次数、访问次数、访问者人数、浏览量和唯一身份浏览量有何区别？" href="http://support.google.com/analytics/bin/answer.py?hl=zh-Hans&cbrank=3&hlrm=en&cbid=1cu4lnumvkl0y&ctx=cb&answer=1257084&src=cb" target="_blank">点击次数、访问次数、访问者人数、浏览量和唯一身份浏览量有何区别？</a>

<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%82%b9%e5%87%bb%e6%ac%a1%e6%95%b0/" title="查看点击次数中的全部文章" target="_blank">点击次数</a></span>、<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%ae%bf%e9%97%ae%e6%ac%a1%e6%95%b0/" title="查看访问次数中的全部文章" target="_blank">访问次数</a></span>、<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%ae%bf%e9%97%ae%e8%80%85%e4%ba%ba%e6%95%b0/" title="查看访问者人数中的全部文章" target="_blank">访问者人数</a></span>、<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e6%b5%8f%e8%a7%88%e9%87%8f%e5%92%8c%e5%94%af%e4%b8%80%e8%ba%ab%e4%bb%bd%e6%b5%8f%e8%a7%88%e9%87%8f/" title="查看浏览量和唯一身份浏览量中的全部文章" target="_blank">浏览量和唯一身份浏览量</a></span>有何区别？

因为不同的报告中会使用许多类似术语，所以 Google Analytics（分析）帐户中的访问者数据可能很容易让人误解。我们将在下面对一些最容易混淆的术语进行更详细的说明。

“<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%82%b9%e5%87%bb%e6%ac%a1%e6%95%b0/" title="查看点击次数中的全部文章" target="_blank">点击次数</a></span>”与“<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%ae%bf%e9%97%ae%e6%ac%a1%e6%95%b0/" title="查看访问次数中的全部文章" target="_blank">访问次数</a></span>”

“<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%ae%bf%e9%97%ae%e6%ac%a1%e6%95%b0/" title="查看访问次数中的全部文章" target="_blank">访问次数</a></span>”与“<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%ae%bf%e9%97%ae%e8%80%85%e4%ba%ba%e6%95%b0/" title="查看访问者人数中的全部文章" target="_blank">访问者人数</a></span>”

“浏览量”与“唯一身份浏览量”

“点击次数”与“访问次数”

“点击次数”（如在“AdWords 广告系列”报告中）和“访问次数&#8221;（在“访问者”报告中）具有一个显著的不同之处。报告中的“点击次数”列表明您的广告被访问者点击的次数，而“访问次数”表明访问者进行的唯一会话次数。这两个数据彼此不符的原因有多种：

访问者可能多次点击您的广告。如果一个人在同一会话中多次点击一个广告，AdWords 会记录多次点击，而 Google Analytics（分析）会将多次单独的网页浏览识别为一次访问。这是访问者在进行比较购物过程中的常见行为。

用户可能会先点击某个广告，稍后，在另一会话期间通过书签直接返回此网站。在这种情况下，来自初始访问的引荐信息将被保留，因而就会出现一次点击带来多次访问的现象。

访问者可能点击您的广告，但却没有让网页完全载入，而是转到了另一网页或按下了浏览器的“停止”按钮。在这种情况下，Google Analytics（分析）跟踪代码将无法执行，也无法将跟踪数据发送到 Google 服务器；但 AdWords 仍然会记录一次点击。

为确保更准确的结算，<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-adwords/" title="Google Adwords" target="_blank">Google Adwords</a></span> 会自动从报告中滤除无效点击。但是，Google Analytics（分析）会将这些点击报告为对您网站的访问，以显示全部流量数据。

“访问次数”与“<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%ae%bf%e9%97%ae%e8%80%85%e4%ba%ba%e6%95%b0/" title="查看访问者人数中的全部文章" target="_blank">访问者人数</a></span>”

Google Analytics（分析）对帐户中的“访问次数”和“访问者人数”均进行统计。“访问次数”表示您网站的所有访问者发起的具体会话次数。如果某用户在您网站上处于非活动状态的时间达到或超过 30 分钟，那么任何进一步的活动都会被归入新会话。如果用户在离开您网站后 30 分钟内返回，则之后的活动仍将被计为初始会话的一部分。

系统会将用户在任何给定日期范围内发起的初次会话视为一次新的“访问”，并将该用户视为一位新的“访问者”。同一用户在选定时间段内的所有后续会话都会被算作另一次“访问”，但该用户不会被视作另一个“访问者”。

“浏览量”与“唯一身份浏览量”

“浏览量”定义为对 Google Analytics（分析）跟踪代码正在跟踪的网站网页的一次浏览。如果访问者到达此页后点击重新载入，会被算做另一次浏览。如果用户浏览到其他网页后返回原始网页，也会被记录为另一次浏览。

“唯一身份浏览量”（如“内容概览”报告中所示）会汇总由同一用户在同一会话期间生成的浏览量。“唯一身份浏览量”表示该页被浏览（一次或多次）期间的会话次数。