---
title: 通过自定义变量扩展谷歌分析测量平台（三篇连载之一）
author: 54jack
layout: post
permalink: /google-analytics/extending-google-analytics-measurement/
sina_t:
  - 'true'
views:
  - 1587
  - 1587
qq_t:
  - 'true'
duoshuo_thread_id:
  - 511892
yourls_shorturl:
  - http://t.xiaoq.in/2n
ta-thumbnail:
  - NoMediaFound
categories:
  - Google Analytics
tags:
  - 自定义变量
  - 访问者级自定义变量
  - 谷歌分析
---
*<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>的一个系列文章，共有三部分，分别讲述三个基本<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>（访问者级、会话级、页面级）的不同应用，本文先是总体地简要介绍了自定义变量，然后说明了使用<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%ae%bf%e9%97%ae%e8%80%85%e7%ba%a7%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看访问者级自定义变量中的全部文章" target="_blank">访问者级自定义变量</a></span>的一个实例。下文由<span class='wp_keywordlink'><a href="http://www.yeezhe.com/" title="译者" target="_blank">译者</a></span><span class='wp_keywordlink'><a href="https://xiaoq.in/" title="肖庆" target="_blank">肖庆</a></span>原创翻译自谷歌亚太区转化教室博客，原文在<a title="通过自定义变量扩展谷歌分析测量平台，第一部分" href="http://conversionroom-japac.blogspot.com/2011/04/extending-google-analytics-measurement.html" target="_blank">这里</a>。*

*[Custom Variables][1] allow website owners to extend <span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>’ measurement capabilities and track information that is meaningful to them. In this series of three articles, [Barbara Pezzi][2], Director of Analytics and Search Optimisation for [Fairmont Raffles Hotels International][3], shares how she makes use of custom variables to understand how to engage more effectively with her customers. – Ed.*

自定义变量允许网站所有者扩展<span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="谷歌分析" target="_blank">谷歌分析</a></span>的测量能力并且跟踪对其有意义的信息。在这个三篇连载的系列文章中，[Fairmont Raffles Hotels International][3]的分析总监兼搜索优化师[Barbara Pezzi][2]与我们分享了她如何利用自定义变量来了解如何更积极地与抓牢其客户。

One of the latest features of [Google Analytics][4] that I’m excited about is [Custom Variables][1]. Google Analytics has a very extensive list of default dimensions and metrics, such as time on site and traffic sources, that it tracks for your website. While these dimensions and metrics cover most websites’ needs, every website and business is unique, with its own set of objectives and goals. You might want to track certain visitor segments or user behaviour that is not reflected in the default set of metrics.

令我兴奋的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%b0%b7%e6%ad%8c%e5%88%86%e6%9e%90/" title="查看谷歌分析中的全部文章" target="_blank">谷歌分析</a></span>新功能之一便是自定义变量。<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%b0%b7%e6%ad%8c%e5%88%86%e6%9e%90/" title="查看谷歌分析中的全部文章" target="_blank">谷歌分析</a></span>有很多默认的维度和指标，比如网站停留时间，流量来源等，以用来跟踪网站。尽管这些维度和指标涵括了大部分网站的需求，每个网站和企业却又是独特的，有着他们自己设定的目的和目标。你可能想跟踪不在默认维度中反映的特定访问者群体或者用户的行为。

Custom variables allow you to extend Google Analytics’ default metrics and dimensions to track information that is meaningful to you by labelling interactions with your site at three levels: visitor, session and page. You can then segments and run custom reports based on these variables. You can learn all about the technical implementation of custom variables in the [Google Analytics Code Site][1].

自定义变量在三个级别（访问者、会话、页面）的对你网站的互动进行标记，从而允许你扩展<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%b0%b7%e6%ad%8c%e5%88%86%e6%9e%90/" title="查看谷歌分析中的全部文章" target="_blank">谷歌分析</a></span>的默认维度和指标以跟踪对你有用的信息。然后，你可以基于这些自定义变量细分群体或者运行自定义报告。你可以在谷歌分析编码网站了解所有关于自定义变量的技术应用。

The possibilities are endless with custom variables. You could for example:自定义变量的可能性无穷无尽。比如，你可以：

*   identify segments of visitors based on a specific landing page that they visited基于特定的着陆页面识别细分的访问者
*   identify staff-visits vs non-staff visits识别员工及非员工访问
*   identify and analyse sessions during which a visitor posted a comment on your blog or subscribed to your newsletter识别并分析访问期间访问者在你的博客发表了评论或者订阅了邮件的会话

We use custom variables for a number of purposes on our [Fairmont][5] and [Swissotel][6] websites. Over the next few weeks, I will walk you through three examples, one for each variable type (visitor, session, page).  
我们在[Fairmont][5] 和 [Swissotel][6]这两个网站使用自定义变量做多种用途。在接下来几周，我将分享三个案例，每个自定义变量类型一个（访问者级、会话级、页面级） 。

