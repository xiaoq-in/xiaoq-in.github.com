---
title: 解密Google搜索的VED参数
author: 肖庆
layout: post
permalink: /google-analytics/decoding-google-referral-string/
yourls_shorturl:
  - http://t.xiaoq.in/7v
views:
  - 564
ratings_users:
  - 1
ratings_score:
  - 5
ratings_average:
  - 5
ta-thumbnail:
  - http://blog.xiaoq.in/thumb/cache/2013/9/1313-1.png;http://blog.xiaoq.in/thumb/cache/2013/9/1313-2.png;http://blog.xiaoq.in/thumb/cache/2013/9/1313-3.png;http://blog.xiaoq.in/thumb/cache/2013/9/1313-4.png;http://blog.xiaoq.in/thumb/cache/2013/9/1313-5.png;http://blog.xiaoq.in/thumb/cache/2013/9/1313-6.png;http://blog.xiaoq.in/thumb/cache/2013/9/1313-7.png;http://blog.xiaoq.in/thumb/cache/2013/9/1313-8.png;
categories:
  - Google Analytics
tags:
  - google ved参数
  - not provided
  - VED
  - ved参数
  - 过滤器
  - 高级细分
---
不经意间看到<a title="Decoding Google's Referral String (or, how I surviVED Secure Search)" href="http://moz.com/blog/decoding-googles-referral-string-or-how-i-survived-secure-search" target="_blank">这篇文章</a>，首先让我想起大概2年前鱼励（Adiemusy）的这篇文章：<a title="百度竞价链接bdclkid全解密" href="http://yuli.in/webanalytics/%E7%99%BE%E5%BA%A6%E7%AB%9E%E4%BB%B7%E9%93%BE%E6%8E%A5bdclkid%E5%85%A8%E8%A7%A3%E5%AF%86/" target="_blank">百度竞价链接bdclkid全解密</a>（百度后来取消了该标记），方法类似，前者是对引荐网址进行处理，后者则是对目标网址进行处理。

