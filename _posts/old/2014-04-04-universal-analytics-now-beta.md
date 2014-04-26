---
title: Universal Analytics正式发布了！
author: 肖庆
layout: post
permalink: /google-analytics/universal-analytics-now-beta/
ratings_users:
  - 0
ratings_score:
  - 0
ratings_average:
  - 0
views:
  - 261
categories:
  - Google Analytics
tags:
  - analytics.js
  - GTM
  - UA
  - uid
  - Universal Analytics
  - 升级
  - 宏
  - 自定义指标
  - 自定义维度
  - 跨屏跟踪
---
<a title="Universal Analytics: Out of beta, into primetime" href="http://analytics.blogspot.com/2014/04/universal-analytics-out-of-beta-into.html" target="_blank">Google Analytics官方博客</a>和<a title="Universal Analytics: Now out of beta!" href="http://cutroni.com/blog/2014/04/02/universal-analytics-now-beta/" target="_blank">Justin Cutroni的博客</a>于美国时间4月2日发布博客公告<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/universal-analytics/" title="查看Universal Analytics中的全部文章" target="_blank">Universal Analytics</a></span>（以下简称<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ua/" title="查看UA中的全部文章" target="_blank">UA</a></span>）已经走出测试阶段，即正式发布了。<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ua/" title="查看UA中的全部文章" target="_blank">UA</a></span>自去年十月份推出以来，各项<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%8d%87%e7%ba%a7/" title="查看升级中的全部文章" target="_blank">升级</a></span>功能让人眼前一亮，不过在此前由于对GA老版本功能的支持不太全面（比如再营销、人群报告、内容实验等），因此我们不得不同时运行2个跟踪代码。不过现在，我们可以只用一个了，UA是未来的方向，虽然GA版本并不会马上淘汰，但是后续的功能<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%8d%87%e7%ba%a7/" title="查看升级中的全部文章" target="_blank">升级</a></span>将只针对UA版本了。

从今天开始，<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/universal-analytics/" title="查看Universal Analytics中的全部文章" target="_blank">Universal Analytics</a></span>就是<span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>，反之亦然！尽早切换到UA版本吧。

<img class="alignnone size-full wp-image-1661" alt="Google-Analytics-Universal-Analytics-e1351521478750" src="https://xiaoq.in/cdn/2014/04/Google-Analytics-Universal-Analytics-e13515214787501.png" width="600" height="341" />

另外，我们发现<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/analytics-js/" title="查看analytics.js中的全部文章" target="_blank">analytics.js</a></span>代码也于4月2日进行了更新，增加了对<a title="User ID - Web Tracking (analytics.js)" href="https://developers.google.com/analytics/devguides/collection/analyticsjs/user-id" target="_blank">User ID参数</a>的支持。

如果你对部署<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/uid/" title="查看uid中的全部文章" target="_blank">uid</a></span>感兴趣，并且使用<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/gtm/" title="查看GTM中的全部文章" target="_blank">GTM</a></span>的话，可以看<a href="https://support.google.com/tagmanager/answer/4565987" target="_blank">这里</a>。简单来说，就是新增一个<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%ae%8f/" title="查看宏中的全部文章" target="_blank">宏</a></span><span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/uid/" title="查看uid中的全部文章" target="_blank">uid</a></span>，获取用户ID（一般是会员ID之类的，如有必要可以进行（哈希值加密）处理，不要传递可识别身份的信息，这是违反GA政策的），然后通过自定义字段将&<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/uid/" title="查看uid中的全部文章" target="_blank">uid</a></span>={{uid}}附加到UA的请求URL参数中去。而获取用户ID的方法比较多，通常来说有3种：

