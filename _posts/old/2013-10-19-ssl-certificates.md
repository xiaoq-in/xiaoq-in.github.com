---
title: 安全套接口层（SSL证书）简介
author: 肖庆
layout: post
permalink: /net/ssl-certificates/
yourls_shorturl:
  - http://t.xiaoq.in/7z
ta-thumbnail:
  - http://blog.xiaoq.in/cdn/2013/10/PositiveSSL.png;
views:
  - 538
ratings_users:
  - 0
ratings_score:
  - 0
ratings_average:
  - 0
categories:
  - 互联网
tags:
  - https
  - PositiveSSL
  - SSL证书
  - 安全套接口层
  - 安全证书
---
请注意，是**<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%ae%89%e5%85%a8%e5%a5%97%e6%8e%a5%e5%8f%a3%e5%b1%82/" title="查看安全套接口层中的全部文章" target="_blank">安全套接口层</a></span>**，不是安全套哈，最直观的表现就是你在浏览器地址栏左侧会看到多了一个绿色安全标识。说明你访问这个页面是信息传输被加密的，任何第三方都无法窃听。这种证书，一般应用在电子商务网站、银行网站或者对安全要求很高的网站。

<img class="alignnone size-full wp-image-1374" alt="PositiveSSL" src="http://blog.xiaoq.in/cdn/2013/10/PositiveSSL.png" width="250" height="280" />

<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ssl%e8%af%81%e4%b9%a6/" title="查看SSL证书中的全部文章" target="_blank">SSL证书</a></span>，最便宜的就是我买的这个了，5年22.5美金，这是单域名的域名验证证书。<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ssl%e8%af%81%e4%b9%a6/" title="查看SSL证书中的全部文章" target="_blank">SSL证书</a></span>，从域名使用限制来说，主要分为单域名证书和泛域名的证书，泛域名的比单域名贵，贵很多，可能十倍左右；从验证范围来说，主要分为域名验证（5分钟左右就能发证，基本是系统自动审核的）、组织机构验证（一般需要寄送相关证明文件，如公司注册资料等，比较耗时，可能需要1-3个工作日，视发证单位而定）；从品牌来分，就比较多了，为了避免广告嫌疑，大家可以自己去搜索下。就知名度来说，可能VeriSign、GeoTrust、Godaddy用的人也比较多，像Google的证书是自己颁发的。Google的SSL安全登录，也是众多SEO和数据分析人员比较纠结的，(not provided)基本就是因为这个东西造成的。

细心的话，你会发现，从<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/https/" title="查看https中的全部文章" target="_blank">https</a></span>://出去的流量，都是归属于直接流量的。大家去我的友情链接点击几个看下utmz_的值就知道了。大概会是这样：248129937.1382111666.1.1.utmcsr=(direct)|utmccn=(direct)|utmcmd=(none)，意思就是，会被识别为直接流量。

因此，如果你的现有直接流量，可能有部分是来自一些支付通道的返回页面，或者其他安全网址的链接。这个要怎么区分？基本没辙。<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%ae%89%e5%85%a8%e5%a5%97%e6%8e%a5%e5%8f%a3%e5%b1%82/" title="查看安全套接口层中的全部文章" target="_blank">安全套接口层</a></span>的一个作用也在于此：保护隐私。引荐来源也在一定程度上属于个人隐私，如果严格来说的话。这也是Google为什么启用安全搜索的一个原因吧。

如果你只是购买的单域名证书，需要特别注意的是，如果你之前使用了子域名（www不算，<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%ae%89%e5%85%a8%e8%af%81%e4%b9%a6/" title="查看安全证书中的全部文章" target="_blank">安全证书</a></span>是包括它的），那么可能需要对这些引用地址做些处理，否则，你会看到绿色标识变灰了，右边地址栏也会多了个温馨提示的东西。这是因为你的安全网页存在混合性的内容，属于部分加密，即安全内容内部包含了非安全内容，大多数最新版本的浏览器默认是会屏蔽这种内容的加载的，主要是css、js等文件，因为它们在一定程度上还是存在安全隐患的（相对<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/https/" title="查看https中的全部文章" target="_blank">https</a></span>来说，大多数情况下还是安全的），从而造成页面变形等情况。当然，如果你还引用了外部文件的话，也需要特别注意修改下http协议为https，一般就是jquery之类的（大多数直接改下https就好，或者直接改成//，它们本来就支持http）。另外，部分数据分析工具可能并不支持https协议，比如腾讯分析，CNZZ的部分跟踪代码需要手动修改来支持。

