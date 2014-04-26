---
title: GA高级细分的升级与革新
author: 肖庆
layout: post
permalink: /google-analytics/google-analytics-updated-revolutionized-segmentation/
yourls_shorturl:
  - http://t.xiaoq.in/7t
views:
  - 3800
ratings_users:
  - 1
ratings_score:
  - 5
ratings_average:
  - 5
ta-thumbnail:
  - https://xiaoq.in/thumb/cache/2013/9/1300-1.png;https://xiaoq.in/thumb/cache/2013/9/1300-2.png;https://xiaoq.in/thumb/cache/2013/9/1300-3.png;
categories:
  - Google Analytics
tags:
  - 序列分析
  - 访客细分
  - 队列分析
  - 高级细分
---
<span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>这个升级版的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e9%ab%98%e7%ba%a7%e7%bb%86%e5%88%86/" title="查看高级细分中的全部文章" target="_blank">高级细分</a></span>，主要革新特色是可以进行访客级别的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e9%ab%98%e7%ba%a7%e7%bb%86%e5%88%86/" title="查看高级细分中的全部文章" target="_blank">高级细分</a></span>，因此也可以很好的支持<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e9%98%9f%e5%88%97%e5%88%86%e6%9e%90/" title="查看队列分析中的全部文章" target="_blank">队列分析</a></span>，同时支持按照序列进行细分，当然如此前一样可以进行个性化的定制组合。GA的高级细分在大概两个月前就开始了这个升级（目前还在小范围测试中，几周内将公测），作为GA的Analytics Advocate（某种程度类似于产品经理）Justin曾经写过<a href="http://cutroni.com/blog/2013/07/16/google-analytics-segmentation/" target="_blank">一篇博客</a>进行了介绍，刚看了Avinash的<a href="http://www.kaushik.net/avinash/google-analytics-visitor-segmentation-users-sequences-cohorts/" target="_blank">博客</a>，也对这个功能大表赞许。的确如此！

<img class="alignnone size-full wp-image-1303" alt="new_google_analytics_segmentation_options" src="http://cdn.xiaoq.in/2013/09/new_google_analytics_segmentation_options.png" width="625" height="557" />

在此之前，GA的高级细分只支持visits（访问）和hits层级的数据细分。这在一定程度上会造成分析出来的数据与实际业务需求产生偏差。比如，下面两个图，需要细分出500元客单价的用户：如果按照用户层级进行细分的话，可以出来2个访客；而如果按照访问进行细分，由于A用户经历了2次访问，且每次访问均低于500，因此只能出来1次访问。显然，第一个更符合我们的商业需求。我们更关注一个用户的LTV（客户终身价值），而且由于我们身处多屏时代，用户使用不同浏览器（设备）或者经历较长周期完成一个转化或分开多个订单进行订购的情况也会越来越多。

<img class="alignnone size-full wp-image-1301" alt="1A_UserSegment" src="http://cdn.xiaoq.in/2013/09/1A_UserSegment.png" width="620" height="228" />

<p style="text-align: center;">
  图一（符合要求的有2个访客）
</p>

<img class="alignnone size-full wp-image-1302" alt="1B_VisitSegment" src="http://cdn.xiaoq.in/2013/09/1B_VisitSegment.png" width="619" height="214" />

<p style="text-align: center;">
  图二（符合要求的有1个访问）
</p>

<p style="text-align: left;">
  以上是关于升级版的高级细分的基本功能，当然我们可以更深入挖掘利用这个功能，其中最常使用的就是<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e9%98%9f%e5%88%97%e5%88%86%e6%9e%90/" title="查看队列分析中的全部文章" target="_blank">队列分析</a></span>。记得在早些时候也有探讨过如何通过自定义变量的访客级存储变量方式来间接实现<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e9%98%9f%e5%88%97%e5%88%86%e6%9e%90/" title="查看队列分析中的全部文章" target="_blank">队列分析</a></span>的功能。现在，不用那么麻烦，只需要使用高级细分即可。比如你想细分出在10.1-10.7之间通过百度网盟注册成为会员并订购价值100元以上产品的访客，与其他数据类似数据进行对比，从而分析出该段时间该广告渠道的广告效果，通过高级细分进行筛选组合即可完成，非常方便。当然，如上述范例，你也可以同时使用访客层级和访问或者hits层级的细分。通过多个层级的自定义组合筛选，几乎可以实现你所有想实现的高级细分。
</p>

<p style="text-align: left;">
  这个升级带来的另外一个作用是可以按照序列进行细分，有点类似于多渠道路径中的那种效果，你可以按照渠道来源步骤（或者其他路径）对用户进行细分。比如，可以细分出：从首页某个促销广告进入产品分类页面，再到产品页的用户；同时再去对比直接从分类页面进入产品页面的用户。这对于我们进行着陆页面的选择可以提供很有价值的参考数据。类似的场景可以根据实际业务需求进行拓展，发挥你的想象！
</p>

<p style="text-align: left;">
  更多详细的可以打开开篇提到的2个链接去看看，本文算是对它们的一个编译总结，同时加入了一些自己的想法。
</p>

<p style="text-align: left;">
  注：<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%ae%bf%e5%ae%a2%e7%bb%86%e5%88%86/" title="查看访客细分中的全部文章" target="_blank">访客细分</a></span>目前仅支持90天内的数据细分。
</p>

<p style="text-align: left;">