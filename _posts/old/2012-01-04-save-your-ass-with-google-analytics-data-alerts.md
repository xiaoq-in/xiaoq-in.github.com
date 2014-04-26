---
title: 通过GA自定义提醒摆脱烦扰
author: 肖庆
layout: post
permalink: /google-analytics/save-your-ass-with-google-analytics-data-alerts/
sina_t:
  - 'true'
views:
  - 1561
duoshuo_thread_id:
  - 511939
yourls_shorturl:
  - http://t.xiaoq.in/m
ta-thumbnail:
  - https://xiaoq.in/thumb/cache/2012/1/577-1.jpg;https://xiaoq.in/thumb/cache/2012/1/577-2.png;https://xiaoq.in/thumb/cache/2012/1/577-3.png;https://xiaoq.in/thumb/cache/2012/1/577-4.png;https://xiaoq.in/thumb/cache/2012/1/577-5.png;
categories:
  - Google Analytics
tags:
  - GA
  - 指标
  - 数据专家
  - 智能事件
  - 维度
  - 自定义提醒
---
面对现实吧，我们都有点“懒”。我承认，我并不会每天查看我的网站数据。特别是当我在度假的时候，就更难了。

但是，没关系。尽管我无法每天查看分析数据，我使用<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e6%8f%90%e9%86%92/" title="查看自定义提醒中的全部文章" target="_blank">自定义提醒</a></span>功能来紧密关注我的数据。你正在使用提醒功能吗？

从未使用过<span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>(<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>)<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e6%8f%90%e9%86%92/" title="查看自定义提醒中的全部文章" target="_blank">自定义提醒</a></span>？其实它们非常容易设置。你可以在配置文件设置中找到它们（配置文件-资源-<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e6%8f%90%e9%86%92/" title="查看自定义提醒中的全部文章" target="_blank">自定义提醒</a></span>，或在home的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e6%99%ba%e8%83%bd%e4%ba%8b%e4%bb%b6/" title="查看智能事件中的全部文章" target="_blank">智能事件</a></span>中）。

要设置一个提醒你需要做五件事情：

1. 选择一个需要应用提醒的配置文件【应用到】。  
2. 选择你想跟踪数据的频率（每天，每周或者每个月）【时段】。  
3. 设定你想监控的流量<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%bb%b4%e5%ba%a6/" title="查看维度中的全部文章" target="_blank">维度</a></span>（即，哪组访客，比如来自特定广告系列或地理区域的访客）【应用范围】。  
4. 选择你想跟踪什么<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e6%8c%87%e6%a0%87/" title="查看指标中的全部文章" target="_blank">指标</a></span>（收入，访问，网站停留时间，等等）【出现以下情况时请提醒我】。  
5. 选择提醒的条件，即<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e6%8c%87%e6%a0%87/" title="查看指标中的全部文章" target="_blank">指标</a></span>需要变化多少才激活这个提醒（即，增加，减少，等）【条件】。

[<img title="Google Analytics Alert Settings" src="http://cutroni.com/blog/wp-content/uploads/GoogleAnalyticsAlertSettings.jpg" alt="Google Analytics Alert Settings" width="544" height="405" />][1]

把我的提醒分为两组：一组用来确保我有良好的数据，一组用来测量商业表现。本文处理第一组的情况：保持你的数据处于极佳的状态。

**提醒#1：每日流量下滑10%**

第一个提醒只是为了确保我在收集数据。我注意到，对于我的网站，当以周为单位测量时，我的流量通常不会在某天下滑超过10%。因此，如果我看到流量下滑了10%以上，我知道肯定有事情发生了，我需要做更深入调查。

<div id="attachment_2048">
  <img title="Google Analytics Decrease in Traffic Alert" src="http://cutroni.com/blog/wp-content/uploads/Screen-Shot-2011-12-19-at-2.49.27-PM.png" alt="Google Analytics Decrease in Traffic Alert" width="774" height="343" />10%的流量下滑
</div>

**提醒#2：平线条！即，没数据**

这是一个通用的提醒来确认某个<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e6%8c%87%e6%a0%87/" title="查看指标中的全部文章" target="_blank">指标</a></span>达到0。很多时候，客户尝试在月底分析数据，结果却只看一个数据问题，这种情况经常发生。这通常是因为你不会每日对每个指标进行分析，某些指标以月底为周期进行分析。

