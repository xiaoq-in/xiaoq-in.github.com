---
title: 通过自定义变量扩展谷歌分析测量平台（三篇连载之二）
author: 54jack
layout: post
permalink: /google-analytics/extending-google-analytics-measurement-part-2/
sina_t:
  - 'true'
views:
  - 820
  - 820
qq_t:
  - 'true'
duoshuo_thread_id:
  - 511893
yourls_shorturl:
  - http://t.xiaoq.in/3g
ta-thumbnail:
  - NoMediaFound
categories:
  - Google Analytics
tags:
  - 会话级自定变量
  - 自定义变量
  - 酒店预定
---
通过<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>扩展<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="谷歌分析" target="_blank">谷歌分析</a></span>测量平台是一个系列文章，有三篇文章，来自谷歌亚太区转化教室官方博客，本文是第二篇（<a title="通过自定义变量扩展谷歌分析测量平台：会话级自定义变量" href="http://conversionroom-japac.blogspot.com/2011/04/extending-google-analytics-measurement_26.html" target="_blank">原文</a>），主要介绍了会话级<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>在<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e9%85%92%e5%ba%97%e9%a2%84%e5%ae%9a/" title="查看酒店预定中的全部文章" target="_blank">酒店预定</a></span>系统中的应用，可以方便地识别用户预定房间的数量，结合地理位置和关键词定位，可以为营销计划及搜索引擎优化提供十分有价值的参考。

*[Custom Variables][1] allow website owners to extend <span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>’ measurement capabilities and track information that is meaningful to them. In this series of three articles, [Barbara Pezzi][2], Director of Analytics and Search Optimisation for [Fairmont Raffles Hotels International][3], shares how she makes use of custom variables to better understand how to better engage with her customers. You can familiarise yourself with custom variables in [part one][4] of this series. – Ed.*

自定义变量允许网站所有者扩展<a title="谷歌分析" href="http://g.xiaoq.in/" target="_blank">谷歌分析</a>的测量能力并且跟踪对其有意义的信息。在这个三篇连载的系列文章中，[Fairmont Raffles Hotels International][3]的分析总监兼搜索优化师[Barbara Pezzi][2]与我们分享了她如何利用自定义变量来了解如何更积极地与抓牢其客户。你可以在本系列的第一篇中熟悉自定义变量。

We recently introduced the option of booking more than one room within a single reservation on our [Fairmont][5] sites. In the past, if a visitor wanted to book three rooms, she would have had to go through the checkout process three times.

我们最近在[Fairmont][5]这个网站引入了在一个单次预定中预定超过一间房。在过去，如果一个访问者想预定3间房，她不得不进行三次结算。

This new option greatly improved the booking experience for our customers. We knew this both intuitively and anecdotally, but we wanted to understand the impact of this change with data. We wanted to understand the popularity of this new feature, which group of hotels benefited the most (e.g. city hotels or resorts), and what the impact has been on our booking rates.

这个新的选项大大提升了我们顾客的预定体验。我们从直觉和轶闻中知道这点，但是我们想了解这种数据变化的影响。我想了解这种新功能的受欢迎度，哪种类型的酒店从这受益最多（城市酒店还是度假村），以及对于预订率的影响。

**Booking types &#8211; Session-level custom variables预定类型-会话级自定义变量**  
We used a [session-level custom variable][6] in Google Analytics to help us answer these questions. Session variables are applied to a single session and help you understand specific behaviours that happen during a particular session or visit.

我们在谷歌分析中使用了会话级自定义变量来帮助我们解答这些问题。会话级变量被应用到每个会话中后可以帮助你了解在某个特定会话或访问中发生的一些特定行为。

As with all custom variables, the code to add to your Google Analytics snippet is very simple: a single function placed in the confirmation page above the _trackPageview() call. We set a custom variable called “booker” each time a booking was made, and its value would be “single” or “multiple” depending on the number of rooms booked.

正如所有的自定义变量一样，添加到谷歌分析代码片段中的代码非常简单：一个单一功能被放在在确认页面中，其位于_trackPageview() 命令之前。每当产生一个预定，我们设置一个称作“预订者”的自定义变量，而其值取决于房间预定的数量，可能会是“一间”或者“多间”。

\_gaq.push(['\_setCustomVar', 1, 'booker', 'single', 2]);

**Analysing the data分析数据**  
Using this custom variable, we could conveniently assess the proportion of sales through our sites for single or multiple rooms.

使用这种自定义变量，我们可以很方便地评估单间或者多间预定所占的比例。

<a href="http://blog.xiaoq.in/cdn/images/2011/06/image08.png" target="_blank"><img style="border: 0px;" src="http://blog.xiaoq.in/cdn/images/2011/06/image08.png" alt="" width="640" height="138" border="0" /></a>