<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%ae%89%e5%85%a8%e8%af%81%e4%b9%a6/" title="查看安全证书中的全部文章" target="_blank">安全证书</a></span>，在一定程度上是会降低加载速度的，因为它需要发送多几个请求，但影响微乎其微，而且再次访问时候，这种影响就更小了。

对于电商网站来说，使用<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%ae%89%e5%85%a8%e8%af%81%e4%b9%a6/" title="查看安全证书中的全部文章" target="_blank">安全证书</a></span>主要有两个好处：

1.  安全：任何第三方均无法截获你的数据，你可以对敏感数据进行加密，如会员信息、订单数据。因为它们的传输过程是经过多层加密解密算法进行的，基本无法破解。
2.  信任：有相关的研究和调研表明，用户在输入信用卡信息、用户敏感信息时候，会特别谨慎，网址前的绿色标识能一定程度提升其信任度。就我个人来说，如果哪天我看到支付宝不使用https，我可能就不敢输入支付密码。银行网站也是。我们看到铁道部的订火车票网站也会搞一个证书（它使用的是自己颁发的证书，因此需要用户安装，否则会被浏览器拦截），也类似。

当然，也需要提醒一下的是，看到有绿色标识，尤其是域名认证的，其实也并不一定是安全的，因为它就只是核对域名注册信息是否正确，然后邮箱验证。这种数据当然也很容易造假。组织机构认证的可能就相对更安全一些，因为它是必须验证你的商业或组织实体的。不同的证书发行机构都会有不同的赔付金额，组织机构证书的赔付金额相对多很多。这种赔付主要是针对网站而言的，大体是如果证书原因造成信息泄露之类的，可以得到赔付。它并非针对消费者，基本也是个幌子，貌似也没人真正有机会得到这种赔付的。

大多数证书都是可以免费无限次数的重新生成的，当然也就是比如你不小心删除了初始SCR文件（然后备份也找不到了），或者更换了服务器这种情况，才需要重新生成。

证书的安装并不是非得要独立服务器或者VPS才能玩的，一般的虚拟主机也行。Cpanel和DirectAdmin应该都没问题，其他控制面板未测试过，国内的虚拟主机商控制面板貌似比较弱，各种收费项目，不知道是否都能免费给你支持了。

安装起来并不难，至少对于我这个没学过技术的人来讲，跟着系统邮件发送帮助文档，5分钟就可以配置好。

我买这个证书也主要是因为它便宜，顺便玩下。本站也基本不涉及到敏感信息的交互的，放心~

在这个网站买的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/positivessl/" title="查看PositiveSSL中的全部文章" target="_blank">PositiveSSL</a></span>证书：<a title="cheapssls" href="http://www.cheapssls.com/" target="_blank">http://www.cheapssls.com/</a>，NameCheap旗下的公司，还行吧。对了，别忘了使用优惠码（直接打九折）：MissedYou。这个是看到他们的再营销广告打出来的。本站无任何广告成分，虽然国外的优惠码推荐这些都有分成之类的（所谓的affiliate marketing），但是这个是真的没有！

扩展阅读，归为直接来源的可能情况：<a href="http://www.webtrendsoutsider.com/2013/reasons-for-direct-traffic-in-referrer-reports/" target="_blank">http://www.webtrendsoutsider.com/2013/reasons-for-direct-traffic-in-referrer-reports/</a>

最后，对SSL证书有兴趣的童鞋，可以看下阮一峰翻译的博客：<a href="http://www.ruanyifeng.com/blog/2011/02/seven_myths_about_https.html" target="_blank">http://www.ruanyifeng.com/blog/2011/02/seven_myths_about_https.html</a>