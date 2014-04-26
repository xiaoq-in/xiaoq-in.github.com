---
title: 搜索网络合作伙伴（要求同时选中 Google 搜索）？
author: 肖庆
layout: post
permalink: /google-adwords/filter-and-bid-differently-for-google-search-partners/
sina_t:
  - 'true'
ratings_users:
  - 1
ratings_score:
  - 5
ratings_average:
  - 5
views:
  - 1447
yourls_shorturl:
  - http://g.xiaoq.in/a
ta-thumbnail:
  - http://blog.xiaoq.in/thumb/cache/2012/4/744-1.jpg;http://blog.xiaoq.in/thumb/cache/2012/4/744-2.png;http://blog.xiaoq.in/thumb/cache/2012/4/744-3.png;http://blog.xiaoq.in/thumb/cache/2012/4/744-4.png;
categories:
  - Google AdWords
tags:
  - Adwords编辑器
  - Google 搜索
  - 搜索网络合作伙伴
  - 自定义字段
  - 过滤器
---
如果说展示广告的质量得分让你摸不着头脑，那么这是<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-adwords/" title="Google Adwords" target="_blank">Google Adwords</a></span>中数据最不透明的地方，完全剥夺了用户的选择权！

我们知道在Google AdWords的搜索广告中，你可以选择<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/google-%e6%90%9c%e7%b4%a2/" title="查看Google 搜索中的全部文章" target="_blank">Google 搜索</a></span>或者<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e6%90%9c%e7%b4%a2%e7%bd%91%e7%bb%9c%e5%90%88%e4%bd%9c%e4%bc%99%e4%bc%b4/" title="查看搜索网络合作伙伴中的全部文章" target="_blank">搜索网络合作伙伴</a></span>（要求同时选中 <span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/google-%e6%90%9c%e7%b4%a2/" title="查看Google 搜索中的全部文章" target="_blank">Google 搜索</a></span>），但是你无法单独选择<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e6%90%9c%e7%b4%a2%e7%bd%91%e7%bb%9c%e5%90%88%e4%bd%9c%e4%bc%99%e4%bc%b4/" title="查看搜索网络合作伙伴中的全部文章" target="_blank">搜索网络合作伙伴</a></span>，更不用说单独选择其中的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e6%90%9c%e7%b4%a2%e7%bd%91%e7%bb%9c%e5%90%88%e4%bd%9c%e4%bc%99%e4%bc%b4/" title="查看搜索网络合作伙伴中的全部文章" target="_blank">搜索网络合作伙伴</a></span>，比如www.ask.com。

搜索网络合作伙伴的效果是大相径庭的，在某些国家针对某些产品的广告，虽然流量份额很小，但是可能搜索网络合作伙伴的点击率和转化率会高些，但是在某些国家针对某些产品的广告，这些流量简直可以称作为垃圾流量。不信？数据说话！

在广告选项卡中选择细分“投放网络（含搜索网络合作伙伴）”，你绝对会惊奇地发现它们的点击率可能会相差几倍，转换费用也会差距很大。而看聚合数据的话，你很容易被误导。在此出于保密需要，不拿实际数据，截取了网络上的一个数据。

[<img class="alignnone size-full wp-image-745" title="superweak" src="http://xiaoq.in/g/pics/2012/04/superweak.jpg" alt="" width="846" height="252" />][1]

那么，既然我们知道搜索网络和合作伙伴中的数据和效果存在差异，首先需要解决的问题是这种差异性到底有多大，上面的方法是发现这种差异性的一种方法，另外一种是通过GA定制<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%bf%87%e6%bb%a4%e5%99%a8/" title="查看过滤器中的全部文章" target="_blank">过滤器</a></span>实现，后面将会说到具体怎么做。

在此，我们先假设Google搜索的转化率和各项综合指标均好于合作伙伴的，并且我们希望获得更广泛的覆盖面，那么我们如何优化呢？国外有人称可以让google客服手动排除一些合作伙伴的网站，具体如何操作及能否操作还没尝试过。假设，我们不求助于Google客服，该怎么做呢？