We are also able to assess corresponding traffic and conversion data and even see the increased value of “multiple” booking visits. By creating an advanced segment, I could identify which traffic channels sent me these customers and adjust my marketing activities accordingly.

我们还可以评估相应的流量和转化数据并且甚至能够看到预定访问中“多间”增加的值。通过创建一个高级细分，我可以识别哪个流量渠道带来了这些顾客，从而相应地调整营销活动。

<a href="http://blog.xiaoq.in/cdn/images/2011/06/image09.png" target="_blank"><img style="border: 0px;" src="http://blog.xiaoq.in/cdn/images/2011/06/image09.png" alt="" width="640" height="172" border="0" /></a>

**Identifying relevant keywords识别相关关键词**  
Since organic search traffic from Google is sending us almost 45% of all multiple “bookers”, we decided to drill down deeper and look at the keywords that sent us the traffic. We do a number of things with these keywords: add them to our paid search campaigns, optimise for them in our SEO strategy, and use them as seeds for identifying new keywords. Our multiple room bookers, for example, seem to favour our more traditional hotels and resorts. With this information, we can now look at adding content to our websites that would appeal to this group.  
由于来自谷歌的自然搜索流量带来了几乎45%的多间房“预订者”，我们决定深入挖掘数据，查看带来这些流量的关键词。我对这些关键词做了些事情：把它们添加到我们的付费搜索计划中，利用我们的搜索引擎优化策略中优化它们，使用它们作为作为启发以来识别新的关键词。比如，我们多间房的预订者似乎更喜欢传统的酒店和度假村。有了这些信息，我们可以考虑添加会吸引这类人的内容到我们的网站。  
<a href="http://blog.xiaoq.in/cdn/images/2011/06/image01.png" target="_blank"><img style="border: 0px;" src="http://blog.xiaoq.in/cdn/images/2011/06/image01.png" alt="" border="0" /></a>

I can also easily identify which hotels seem to be more popular with multiple room bookers and advise the property accordingly. They can then use this information to create new offers that might appeal to small groups or families who are likely to book multiple rooms.  
我还可以轻易地识别多房间预定者更喜欢哪些酒店然后相应对给它们推荐。我们还可以使用这些信息创建对可能会预定多间房的小群体或家庭有吸引力的新的促销活动。

**Identifying key markets识别重点市场**  
We were interested in identifying the countries of residence of our customers, and in particular, which locations were more likely to provide us with multiple room bookings.  
我们对于识别客户的居住国感兴趣，特别是哪些位置更可能给我们带来多间房的预定。  
<a href="http://blog.xiaoq.in/cdn/images/2011/06/image00.png" target="_blank"><img style="border: 0px;" src="http://blog.xiaoq.in/cdn/images/2011/06/image00.png" alt="" width="640" height="236" border="0" /></a>

Based on the data, we can now run adjust our marketing campaigns in the best performing markets to include multi-room offers.  
基于这个数据，我们现在可以调整我们的营销计划到表现最好的市场以获得更多多间房的预定。

**Applying our learnings学以致用**  
Session-level custom variables allowed us to effectively analyse a scenario that was unique to our websites and wasn’t immediately available in Google Analytics standard e-commerce reports. We are now in the process of introducing the multi-booking functionality to the [Swissotel][7] websites and feel that we have a head start in ensuring its success thanks to the learnings we gained from our Fairmont sites.  
会话级自定义变量允许我们有效地分析某个对我们网站独特且无法暂时在谷歌分析的标准电子商务报告中无法看到的场景。我们现在正在把多间房预定的功能添加到 [Swissotel][7]这个网站的过程中，由于有了从Fairmont这个网站中学到的一些东西，我们开了一个好头，成功在即。  
Stay tuned for part 3 in this series, in which I will discuss page-level custom variables.

敬请关注本系列的第三篇文章，我将讨论页面级自定义变量。

Posted by [Barbara Pezzi][2], Director of Analytics and Search Optimisation, [Fairmont Raffles Hotels International][3]

[Fairmont Raffles Hotels International][3]分析总监兼搜索优化师[Barbara Pezzi][2]发表

 [1]: http://code.google.com/apis/analytics/docs/tracking/gaTrackingCustomVariables.html
 [2]: http://www.linkedin.com/in/barbarapezzi
 [3]: http://www.frhi.com/
 [4]: http://conversionroom-japac.blogspot.com/2011/04/extending-google-analytics-measurement.html
 [5]: http://www.fairmont.com/
 [6]: http://code.google.com/apis/analytics/docs/tracking/gaTrackingCustomVariables.html#sessionLevel
 [7]: http://www.swissotel.com/EN/Home