1.  通过第一方Cookie的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%ae%8f/" title="查看宏中的全部文章" target="_blank">宏</a></span>：console中输入document.cookie找到用户ID的字段，在<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/gtm/" title="查看GTM中的全部文章" target="_blank">GTM</a></span>的cookie名称中填写该字段值，即=前的，如一号店的为：yihaodian_uid。
2.  通过dataLayer的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%ae%8f/" title="查看宏中的全部文章" target="_blank">宏</a></span>：在程序的模板中写入dataLayer的相关信息，范例如：<script>dataLayer = [{'uid': '<span style="color: #ff6600;">1</span>'}];</script>
3.  通过自定义JavaScript的宏：这个需要懂点js或jquery以及dom相关知识，然后网站的前端可以通过js识别并读取到用户ID的字段。这个对网站的规范要求比较严格，一旦网站的相关class或id更改，或者部分页面的这些值没有或class和id不同，可能会丢失数据或造成数据比较混乱，一般情况下不建议使用这种。当然，使用自定义JavaScript也可以获取cookie的值，如方法一，不过麻烦很多，不如直接用方法一。

那么，我们为什么要升级到UA？UA有什么优势？概括起来主要有以下几点：

1.  GA能实现的功能，UA也都能实现。UA支持更多新功能，比如上面说到的User Id（个人预测这个将会成为今年的一个热门功能，它解决的问题正是目前备受关注的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%b7%a8%e5%b1%8f%e8%b7%9f%e8%b8%aa/" title="查看跨屏跟踪中的全部文章" target="_blank">跨屏跟踪</a></span>）及其相关功能报告，另外<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e7%bb%b4%e5%ba%a6/" title="查看自定义维度中的全部文章" target="_blank">自定义维度</a></span>和指标比此前的自定义变量可要好用多了，Measurement Protocol让我们的跟踪不仅仅局限于WEB、mobile或者APP，理论上只要能上网的设备，都可以接入UA进行跟踪。维度扩展、数据导入、服务器端的跟踪参数设置等，都远远超越了GA。
2.  Google Tag Manager已经全面支持UA的所有功能设置。当大家对UA的认识逐步加强之后，我们会越来越多地使用Tag Manager类工具，而Google本身提供的这个免费工具也会随着UA的使用而逐步受到广泛认可与使用。
3.  商业付费版的支持也让一些高大上的公司可以放心使用了，因为UA也在SLA协议中了，SLA即类似于国外很多主机服务商所承诺的在线率保证，比如99.99%。UA保证的SLA是：数据收集99.9%，数据处理在98%的情况下4小时内处理完毕，数据报告每个月都保证99%的可用率。详见<a title="Intelligence for  the enterprise,  made easy" href="http://static.googleusercontent.com/media/www.google.com/en/us/intl/en_ALL/analytics/premium/premium_fact_sheet.pdf" target="_blank">这里</a>。
4.  另外，上面说的Measurement Protocol还支持自定义传递IP和User Agent的值对原始数据进行覆盖，这个可能对于某些开发者比较有用。
5.  在上述两个博客中，都提到之后的数据处理将根据用户设置的时区进行处理。在此前都是根据美国太平洋时间（即谷歌数据中心的地理位置时间），用户可能感觉不到什么，但是对于我们亚洲国家的用户来说确实很好，跟着我们自己的时区来走好多了，毕竟GA还是有数据延迟的。这个相当于是给每个账户制定相应的计划任务了，个人认为。

从GA升级到UA，对于一般的公司（只进行简单的流量统计）来说可能没有什么，点击几个升级按钮即可。而对于之前进行过复杂的代码部署的公司来说，确实会比较费事，如果你恰好是这种类型，最好现在就开始规划好吧。UA是大势所趋！

如果你现在新注册UA，强烈建议直接选择UA版本，免得后续再升级迁移很麻烦。

另外，uid相关的几个设置和报告，貌似还没有完全开放出来，至少我这边几个站点都是没有看到踪影，不过非常值得期待。我们后续再分享一些uid和GTM相关的内容，欢迎留言说下你感兴趣的话题。

&nbsp;