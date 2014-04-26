---
title: 通过自定义变量扩展谷歌分析测量平台（三篇连载之三）
author: 54jack
layout: post
permalink: /google-analytics/extending-google-analytics-measurement-part-3/
sina_t:
  - 'true'
views:
  - 906
  - 906
qq_t:
  - 'true'
duoshuo_thread_id:
  - 511894
yourls_shorturl:
  - http://t.xiaoq.in/42
ta-thumbnail:
  - NoMediaFound
categories:
  - Google Analytics
tags:
  - 内容语言
  - 自定义变量
  - 语言识别
  - 页面级自定义变量
---
通过<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>扩展<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="谷歌分析" target="_blank">谷歌分析</a></span>测量平台系列文章的第三篇，由<span class='wp_keywordlink'><a href="http://www.yeezhe.com/" title="译者" target="_blank">译者</a></span><span class='wp_keywordlink'><a href="http://blog.xiaoq.in/" title="肖庆" target="_blank">肖庆</a></span>原创翻译，本文讲述了如何应用<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e9%a1%b5%e9%9d%a2%e7%ba%a7%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看页面级自定义变量中的全部文章" target="_blank">页面级自定义变量</a></span>，如果你的网站有多语种，那么通过使用<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e9%a1%b5%e9%9d%a2%e7%ba%a7%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看页面级自定义变量中的全部文章" target="_blank">页面级自定义变量</a></span>可以很好地区分不同语言访问者的不同偏好，从而针对性地调整SEO策略和广告计划或者制作更具针对性的着陆页面。

*[Custom Variables][1] allow website owners to extend <span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>’ measurement capabilities and track information that is meaningful to them. In this series of three articles, [Barbara Pezzi][2], Director of Analytics and Search Optimisation for [Fairmont Raffles Hotels International][3], shares how she makes use of custom variables to better understand how to better engage with her customers. You can familiarise yourself with custom variables in [Part 1][4] and [Part 2][5] of this series. – Ed.*

<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>允许网站所有者扩展<a title="谷歌分析" href="http://g.xiaoq.in/" target="_blank">谷歌分析</a>的测量能力并且跟踪对其有意义的信息。在这个三篇连载的系列文章中，[Fairmont Raffles Hotels International][3]的分析总监兼搜索优化师[Barbara Pezzi][2]与我们分享了她如何利用<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>来了解如何更积极地与抓牢其客户。你可以在本系列的第一篇和第二篇中熟悉自定义变量。

Our hotels are located all over the world. As a result, our website visitors are just as geographically diverse. We are planning to expand our language offerings this year and want to understand how each language we currently offer is performing and which languages we should prioritise for.

我们的酒店坐落于全球个点。因此，我们网站的访问者具有地理位置差异。我们计划在今年扩展我们的促销语言，并且想了解目前每种语言的表现如何以及我们应该优先推广哪些语言。

On the Swissotel site we offer content in English, German, Russian, Spanish, French, Arabic and Chinese. We don’t have separate websites for each language and, in some cases, only part of the content is translated. For example, we only provide Chinese translations for content related to our hotels in China. Furthermore, the checkout pages are only available in German and English and located on a separate subdomain. As a result, it is very difficult to assess how our content is being consumed in different languages and the impact of language on our sales.

在Swissotel这个网站我们的内容以英语，德语，俄语，西班牙语，阿拉伯语，以及中文提供。我们并未真的每个语言建立独立的网站，在某些情况下，我们只翻译了部分内容。比如，我们仅仅针对中国的酒店提供繁体中文的内容。而且结算页面只有德语和英语，这些页面位于一个独立的子域名。因此，很难评估我们的内容在不同语言下的表现情况，语言对于销售的影响力。  
**Content Languages – Page level custom variable <span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%86%85%e5%ae%b9%e8%af%ad%e8%a8%80/" title="查看内容语言中的全部文章" target="_blank">内容语言</a></span>-<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e9%a1%b5%e9%9d%a2%e7%ba%a7%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看页面级自定义变量中的全部文章" target="_blank">页面级自定义变量</a></span>**  
To help understand how our foreign-language content is consumed, I decided to use page-level custom variables in Google Analytics. Page-level custom variables apply to a single pageview and allow you to track attributes related to that page such as category, section, author, or, in our case, language. They are very useful for grouping together related pages in our reports.  
为了帮助我们了解外语内容的表现如何，我们决定在谷歌分析中使用页面级自定义变量。页面级自定义变量应用于单个页面浏览，允许我们跟踪与例如分类，部分，作者，或者在我们的案例中的语言等相关的属性。  
The custom variables code used is fairly straightforward. On each page, we set a page-level custom variable called “content_language” and set its value to the language code for the language that the page content is written in.

