---
title: Google Analytics功能推介之用户计时
author: 肖庆
layout: post
permalink: /google-analytics/user-timing/
yourls_shorturl:
  - http://t.xiaoq.in/8b
ta-thumbnail:
  - https://xiaoq.in/cdn/2013/12/user-timing.png;
views:
  - 278
ratings_users:
  - 2
ratings_score:
  - 10
ratings_average:
  - 5
categories:
  - Google Analytics
tags:
  - 停留时间
  - 用户计时
  - 转化耗时
---
你在各种标准报告中看到的默认<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%81%9c%e7%95%99%e6%97%b6%e9%97%b4/" title="查看停留时间中的全部文章" target="_blank">停留时间</a></span>或者任何与时间相关的维度，在很多时候基本是没有任何价值的，不管你信不信。停留2分钟或者3分钟，在实质上是差异并不大的，而且我们也往往无从下手，并且很可能会受到各种因素的限制造成统计不准确，误导你对数据的判断。

这里，我们介绍一个更准确的计算<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%81%9c%e7%95%99%e6%97%b6%e9%97%b4/" title="查看停留时间中的全部文章" target="_blank">停留时间</a></span>的方法：使用user timing。它可以更准确地分析用户的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%bd%ac%e5%8c%96%e8%80%97%e6%97%b6/" title="查看转化耗时中的全部文章" target="_blank">转化耗时</a></span>，<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%81%9c%e7%95%99%e6%97%b6%e9%97%b4/" title="查看停留时间中的全部文章" target="_blank">停留时间</a></span>，任意节点的停留时间，任意用户在任意节点的停留时间，任意用户在任意节点任意路径的停留时间，发挥你的想象！

使用<span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>跟踪<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%bd%ac%e5%8c%96%e8%80%97%e6%97%b6/" title="查看转化耗时中的全部文章" target="_blank">转化耗时</a></span>，一般都是去看这几个标准报告：电子商务分析报告中的转化前所耗天数，多渠道转化路径中的转化耗时，归因分析中的模型对比工具。但是，它们提供的只是一个约数，并且针对的都是访客层级的汇总数据。我们无法知晓用户在单次访问中究竟要花多长时间来完成我们的期望转化目标。

而使用Google Analytics跟踪网页停留时间，我们则是去看标准报告中的平均停留时间之类的指标。这个时间的准确性，我想大家都懂的。

我们来想象一些场景，用户从进入网站开始，到最终完成转化的时间间隔；或者用户进入购物车页面，再到完成订单的时间间隔，当然使用下面的方法，你还能定义任意区间的时间范围。这些，对于营销人员的意义，绝对比上面那些平均数或者不那么真实的数据更有价值，对于我们优化网站流程，进而提高转化率，也是非常有帮助的。

<img class="alignnone  wp-image-1499" style="line-height: 1.5em;" alt="user timing" src="https://xiaoq.in/cdn/2013/12/user-timing.png" width="600" />

<a title="User Timing" href="https://developers.google.com/analytics/devguides/collection/gajs/gaTrackingTiming" target="_blank">User Timing</a>，它的时间刻度是秒，并且比事件跟踪那些还多出几个参数，数据展现形式也多样化，分层图表类似于事件跟踪，还多出一个分布标签，可以查看各个时间段范围的用户所占比例，并且还有地理分布图，次级维度和高级细分等功能也同样支持。完整的代码参数配置如下：

<pre>_gaq.push([‘_trackTiming’, category, variable, time, opt_label, opt_sample]);</pre>

其中，category是指计时类别；variable是指计时变量；time是指具体的时间，单位为秒；opt\_label是指计时标签；opt\_sampleRate是抽样比例（<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%94%a8%e6%88%b7%e8%ae%a1%e6%97%b6/" title="查看用户计时中的全部文章" target="_blank">用户计时</a></span>样本），取值范围是1到100。其中的time我们一般通过js去定义，根据触发条件记录下各个关键时间点，然后再进行减法运算，即可知道这个流程所耗的时间。

<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%94%a8%e6%88%b7%e8%ae%a1%e6%97%b6/" title="查看用户计时中的全部文章" target="_blank">用户计时</a></span>的最主要应用就是对关键访问流程的计时，另外还可以用来跟踪用户的停留时间（单页面网站特别管用），用户在网站的终身停留时间或者单个访问期间的停留时间。再结合自定义变量或自定义维度功能，将这些作为次级维度或细分项，可以实现更细致的用户价值研究。