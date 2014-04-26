---
title: AdWords Scripts的常见用法解析
author: 肖庆
layout: post
permalink: /google-adwords/adwords-scripts-common-usages/
yourls_shorturl:
  - http://t.xiaoq.in/7u
views:
  - 1367
ratings_users:
  - 1
ratings_score:
  - 5
ratings_average:
  - 5
ta-thumbnail:
  - http://blog.xiaoq.in/thumb/cache/2013/9/1307-1.png;
categories:
  - Google AdWords
tags:
  - AdWords Scripts
---
对于大多数的广告优化人员来说，可能很少有机会去用到自动竞价管理工具或者通过API去进行批量化管理与优化，不过对于使用<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-adwords/" title="Google Adwords" target="_blank">Google Adwords</a></span>的人来说，只要你稍微懂一些Javascript，具有一定的广告优化经验，很多自动化的功能都能够实现，绝对高端大气上档次，这就是<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/adwords-scripts/" title="查看AdWords Scripts中的全部文章" target="_blank">AdWords Scripts</a></span>。

<img class="alignnone size-full wp-image-1308" alt="AdWords Scripts" src="http://blog.xiaoq.in/cdn/2013/09/AdWords-Scripts.png" width="648" height="375" />

<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/adwords-scripts/" title="查看AdWords Scripts中的全部文章" target="_blank">AdWords Scripts</a></span>这个东西，在某种程度上是自动化规则的升级版，不过由于它是从底层的代码进行操作的，因此更为灵活。通过它，你可以实现：自动化出价、自动化报表、自动化替换和暂停或启用广告语、记录各种细微数据变化进行测试对比、调整预算，你能想到的几乎都可以实现。当然主要还是基于现有的逻辑和外部的一些数据来进行操作，有些过于复杂的竞价策略实现起来可能还是比较麻烦。

如果你稍微研究过这个功能，应该都会知道这个网站：<a title="Free AdWords Scripts.com" href="http://www.freeadwordsscripts.com/" target="_blank">Free AdWords Scripts.com</a>，里面提供了很多范例代码，很多可以直接套用，或者进行一些细微修改来用。当然，<a title="Complete Scripts" href="https://developers.google.com/adwords/scripts/docs/examples/complete-scripts" target="_blank">官方文档</a>也提供了大量的范例文件和详细的说明文档。其中，最经典的例子有几个：

1.  记录质量得分的变化趋势，具体可以看下这篇文章：<a title="AdWords Quality Score Tracker Version 2.0 – Now with Labels" href="http://www.ppc-epiphany.com/2013/01/26/adwords-quality-score-tracker-version-2-0-now-with-labels/" target="_blank">AdWords Quality Score Tracker Version 2.0 – Now with Labels</a>。将这些统计出来的数据再绘制成图表，你将能很直观地体会到质量得分的变化趋势，在一定程度上能了解账户的状况是否在变好或者变差。（不过请注意，质量得分只是一方面，其他如竞争环境或者转化数据等因素也要考虑）
2.  根据条件（如促销倒计时、价格库存更新等）修改、暂停或启用广告语，主要使用<a title="Ad Parameters" href="https://developers.google.com/adwords/api/docs/guides/ad-parameters" target="_blank">Ad Parameters</a>。当然，你也可以结合天气情况等外部数据进行实时广告语或者出价的调控，比如旅游类、化妆品类广告等就可以尝试。当然，考虑到劳动力的廉价，实际情况的复杂程度，和一定的编程门槛，可能有时候并不能实际去使用，仅供参考，了解些思路也是很有必要的。
3.  在公司做广告管理优化的，可能最头疼的事情就是做各种日报、周报和月报等常规报告，以及各种突发性的临时报告了。只要在这个时候，才会发现对各种Excel操作的掌握并不全面和深入，最常用的如Vlookup、SUMPRODUCT、透视表、图表等。如果是常规化的报告，花上半天或者一天的时间去考虑下如何自动化实现，会是一件很有价值的事情。<a title="Account Summary Report" href="https://developers.google.com/adwords/scripts/docs/solutions/account-summary" target="_blank">Account Summary Report</a>提供了不错的范例参考，还有<a title="Automating Monthly Reporting Using AdWords Scripts" href="http://www.ewanheming.com/adwords-scripts-monthly-report" target="_blank">这个</a>。
4.  死链检查。在大概去年的时候有说过一个方法，不过都是需要定期或不定期地进行手工操作，费时费力。通过<a title="Link Checker" href="https://developers.google.com/adwords/scripts/docs/solutions/link-checker" target="_blank">Link Checker</a>，你可以进行每日自动监测，再也不怕浪费广告费了。另外，通过<a title="Account Anomaly Detector" href="https://developers.google.com/adwords/scripts/docs/solutions/account-anomaly-detector" target="_blank">账户异常监测</a>，它能够及时给你发送邮件预警，类似Top Mover的功能了。
5.  搜索查询报告。这个是做搜索最为关注的一个数据点了，否定词和扩展关键词全靠它了。现在，通过<a title="Search Query Report" href="https://developers.google.com/adwords/scripts/docs/solutions/search-query" target="_blank">Search Query Report</a>，你可以预设一些条件对搜索词进行自动地添加或者否定。方便很多了吧？换做内容广告的，展示位置的处理方式也类似于此。
6.  标签（虚拟文件夹）。这个功能是任何大型账户的操作人员都会使用的一个工具，因为我们的广告账户分组可能很多时候需要考虑到账户的结构与表现相关性等因素，而老板关注的点可能是从另外一个角度去看，或者实际业务需要从另外一个角度去看问题，再或者我们需要筛选出其中最有价值的数据进行重点优化，这都是标签的一些基本用途。现在，通过<a title="Labels" href="https://developers.google.com/adwords/scripts/docs/solutions/labels" target="_blank">标签的自动化设置</a>，你可以减少很多重复工作量。比如自动给“昨日点击最多，转化费用高于目标期望的非品牌关键词”加上标签，然后发送到你的工作邮箱。

以上是我们使用<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/adwords-scripts/" title="查看AdWords Scripts中的全部文章" target="_blank">AdWords Scripts</a></span>来实现的最常用的一些功能，并且都有提供了范例，比较适合有一定编程基础和较长账户操作经验的童鞋使用。