**Loyalty Members – Visitor-level custom variables忠诚会员-<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%ae%bf%e9%97%ae%e8%80%85%e7%ba%a7%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看访问者级自定义变量中的全部文章" target="_blank">访问者级自定义变量</a></span>**  
A segment of our customers that we focus on because of their value to us are our loyalty program members. When a customer signs up to our [Club Swiss Gold][7] program, they start as a ‘Classic’ member, and then progress to become an ‘Elite’ member.这是我们关注的一个客户细分，因为他们对我们的会员忠诚计划具有很大价值。当客户注册我们的金牌计划，他们成为“经典”会员，然后逐步成为杰出会员。

We want to understand the difference in behaviour and purchase patterns between our Classic and Elite members. Google Analytics can’t easily provide us with that insight by default, but with visit-level custom variables, we can answer this question.我们想了解经典会员和杰出会员在行为和购买方式上的不同。谷歌分享默认不会轻易给我们提供这些视图，但是通过访问级自定义变量，我们可以回答这个问题。

[Visitor-level custom variables][8] allows us to distinguish categories of visitors across multiple sessions. We are essentially bucketing our users into our own custom categories. Visitor-level custom variables are best used for attributes of a visitor, such as their membership level or product preference, that you wish to track over multiple visits.<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%ae%bf%e9%97%ae%e8%80%85%e7%ba%a7%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看访问者级自定义变量中的全部文章" target="_blank">访问者级自定义变量</a></span>允许我们在多个会话间区别不同类别访问者。我们使我们的用户分组到我们自己的自定义分类。访问者级自定义变量十分适合用作给访问者赋值，比如他们的会员级别或者产品偏好，这些你希望跟踪不同访问的信息。

On our Swissotel site, we set the visitor-level custom variable whenever a member logs in by inserting a line of code into our Google Analytics tracking code. The code involved is very simple: a single function placed above the _trackPageview() call on the same page:  
在我们的网站，当会员登录时，我们通过插入一行代码到谷歌分析跟踪码中设置访问者级自定义变量。涉及到的代码很简单：放置在同一页面且位于_trackPageview() 之前的一个简单的函数。  
\_gaq.push(['\_setCustomVar', 1, 'Membership', 'logged\_in\_classic', 1]);

<div>
  <a href="http://cdn.54jack.com/images/2011/06/image05.png" target="_blank"><img style="border: 0px;" src="http://cdn.54jack.com/images/2011/06/image05.png" alt="" width="640" height="88" border="0" /></a>
</div>

We are now able to distinguish between members and non-members as well as membership levels. Within the custom variable report, I can now see at a glance information like site usage, goal conversion data, and ecommerce data, which is broken down by membership levels.  
我们现在可以区别会员和非会员以及不同的会员等级。在自定义变量报告中，我现在可以看到网站使用情况，目标转化数据，电子商务数据等信息，这些数据通过会员级别进行了划分。  
I can use this custom variable to create an advanced segment for additional insights, such as countries of our classic members and conversion rates across countries. We use these insights to identify any potential deficiencies in language coverage or regional product preference.  
我可以使用自定义变量来为额外的透视数据创建高级细分，比如我们经典会员的国家以及不同国家的转化率。我们使用这些透视数据来识别任何在语言覆盖或者区域产品偏好方面的潜在缺陷。

<div>
  <a href="http://cdn.54jack.com/images/2011/06/image06.png" target="_blank"><img style="border: 0px;" src="http://cdn.54jack.com/images/2011/06/image06.png" alt="" width="640" height="281" border="0" /></a>
</div>

Or, we can look at which property classic members book the most and use that insight to create more offers for popular hotels and increase bookings for less popular properties.或者，我们可以查看哪个经典会员预订了最多，并且使用那个透视数据为受欢迎的酒店创建更多促销活动并且增加那些不太受欢迎酒店的预订。

<div>
  <a href="http://cdn.54jack.com/images/2011/06/image07.png" target="_blank"><img style="border: 0px;" src="http://cdn.54jack.com/images/2011/06/image07.png" alt="" width="640" height="270" border="0" /></a>
</div>

We are now in the process of updating our loyalty program, and these insights are invaluable in helping us make improvements based on our customers’ preferences.我们现在在更新我们的忠诚计划的过程中，这些数据对于帮助我们基于客户偏好的改进价值是无法估量的。

Stay tuned for part two of this series, in which I’ll cover how we use session-level custom variables on Fairmont’s sites.敬请关注这个系列的第二部分，在第二部分中我们将讲述在Fairmont的网站我们是如何使用会话级自定义变量的。

Posted by [Barbara Pezzi][2], Director of Analytics and Search Optimisation, [Fairmont Raffles Hotels International][3]

[Fairmont Raffles Hotels International][3]，分析总监兼搜索优化师，[Barbara Pezzi][2]发表

 [1]: http://code.google.com/apis/analytics/docs/tracking/gaTrackingCustomVariables.html
 [2]: http://www.linkedin.com/in/barbarapezzi
 [3]: http://www.frhi.com/
 [4]: http://www.google.com/analytics/
 [5]: http://www.fairmont.com/
 [6]: http://www.swissotel.com/EN/Home
 [7]: http://csg.swissotel.com/index.php
 [8]: http://code.google.com/apis/analytics/docs/tracking/gaTrackingCustomVariables.html#visitorLevel