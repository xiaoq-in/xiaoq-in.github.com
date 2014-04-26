---
title: 将广告引流到第三方平台，如何做数据分析和再营销
author: 肖庆
layout: post
permalink: /google-analytics/ad-leading-to-third-party-platform/
yourls_shorturl:
  - http://t.xiaoq.in/83
ta-thumbnail:
  - http://blog.xiaoq.in/cdn/2013/10/1111.jpg;http://blog.xiaoq.in/cdn/2013/10/full-referral-filter1.png;
views:
  - 1059
ratings_users:
  - 1
ratings_score:
  - 5
ratings_average:
  - 5
categories:
  - Google Analytics
tags:
  - 再营销
  - 双十一
  - 实时报告
  - 数据对接
  - 来源跟踪
  - 点击跟踪
  - 第三方平台
  - 订单跟踪
  - 转化跟踪
---
将广告引流到<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%ac%ac%e4%b8%89%e6%96%b9%e5%b9%b3%e5%8f%b0/" title="查看第三方平台中的全部文章" target="_blank">第三方平台</a></span>，是很多<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%ac%ac%e4%b8%89%e6%96%b9%e5%b9%b3%e5%8f%b0/" title="查看第三方平台中的全部文章" target="_blank">第三方平台</a></span>卖家会做的一件事情。其中以知名的或品牌建立初期的旗舰店或集市卖家为主。平台内的广告虽然转化率很高，但竞争激烈，点击成本很高。如果稍微有些外部广告投放经验的团队，可能也会同时再考虑下外部广告，比如搜索引擎广告。它们能带来新鲜的血液，点击成本会低很多，虽然转化率可能也低很多，但如果做的好的话，可能最终的效果会更好。当然，投放这种广告，很难避免的一个情况就是给其他同行做了嫁衣，当然最终受益者是平台本身了。

事实有时就是这么无奈。不过一旦决定投放，设计一个极富吸引力并能让用户**买单**的页面；或者使用历史转化效果最高的页面是非常有必要的。尽量避免流失，优惠券、满减送、包邮、五折、收藏送礼啥的，都可以尝试下。

将广告投放到<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%ac%ac%e4%b8%89%e6%96%b9%e5%b9%b3%e5%8f%b0/" title="查看第三方平台中的全部文章" target="_blank">第三方平台</a></span>，最让人头疼的就是数据的不开放。大多数第三方平台是不支持添加自己的JS代码的。要获取到相关数据，很难。关系好并且有钱的话，可能会给你建立一个频道，让你添加自己的代码，但跟踪到的数据也仅限于页面点击，最终成单数据与来源的对接也很难。另外的一个途径是通过联盟平台，可以获取到一些基本的订单数据，不过同样的是，关键词或者展示网址这种层级数据的对接，你还是没办法。再高级一点的方法是，通过API对接，这个技术门槛很高并且平台的数据开放程度不同，很多所谓的开放平台其实非常闭合的。而且，如果要细致跟踪的话，还得给每个关键词添加不同的代码，麻烦程度可想而知。

快要到<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%8f%8c%e5%8d%81%e4%b8%80/" title="查看双十一中的全部文章" target="_blank">双十一</a></span>了，想起了去年的这个时候。投放天猫旗舰店广告，千辛万苦的加代码，千辛万苦的等数据，费劲功夫的要数据。

<a href="http://g.xiaoq.in/?url=http://ai.m.taobao.com/?pid=mm_17247524_4240622_14488459&eventid=858300" target="_blank"><img class="alignnone  wp-image-1398" alt="1111" src="http://blog.xiaoq.in/cdn/2013/10/1111.jpg" width="600" height="144" /></a>

当时最有效的方式就是要来量子统计的数据，虽然费劲周章，但最终还是成功了—破纪录的销量，客户的表扬。

这两天，突然想到一个比较好的方式：通过添加<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%82%b9%e5%87%bb%e8%b7%9f%e8%b8%aa/" title="查看点击跟踪中的全部文章" target="_blank">点击跟踪</a></span>代码来实现。主要是看到AdWords设置选项卡里面有“动态跟踪网址”才想到的。添加方式当然是类似于MZ等很多付费工具那样，前面加个前缀，如：

**http://g.xiaoq.in/?url=**http://ai.m.taobao.com/?pid=mm\_17247524\_4240622_14488459&eventid=858300

可以说，我们目前看到的视频广告、门户网站广告等数字平台广告，基本都是使用的这种跟踪方式。当然它们可能还会结合其他相关数据、捕捉的信息更多、准确性提高、速度更快、有防作弊机制等。稍微优雅点的方式是再转换成短网址形式。

这个方法的原理很简单：使用自己的URL来进行<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%82%b9%e5%87%bb%e8%b7%9f%e8%b8%aa/" title="查看点击跟踪中的全部文章" target="_blank">点击跟踪</a></span>，<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%82%b9%e5%87%bb%e8%b7%9f%e8%b8%aa/" title="查看点击跟踪中的全部文章" target="_blank">点击跟踪</a></span>的URL有跳转的功能，同时页面内部加入必要的跟踪代码：<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>代码、百度统计代码、<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%86%8d%e8%90%a5%e9%94%80/" title="查看再营销中的全部文章" target="_blank">再营销</a></span>代码、回访客代码等（如代码太多可以加上一个短暂加载延迟）。当然，更简单的方式是直接加入Google Tag Manager代码，加载快些并且方便扩展。

作为一个技术小白，提供下最简单的代码：

**index.php**

<?php  
include &#8216;tag.php&#8217;;  
$url = str\_replace(&#8216;url=&#8217;,&#8221;,$\_SERVER['QUERY_STRING']);  
echo &#8220;<meta http-equiv=&#8217;refresh&#8217; content=&#8217;0;url=$url&#8217; />&#8221;  
?>

**tag.php**

echo方式加入GTM代码或其他代码即可。

这里，我们以GA为例，如果遇到实时性要求很高的促销活动（比如<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%8f%8c%e5%8d%81%e4%b8%80/" title="查看双十一中的全部文章" target="_blank">双十一</a></span>），我们大可以投放广泛匹配关键词，然后再去实时调整关键词或展示位置。

如果是关键词搜索广告，则只需查看自然搜索的关键词报告即可（其实就是用户的搜索词）；如果是内容广告，则可以配置一个“完整引荐URL”的过滤器。再经过简单的Excel分列处理，则可以看到所有的展示URL了。GA提供的数据报告比广告系统的数据报告延迟更短，数据也更全面。

<img class="alignnone size-full wp-image-1400" alt="full referral filter" src="http://blog.xiaoq.in/cdn/2013/10/full-referral-filter1.png" width="700" height="450" />

当然，如果希望对接订单系统，还可以加上时间戳，如果数据量不是太多，用户也不是太纠结，基本还是可以将来源与转化数据拼接起来的。如果希望查看更详细的广告来源数据，可以再使用TrackValue动态参数，再使用一些简单的URL截取函数，就可以形成比较全面的数据报告了。

如果是投放内容广告的话，一般我们可以提前一周左右时间进行较大规模的投放将<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%86%8d%e8%90%a5%e9%94%80/" title="查看再营销中的全部文章" target="_blank">再营销</a></span>的网撒开积累足够的用户，这样在活动当天就可以很快爆发了。爆款，就是这么炼成的！

方法很简单，有兴趣的试试吧！

&nbsp;