首先，请登录AdWords编辑器（这是一个非常重要的工具！）。我们需要在原来已经开启合作伙伴搜索的广告系列基础上新建一个广告系列不开启合作伙伴搜索的广告系列，通过编辑器复制黏贴功能几秒钟就可以搞定。因为Google搜索的效果更好，那么我们就在新建的仅开启Google搜索的广告系列设置更高些的出价。由于合作伙伴搜索的竞争稍微更低些，其CPC一般会低一些。因此，出价更高的广告系列中广告将仅展示在Google搜索中，而出价稍低的开启合作伙伴搜索的广告系列中，广告将会更多的展示在合作伙伴中。通过这种方法，你可以在一定程度控制在两个大类中的展示份额，控制预算分配和ROI。

如果你发现合作伙伴的效果更好，那么，反之亦然。

下面说说如何在GA中获取合作伙伴网络的数据。

你需要创建一个<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%bf%87%e6%bb%a4%e5%99%a8/" title="查看过滤器中的全部文章" target="_blank">过滤器</a></span>，将来源字段直接整合到来源或写入到一个新的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%ad%97%e6%ae%b5/" title="查看自定义字段中的全部文章" target="_blank">自定义字段</a></span>中。

方法一（将来源字段直接整合到来源）：【按照先后顺序】可能有些看不清，第一个引荐中是：^http://([^/]*)

[<img class="alignnone size-full wp-image-746" title="show paid referral1" src="http://xiaoq.in/g/pics/2012/04/show-paid-referral1.png" alt="" width="650" height="500" />][2]

[<img class="alignnone size-full wp-image-747" title="show paid referral2" src="http://xiaoq.in/g/pics/2012/04/show-paid-referral2.png" alt="" width="650" height="500" />][3]

（来源：流量的秘密第三版）

方法二（将来源字段直接写入新定义字段）：

[<img class="alignnone size-full wp-image-748" title="search partners" src="http://xiaoq.in/g/pics/2012/04/search-partners.png" alt="" width="600" height="450" />][4]

（来源：<a href="http://www.boom-online.co.uk/google-search-partner-ppc-data" target="_blank">http://www.boom-online.co.uk/google-search-partner-ppc-data</a>）

通过以上的自定义，你就可以具体了解到哪些合作伙伴带来的是垃圾流量，哪些带来的是高ROI流量。当然，这个提取出来的数据还是不太准确的，缺失了一部分，因为部分流量是没有引荐来源的（感谢cloga提示：部分可能来源于flash广告或者桌面广告）。

在AdWords论坛中看到一段描述这个问题的文字，摘录如下：

Some of the search partners don&#8217;t return referrer information, but Google does. If you have AdWords clicks with no referrer data, they are most likely coming from search partners, but you won&#8217;t know which ones. 有些合作伙伴并不会返回引荐信息，但是Google的流量确实会。如果你在AdWords的点击中看到无引荐的数据，他们很可能来源于搜索合作伙伴，但是你将不会知道到底是哪个。

以上为关于Google AdWords不太满意的一个地方，希望在不久的将来能给我们更多选择权、更多透明度。以及相应的解决方案，同时参考和整合了多个国外博客，感谢：

<a href="http://www.ppcian.com/optimizing-search-partner-network-traffic-in-ppc/" target="_blank">http://www.ppcian.com/optimizing-search-partner-network-traffic-in-ppc/</a>

<http://www.ppc-epiphany.com/2012/04/02/targeting-search-partners/>

<http://www.boom-online.co.uk/google-search-partner-ppc-data>

<http://www.epiphanysearch.co.uk/blog/how-to-improve-your-google-search-partners-ppc-performance/>

最后，没有有效数据支持的营销是盲目的！

 [1]: http://xiaoq.in/g/pics/2012/04/superweak.jpg
 [2]: http://xiaoq.in/g/pics/2012/04/show-paid-referral1.png
 [3]: http://xiaoq.in/g/pics/2012/04/show-paid-referral2.png
 [4]: http://xiaoq.in/g/pics/2012/04/search-partners.png