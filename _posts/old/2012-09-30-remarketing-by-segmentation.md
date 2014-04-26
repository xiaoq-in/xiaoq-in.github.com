---
title: 再营销之流量细分
author: 肖庆
layout: post
permalink: /google-adwords/remarketing-by-segmentation/
ratings_users:
  - 1
ratings_score:
  - 5
ratings_average:
  - 5
views:
  - 1361
yourls_shorturl:
  - http://t.xiaoq.in/1j
ta-thumbnail:
  - http://blog.xiaoq.in/thumb/cache/2012/9/895-1.gif;
categories:
  - Google AdWords
tags:
  - Google再营销
  - UTM标记
  - 再营销
  - 流量细分
  - 自定义变量
  - 谷歌再营销
---
<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/google%e5%86%8d%e8%90%a5%e9%94%80/" title="查看Google再营销中的全部文章" target="_blank">Google再营销</a></span>对于大多数广告主来说，应该是ROI最高的一种广告投放方式，可能仅次于品牌词广告系列，如果控制得当甚至会好于品牌词广告。之前的文章也说过，<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%86%8d%e8%90%a5%e9%94%80/" title="查看再营销中的全部文章" target="_blank">再营销</a></span>的主要优势是可以进行<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e6%b5%81%e9%87%8f%e7%bb%86%e5%88%86/" title="查看流量细分中的全部文章" target="_blank">流量细分</a></span>，自定义组合，针对性进行广告语、有效期和出价的调整。

那么，以下将就一种新的定位组合方式推荐给大家：根据<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/utm%e6%a0%87%e8%ae%b0/" title="查看UTM标记中的全部文章" target="_blank">UTM标记</a></span>进行<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%86%8d%e8%90%a5%e9%94%80/" title="查看再营销中的全部文章" target="_blank">再营销</a></span>。

<img class="alignnone size-full wp-image-896" title="remarketing-segmentation" src="http://blog.xiaoq.in/cdn/2012/09/remarketing-segmentation.gif" alt="" width="540" height="380" />

近期，谷歌启动了一项新的再营销方式，那就是通过URL过滤方式进行<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e6%b5%81%e9%87%8f%e7%bb%86%e5%88%86/" title="查看流量细分中的全部文章" target="_blank">流量细分</a></span>，我们之前可能都忽视了一点，只是对网站本身的URL进行细分组合，比如购物车，产品页面，产品列表页面，首页等。其实，还有另外一种方式，是非常值得去尝试的。尤其是当你进行了多个媒体的投放，比如，你在网址导航（如hao123）、新闻门户（如新浪网）、垂直门户（如太平洋女性网）、聊天工具（如qq聊天窗口）、手机客户端（如app广告）、社会化媒体（如新浪微博），等这些渠道进行了网络广告投放，同时在地铁还有一个二维码的广告，在合作网站还有一些资源互换，在CCTV还有一个添加了标记并进行短网址过处理的促销广告，等等。在此之前，这些流量对于再营销而言，如果用户访问了特定页面，他们对于你或者谷歌来说，都是毫无差异的。

然而，事实并非如此！

对于以上这些链接，为了区分不同来源渠道的流量，很多广告主都会加上标记符（一般就是GA的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/utm%e6%a0%87%e8%ae%b0/" title="查看UTM标记中的全部文章" target="_blank">UTM标记</a></span>，百度也有类似的但貌似很少人使用）。如果你去查看这些各种渠道来源的数据，就会发现它们的转化率会差别很大。因此，我们最好就是给这些不同的流量带来的用户进行**分别**再营销。

要实现这个功能，在AdWords中非常容易就能实现，你只需分别建立相应的再营销列表，然后在各个再营销列表中“包含”来自“utm_source=hao123”之类的流量，再等待数据，然后建立相应的广告组就可以了。

当然，你还可以做得更细化，比如你可能在新浪网的门户网站多个频道进行了投放，那么，你还可以使用utm\_content来进行标记不同的频道，比如你可以过滤来自新浪网女性频道的流量（utm\_content=lady），从而针对女性受众进行定向的广告投放，撰写相应的广告语，设置不同的时间段，或者出价时段等。

或者，你还可以做的稍微宽泛一些，由于AdWords可以通过开启auto tag标记让你的目标网址中自动加上&#8221;gclid=&#8221;，因此如果你只想对Google广告的流量进行定向投放，那么加上这个就行了。很可惜的是，百度已经去掉了URL参数标记这个功能（怀疑很可能跟<a title="百度竞价链接bdclkid全解密" href="http://yuli.in/webanalytics/%E7%99%BE%E5%BA%A6%E7%AB%9E%E4%BB%B7%E9%93%BE%E6%8E%A5bdclkid%E5%85%A8%E8%A7%A3%E5%AF%86/" target="_blank">百度竞价链接bdclkid全解密</a>有关），不过，你还是可以通过<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/utm%e6%a0%87%e8%ae%b0/" title="查看UTM标记中的全部文章" target="_blank">UTM标记</a></span>来实现类似功能，不仅是百度、谷歌，搜搜、搜狗、必应（雅虎）、360等等这些，都是可以的。

如果你已经对各个渠道的流量进行了细分，并且发现了其中的一些差异（如受众偏好、访问偏好、访问习惯等），那么，以上再营销策略是尝试的最好机会！如果你还没细分流量，那么现在就是时候了！

如何了解不同来源的用户行为差异？除了使用UTM标记，再尝试将来源（媒介）数据放入<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>中，是一个更好的方法。

Reference: <a title="Segment AdWords Remarketing By Traffic Source" href="http://searchenginewatch.com/article/2199932/Segment-AdWords-Remarketing-By-Traffic-Source" target="_blank">http://searchenginewatch.com/article/2199932/Segment-AdWords-Remarketing-By-Traffic-Source</a>