Google安全搜索越来越多，于是出现了越来越多的(<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/not-provided/" title="查看not provided中的全部文章" target="_blank">not provided</a></span>)，这主要是由于在这种搜索模式下q=参数被去掉了，因此无法从引荐网址中进行解码。不过，cd=和ved=还是有的，前者大多数人应该知道它是识别排名的参数（注：附加链接也算排名的），<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ved%e5%8f%82%e6%95%b0/" title="查看ved参数中的全部文章" target="_blank">ved参数</a></span>则是本文要讨论的。

<img class="alignnone size-full wp-image-1314" alt="vertical search code" src="http://blog.xiaoq.in/cdn/2013/09/vertical-search-code.png" width="558" height="292" />

如果你比较细心，会发现<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ved%e5%8f%82%e6%95%b0/" title="查看ved参数中的全部文章" target="_blank">ved参数</a></span>实际上对应的关系如上，当然还有更多的对应关系，比如面包屑的对应关系如下：

AD = 第一层  
AT = 第二层  
Aj = 第三层

活动：ved = xxxBE0MGM；音乐：ved = xxxQ6hEw。

那么，我们如何获得这些数据，验证这些数据，并且得出有价值的信息呢？这里主要通过GA的高级<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%bf%87%e6%bb%a4%e5%99%a8/" title="查看过滤器中的全部文章" target="_blank">过滤器</a></span>和<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e9%ab%98%e7%ba%a7%e7%bb%86%e5%88%86/" title="查看高级细分中的全部文章" target="_blank">高级细分</a></span>功能来实现。高级<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%bf%87%e6%bb%a4%e5%99%a8/" title="查看过滤器中的全部文章" target="_blank">过滤器</a></span>简单来说就是读取引荐URL中的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ved%e5%8f%82%e6%95%b0/" title="查看ved参数中的全部文章" target="_blank">ved参数</a></span>，拿出来，并且附加到来源的前面；而<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e9%ab%98%e7%ba%a7%e7%bb%86%e5%88%86/" title="查看高级细分中的全部文章" target="_blank">高级细分</a></span>则主要用来对这些特定的ved参数进行归类分组，然后用作筛选和对比。

过滤器的建立方法如下：

<img class="size-full wp-image-1315 aligncenter" alt="ved filter" src="http://blog.xiaoq.in/cdn/2013/09/ved-filter.png" width="720" height="256" />

<p style="text-align: center;">
  按照顺序建立2个高级过滤器
</p>

<p style="text-align: center;">
  <img class="alignnone size-full wp-image-1321" alt="Universal Extract" src="http://blog.xiaoq.in/cdn/2013/09/Universal-Extract4.png" width="491" height="395" />
</p>

<p style="text-align: center;">
  设置第一个过滤器：从引荐URL中提取ved参数
</p>

Field A  (\?|&)(ved)=([^&]*)

Field B (\?|&)(cd)=([^&]*)

<p style="text-align: center;">
  <img class="alignnone size-full wp-image-1322" alt="Universal Display" src="http://blog.xiaoq.in/cdn/2013/09/Universal-Display1.png" width="504" height="414" />
</p>

<p style="text-align: center;">
  设置第二个过滤器：通过自定义字段承接，将第一步获取的ved参数附加到来源中
</p>

<p style="text-align: center;">
  <img class="alignnone size-full wp-image-1323" alt="ved+source" src="http://blog.xiaoq.in/cdn/2013/09/ved+source.png" width="696" height="359" />
</p>

<p style="text-align: center;">
  最终得出来的数据报告
</p>

<p style="text-align: center;">
  <img class="alignnone size-full wp-image-1324" alt="ved advanced segments" src="http://blog.xiaoq.in/cdn/2013/09/ved-advanced-segments.png" width="648" height="350" />
</p>

<p style="text-align: center;">
  基于有规律的参数，建立高级细分
</p>

<p style="text-align: center;">
  <img class="alignnone size-full wp-image-1325" alt="segmented ved report" src="http://blog.xiaoq.in/cdn/2013/09/segmented-ved-report.png" width="529" height="268" />
</p>

<p style="text-align: center;">
  使用高级细分，对比或汇总数据
</p>

<p style="text-align: left;">
  看到这里，你或许会问，这个数据有何意义，对我有何帮助？主要的参考意义如下：
</p>

<li style="text-align: left;">
  更好地评估SEO价值，了解Google网页搜索结果中各个内容来源带来的效果，可以一定程度解密(<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/not-provided/" title="查看not provided中的全部文章" target="_blank">not provided</a></span>)。
</li>
<li style="text-align: left;">
  优化附加链接，因为现在你可以知道用户喜欢点击哪个链接了。同时，如果是ved = xxxxQjB，那么这个肯定是品牌词带来的流量。
</li>
<li style="text-align: left;">
  优化Google 新闻的标题（ved = xxxxQqQIw）和图片（ved = xxxxQpwI）, Google 视频缩略图（ved = xxxxQuAIw）。
</li>
<li style="text-align: left;">
  优化富文本摘要，如面包屑、活动、音乐、价格、库存等。获取更多前所未有的数据，并总结归类出来。
</li>
<li style="text-align: left;">
  如果你正在进行搜索结果抓取，那么加上对这个参数的识别吧！一个抓取工具：<a title="PhantomJS" href="https://github.com/ariya/phantomjs" target="_blank">https://github.com/ariya/phantomjs</a>
</li>

PS：看到搜外论坛的一个帖子，是2011年发的，分析思路很不错：<a href="http://www.seowhy.com/bbs/thread-799946-1-1.html" target="_blank">http://www.seowhy.com/bbs/thread-799946-1-1.html</a>，不过使用本文的方法，你可以很好的分类汇总数据来进行分析，如果想研究其他参数也可使用类似方法。再附上提取完整引荐URL的过滤器设置如下：

<img class="alignnone size-full wp-image-1327" alt="full referral filter" src="http://blog.xiaoq.in/cdn/2013/09/full-referral-filter.png" width="700" height="450" />

最后温馨提示下，过滤器一定记得新建配置文件来设置，欢迎评论补充你发现的其他对应关系。

&nbsp;