你可以很直接了当地使用自定义变量代码。子啊每个页面，我们设置一个称为“content_language”的页面级自定义变量，并且把其值设置为相应语言内容的语言代码。

For example, on all our English pages we have:例如，在我们的英语页面我们使用：

\_gaq.push(['\_setCustomVar', 1, 'content_language', 'EN', 3]);

On each of our German pages we have:在每个德语页面，我们使用：

\_gaq.push(['\_setCustomVar', 1, 'content_language', 'DE', 3]);

With these page-level custom variables in place, I can see how popular each language is:  
页面级自定义变量正常运行之后，我可以看到每种语言的流行度：

<div>
  <a href="http://blog.xiaoq.in/cdn/images/2011/06/image03.png" target="_blank"><img style="border: 0px;" src="http://blog.xiaoq.in/cdn/images/2011/06/image03.png" alt="" width="610" height="218" border="0" /></a>
</div>

By creating an advanced segment based on this custom variable, I can now view which keywords are generating traffic for each language and make any necessary tweaks to our SEO and paid search campaigns.

基于这个自定义变量，通过创建高级细分，我现在可以看到哪些关键词给每种语言带来了流量，然后可以做出任何SEO及付费搜索计划的调整。

<div>
  <a href="http://blog.xiaoq.in/cdn/images/2011/06/image02.png" target="_blank"><img style="border: 0px;" src="http://blog.xiaoq.in/cdn/images/2011/06/image02.png" alt="" width="640" height="223" border="0" /></a>
</div>

Additionally, by applying the same advanced segment to our product report, I segment which hotels are being booked in a given language. We use this insight to coordinate our marketing strategies so that we are promoting the right properties in the right languages to the right markets.

另外，通过应用与我们的产品报告相同的高级细分，我可以细分哪些酒店在指定语言中被预定。我使用这个数据透视来调整营销策略，以便我们针对合适的市场用合适的语言促销合适的产品。

<div>
  <a href="http://blog.xiaoq.in/cdn/images/2011/06/image04.png" target="_blank"><img style="border: 0px;" src="http://blog.xiaoq.in/cdn/images/2011/06/image04.png" alt="" width="640" height="273" border="0" /></a>
</div>

We would not be able to gain such valuable insights without custom variables and I am looking forward to the day Google increases the maximum number of custom variables, since I have already used up all my slots.  
如果没有自定义变量，我们将无法获得如此宝贵的数据透视，我期待谷歌增加自定义变量的最大数量这一天的早日到来。  
That brings our series on custom variables to an end – for now. I hope that these posts have inspired you to take a closer look at your site, identify dimensions that are truly unique and important to your business, and adopt custom variables to measure them.  
我们的自定义变量系列到此结束了。我希望这三篇文章给予你一些启发，让你们对网站做更深入的观察，识别真正独特且对公司重要的维度，然后采用自定义变量来测量它们。  
Posted by [Barbara Pezzi][2], Director of Analytics and Search Optimisation, [Fairmont Raffles Hotels International][3]

[Fairmont Raffles Hotels International][3]分析总监兼搜索优化师[Barbara Pezzi][2]发表

 [1]: http://code.google.com/apis/analytics/docs/tracking/gaTrackingCustomVariables.html
 [2]: http://www.linkedin.com/in/barbarapezzi
 [3]: http://www.frhi.com/
 [4]: http://conversionroom-japac.blogspot.com/2011/04/extending-google-analytics-measurement.html
 [5]: http://conversionroom-japac.blogspot.com/2011/04/extending-google-analytics-measurement_26.html