但是我不想等到月底，结果却只发现一个问题。

因此，对几乎每个重要的指标，我会创建一个每日提醒，以确保我正在收集数据。下面是一个例子，我创建一个提醒来监控一个事件。

<div id="attachment_2049">
  <img title="A Google Analytics Alert that monitors an Event" src="http://cutroni.com/blog/wp-content/uploads/Screen-Shot-2011-12-19-at-2.52.59-PM.png" alt="A Google Analytics Alert that monitors an Event" width="536" height="341" />监控一个事件的GA提醒
</div>

**提醒#3：每日错误页面**

另外一个我喜欢监测的指标便是错误页面，特定来说是404错误页面。我想知道我的内容是否为我的读者产生了一个错误页面。因此，我创建了一个小提醒，如果错误页面的数量大于0，则会提醒我。

<div id="attachment_2044">
  <a href="http://cutroni.com/blog/wp-content/uploads/Screen-Shot-2011-12-19-at-2.20.23-PM.png"><img title="Google Analytics Daily Error Pages Alert" src="http://cutroni.com/blog/wp-content/uploads/Screen-Shot-2011-12-19-at-2.20.23-PM.png" alt="Google Analytics Daily Error Pages Alert" width="577" height="349" /></a>监控404页面，以及其他网站错误
</div>

很显然，你可以更改这个提醒来监控几乎所有类型的网站错误，这取决于你使用G在跟踪哪些错误。其中的关键便是，你需要能够在<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>报告中识别你的错误页面。

正如你上面看到的，我的错误页面有一个独特的URL（404.html），以及一个查询参数来识别丢失的页面。你可能需要使用虚拟浏览或者事件来跟踪你的错误页面。

**提醒#4：非域名浏览，也称抄袭提醒**

GA中的主机名报告是一个非常好用的小报告。它显示了访客浏览器的网址地址栏中的主机名。在很多情况下，人们未经允许抄袭（借用）我的内容。他们仅仅抄袭我的源文件，然后发布到他们自己的域名

我知道，很流行。

这个提醒会自动让我知道是否我的账号从不是我的域名的其他域名获得数据。

<div id="attachment_2043">
  <a href="http://cutroni.com/blog/wp-content/uploads/Screen-Shot-2011-12-19-at-2.20.41-PM.png"><img title="Google Analytics Hostname Alert" src="http://cutroni.com/blog/wp-content/uploads/Screen-Shot-2011-12-19-at-2.20.41-PM.png" alt="Google Analytics Hostname Alert" width="587" height="436" /></a>这个“抄袭”提醒会让你知道是否有人在剽窃你的内容。
</div>

在一些情况下，这个提醒却是检测到一些好东西！我时常会看到主机名为：translate.googleusercontent.com，这是因为用户在使用Google翻译来翻译我网站的内容。

## 来自你<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e6%95%b0%e6%8d%ae%e4%b8%93%e5%ae%b6/" title="查看数据专家中的全部文章" target="_blank">数据专家</a></span>的提醒

所有这些提醒都会有所帮助。但是，你仍然会在数据中发现不精确的地方。上面的思想是想使这种不精确尽量减少到最低。如果你尝试消除所有错误，那么你将无法做其他任何事情了。这是几乎不可能的。尽力为我。

如果你却是有一些数据问题，而且你却是会有，你将不得不在做分析的时候花些时间解决它们。

<span class='wp_keywordlink'><a href="http://www.yeezhe.com/" title="译者" target="_blank">译者</a></span><span class='wp_keywordlink'><a href="https://xiaoq.in/" title="肖庆" target="_blank">肖庆</a></span>原创翻译自：<a title="通过GA自定义提醒摆脱烦扰" href="http://cutroni.com/blog/2012/01/04/save-your-ass-with-google-analytics-data-alerts/" target="_blank">http://cutroni.com/blog/2012/01/04/save-your-ass-with-google-analytics-data-alerts/</a>

 [1]: http://cutroni.com/blog/wp-content/uploads/GoogleAnalyticsAlertSettings.jpg