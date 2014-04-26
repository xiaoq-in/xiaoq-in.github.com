---
title: Google Analytics实现队列分析
author: 肖庆
layout: post
permalink: /google-analytics/cohort-analysis-with-google-analytics/
ratings_users:
  - 0
ratings_score:
  - 0
ratings_average:
  - 0
views:
  - 3722
yourls_shorturl:
  - http://t.xiaoq.in/16
ta-thumbnail:
  - https://xiaoq.in/thumb/cache/2012/12/1003-1.png;
categories:
  - Google Analytics
tags:
  - Cohort
  - 事件跟踪
  - 自定义变量
  - 队列
  - 队列分析
  - 队列研究
---
本文是对Justin Cutroni的最新文章<a title="Cohort Analysis with Google Analytics" href="http://cutroni.com/blog/2012/12/11/cohort-analysis-with-google-analytics/" target="_blank">Cohort Analysis with Google Analytics</a>的编译及总结，希望对英文水平不太好又对GA的高级应用感兴趣的童鞋有所帮助。

<img class="alignnone size-full wp-image-1006" alt="Screenshot-12712-1201-PM" src="http://cdn.xiaoq.in/2012/12/Screenshot-12712-1201-PM.png" width="586" height="318" />

首先，根据维基百科的解释：<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e9%98%9f%e5%88%97/" title="查看队列中的全部文章" target="_blank">队列</a></span>（cohort）是指一群在特定时期内有共同特征或经历的人，如在某一时期出生或在暴露于某因素（如一种药物、疫苗、污染物或经历特定的医疗过程等）的人。

这个术语通常被用在医学研究领域，不过我们也可以将它应用到我们的数据分析领域，比如分析某个网购高峰期人群的行为习惯，对不同时段注册或购买的老用户进行分析，对不同购买周期的用户进行分析，总之就是通过时间这个维度贯细分不同的用户群，找出它们的共同点和差异，从而为营销计划提供参考。

虽然在<span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>中目前还没有这个功能（根据Justin的介绍，在不久的将来，会有的），不过，我们当前还是可以通过其他的方法来实现类似效果，一种是<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>中写入日期时间值，另外一种是通过<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>来实现，同样也是写入日期时间值到事件参数中。

虽然两种方法都可以实现，不过建议使用<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>的形式，写入访客级<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>中，如：_gaq.push(['setCustomVar', 1,'FPD', 'YYYYMMDD', 1]);（FPD代表首次购买时间，YYYYMMDD代表如20121217形式的日期值）。请注意，这段代码仅在该目标完成之后才写入，一般建议放在支付完成后的感谢页面。

如果你使用<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>方式的话，可能在功能实现上会比较麻烦，并且由于值不是存储在cookie中，还可能出现数据丢失等情况。代码如：_gaq.push(['trackEvent', '<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/cohort/" title="查看Cohort中的全部文章" target="_blank">Cohort</a></span>s','FirstPurchase', 'YYYYMMDD']);，这段代码一般放在是登陆成功页面或者所有页面中。

通过上述方法，我们可以获得用户的初次购买时间，同理，你也可以跟踪注册时间，第二次下单时间，甚至两者之间的时间差，根据具体需要而定。

数据获取之后，我们可以通过自定义报告的方式对这些数据进行更有效的数据呈现，通过过滤功能筛选出某个月份或某一天购买的用户，然后查看各自的目标完成情况，电子商务转化记录，流量来源媒介、或者网站的一般访问指标（如跳出率、停留时间、每次访问页面等），你是否能从中发现一些规律呢？这种研究对于大型电子商务的大型促销活动尤为有效（如京东的双十二促销），你可以了解当天哪种流量来源/媒介最有效，从而为后续推广提供重要参考。当然最主要的是，你可以了解当天购买的新老用户不同的行为习惯，通过对这类人群的后续跟踪分析，你或许会发现它们有着不同的偏好，从而你可以对这类人群进行细分，再进行更有针对性的营销计划。

获取数据的方法其实很简单，访客级的自定义变量写入一个日期数据；定制数据报告也很简单，过滤筛选，拉出关注的数据指标即可。关键是如何应用这些数据，并且应用到你的业务中，如果能对接上CRM系统，那么意义将更加重大。