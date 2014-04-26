---
title: 跟踪离线转化了解更准确的转化路径与广告支出回报率
author: 肖庆
layout: post
permalink: /google-adwords/offline-conversion-tracking/
yourls_shorturl:
  - http://t.xiaoq.in/7s
views:
  - 877
ratings_users:
  - 3
ratings_score:
  - 15
ratings_average:
  - 5
ta-thumbnail:
  - https://xiaoq.in/thumb/cache/2013/9/1286-1.png;
categories:
  - Google AdWords
tags:
  - CRM对接
  - ROAS
  - 广告支出回报率
  - 离线跟踪
  - 离线转化
  - 跟踪离线转化
  - 转化路径
---
对于大多数询盘导向型的网站来说，纯粹地使用在线广告跟踪有时候并不那么准确可靠。在线提交的有所谓的垃圾询盘，而大客户的产生一般都会经历较长的转化周期，线下一般会经历电话、邮件、拜访等多种沟通方式，最终才形成可衡量实际价值的转化——订单。在之前我们一般会使用两套跟踪系统，一个是在线广告转化跟踪，另外一个则是CRM（客户管理系统）或类似的其他系统。

这两个系统很少会进行关联，即便通过一些技术手段进行了关联，但一般是数据分析系统之间的整合，如之前提过的这种方式（<a title="GA如何与CRM系统进行对接" href="http://xiaoq.in/google-analytics/ga-connect-with-crm/" target="_blank">GA如何与CRM系统进行对接</a>），我们可以在CRM中看到客户的来源信息，而如果需要同时看到广告费用信息进行ROI评估，则还需要通过API去导入（API一般门槛都较高）。这是一种本地化的数据导入与整合方式。

<img class="alignnone  wp-image-1295" alt="AdWordsOfflineConv" src="http://cdn.xiaoq.in/2013/09/AdWordsOfflineConv.png" width="500" />

如今，AdWords则支持一种更便捷的方式，你可以直接将离线的转化数据导入到其广告系统中，直接在广告后台中看到一个完整的转化行为和数据，从而实现更好的ROI评估。并且，在不久的将来，它还将支持基于<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/roas/" title="查看ROAS中的全部文章" target="_blank">ROAS</a></span>（return on as spend<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%b9%bf%e5%91%8a%e6%94%af%e5%87%ba%e5%9b%9e%e6%8a%a5%e7%8e%87/" title="查看广告支出回报率中的全部文章" target="_blank">广告支出回报率</a></span>）这种转化出价。

导入数据也并不会如你想象的那么复杂困难，一般技术人员可能只要5分钟就能搞定。基本就是加入2段javascript代码（官方有提供），然后在在线表单中加入一段隐藏字段的数据提交代码，当然你还需要开启自动标记。其实这个跟踪的基本原理很简单，就是通过开启自动标记之后，广告着陆URL的末尾会有一段类似这个标记：?gclid=CMe2k9fxurkCFcwE4godsx0ADg，通过javascript定义把这个字段作为cookie存储在浏览器端，然后在客户在线转化的表单中通过另外一段javascript读取上述存储的这个值，并且通过一个隐藏字段将这个值联通此次提交的所有其他信息同时关联地存储到数据库中。这样，你在CRM系统中对该客户的后续行为进行标记，比如一个礼拜后客户下了一百元的订单，一个月后又下了一万元的订单。这样，通过各个关键转化节点的时间戳，并且标记不同的转化行为，当你导入到AdWords系统中，这些数据就直接呈现在广告报表中了。你可以通过细分数据了解各个转化分别是什么类型的，对应的价值是多少。同时，在搜索渠道中你也可能看到这些导入数据的表现。

需要注意的几点是：

1.  数据一旦导入不能修改或删除，因此务必谨慎操作。
2.  只能支持90天的转化周期，因此如果该<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%a6%bb%e7%ba%bf%e8%bd%ac%e5%8c%96/" title="查看离线转化中的全部文章" target="_blank">离线转化</a></span>源于90天之前的在线点击转化行为，那么导入是无效的，建议定期进行数据导入。（个人认为，可能与gclid的有效期有关）
3.  时区注意设置，如中国的就是+0800。
4.  上传表格中的转化价值如果不填写的话，则会默认使用表单处设置的价值。

如果你使用如下几个CRM系统，那么这是操作指南，如果你想了解更详细的操作指南，那么请看官方帮助中心提供的文档：<a title="跟踪离线转化" href="https://support.google.com/adwords/answer/2998031?hl=zh-Hans" target="_blank">跟踪离线转化</a>：

*   <a href="http://blog.marketo.com/blog/2013/09/how-to-optimize-google-adwords-with-offline-conversion-tracking-and-marketo.html" target="_blank">Marketo</a>
*   <a href="https://support.mongooseportal.com/entries/24967316-AdWords-Conversion-Import-Integration-Feature-Guide" target="_blank">Mongoose Metrics</a>
*   <a href="http://developers.sugarcrm.com/wordpress/2013/09/05/measure-online-to-offline-conversions-with-google-adwords-sugarcrm/" target="_blank">SugarCRM</a>
*   <a href="https://support.google.com/adwords/answer/3285060" target="_blank">Salesforce.com’s Sales Cloud</a>

最后说下，为什么我们不直接通过读取URL中的字段来实现跟踪呢，这样不是简单多了么，何必去存储cookie再去读取？其实很简单，除非你是一个单页面推广，否则用户可能会去到其他页面再最终回到转化页面进行信息提交，而在这个过程中，可能会丢失URL中的标记，而cookie则不同，只要你不清空cookie或者换浏览器之类的，基本是都可以保留的。其实，如果你曾经关注过AdWords官方推广优惠券的着陆页面，你会发现他们其实很早之前就是在用这个“URL读取”方法的。