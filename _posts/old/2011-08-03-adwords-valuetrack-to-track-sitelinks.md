---
title: 善用GA与ValueTrack跟踪广告附加链接
author: 54jack
layout: post
permalink: /google-analytics/adwords-valuetrack-to-track-sitelinks/
sina_t:
  - 'true'
views:
  - 1092
  - 1092
qq_t:
  - 'true'
ratings_users:
  - 1
ratings_score:
  - 5
ratings_average:
  - 5
duoshuo_thread_id:
  - 511912
yourls_shorturl:
  - http://t.xiaoq.in/6r
ta-thumbnail:
  - NoMediaFound
categories:
  - Google AdWords
  - Google Analytics
tags:
  - Google AdWords
  - Google Analytics
  - ValueTrack
  - 广告附加链接
  - 百度蹊径
---
<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/valuetrack/" title="查看ValueTrack中的全部文章" target="_blank">ValueTrack</a></span> 是一种简单易用的 AdWords 网址标记功能。通过此功能，您可以获得有关广告所收到的每次点击的详细数据，并将其用于您自己的跟踪解决方案。您可以使用这些信息来调整定位条件，从而优化投资回报率。<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/valuetrack/" title="查看ValueTrack中的全部文章" target="_blank">ValueTrack</a></span> 目前可提供 14 种用于标记目标网址的参数。详细的信息可以查看：<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-adwords/" title="Google Adwords" target="_blank">Google Adwords</a></span>的<a title="ValueTrack 概述" href="http://adwords.google.com/support/aw/bin/answer.py?hl=zh-Hans&answer=178482" target="_blank">ValueTrack 概述</a>。

我们知道，Google Adwords中可以添加10个<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%b9%bf%e5%91%8a%e9%99%84%e5%8a%a0%e9%93%be%e6%8e%a5/" title="查看广告附加链接中的全部文章" target="_blank">广告附加链接</a></span>，当广告Google搜索结果的左侧（上下均可）广告位时，可以显示2个，4个或者6个（最多）。如果你还提交了附加地址信息，还可同时Google地图。具体显示效果如下：

<img class="alignnone size-full wp-image-521" title="sitelinks-absen" src="http://blog.xiaoq.in/cdn/images/2011/08/sitelinks-absen.gif" alt="" width="550" />

（PS：这个功能相当于百度推广中的蹊径，之前是要提交给客服审核添加，现在百度凤巢新版中也加上了后台自主添加的功能，据说完全切换过来需要等到9月1日。<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%99%be%e5%ba%a6%e8%b9%8a%e5%be%84/" title="查看百度蹊径中的全部文章" target="_blank">百度蹊径</a></span>的子链文字比较短，整个就是在一行显示；而谷歌可以允许35个字符，相当于一行描述的字符长度。）

Google默认情况下只会统计广告附加信息的整体点击和展示情况，无法提供具体某个链接的数据。在帮助中心中我们找到了如下说明文字：

<p style="padding-left: 30px;">
  <strong><span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%b9%bf%e5%91%8a%e9%99%84%e5%8a%a0%e9%93%be%e6%8e%a5/" title="查看广告附加链接中的全部文章" target="_blank">广告附加链接</a></span></strong>：每一行都会显示与一组附加链接相关的数据。目前我们无法提供具体链接一级的数据。此外，如果您修改了任何<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%b9%bf%e5%91%8a%e9%99%84%e5%8a%a0%e9%93%be%e6%8e%a5/" title="查看广告附加链接中的全部文章" target="_blank">广告附加链接</a></span>中的链接或链接文字，此项广告信息附加功能的统计信息将重置为零。
</p>

<p style="padding-left: 30px;">
  <strong>点击次数</strong>：您的广告在与所选附加信息一起展示时所获得的点击次数。对广告标题的点击次数，以及对广告附加信息（如果有）的点击次数都包括在其中。目前，您无法单独查看广告附加信息的点击次数（对广告标题的点击次数未滤除）。例如，假设某广告附加信息与某广告一起展示了 10 次。在二者这 10 次一起展示中，广告标题获得了 2 次点击，广告附加信息获得了 3 次点击。系统会报告以下数字：
</p>

*   点击次数 = 5
*   展示次数 = 10
*   点击率 = 50%

这样的统计数据是不完整的，我们无法得知某个子链接的点击情况，无法得知访问者是通过何种途径进入了我们的网站，因此，如果您想优化子链接，可能会无从下手。

因此，翻看帮助中心看到这么一篇文章：<a title="是否可以在关键字一级跟踪广告附加链接？" href="http://adwords.google.com/support/aw/bin/answer.py?hl=zh-Hans&answer=190706" target="_blank"> 是否可以在关键字一级跟踪广告附加链接？</a> 答案当然是可以的。但是这种做法是有弊端的，因为你必须再去重新定义广告系列自定义字段。这样的话，为了保证其他数据不受干扰，你可能还需要再创建一个account，增加一段代码，然后再添加到网站的模板文件中，重新生成。烦，乱，浪费时间。它生成的链接最终效果是这样的：

[www.absen.cn/a-display.html?origin=sitelinks&keyword={keyword}&matchtype={matchtype}&creative={creative}&sitelink=01][1]

后来细看了一下，以上说的重新定义广告系列字段其实就可以通过替换标记参数一步搞定。

最终广告附加链接的标记如下：

[www.absen.cn/a-display.html?utm\_source=sitelinks&utm\_term={keyword}&utm\_medium={matchtype}&utm\_campaign={creative}&utm_content=01][2]

utm_source=sitelinks：来源为广告附加链接

utm_term={keyword}：搜索关键词

utm_medium={matchtype}：匹配方式（分别为&#8221;b&#8221;代表广泛匹配、&#8221;p&#8221;代表词组匹配、&#8221;e&#8221;代表完全匹配）

utm_campaign={creative}：广告创意ID

utm_content=01：第几个子链接

上述代码部署完毕之后，过几个小时你就可以在<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>的**广告系列**中查看子链接访问的详细信息，有了数据再做优化，简单多了。

&nbsp;

 [1]: http://www.absen.cn/a-display.html?origin=sitelinks&keyword={keyword}&matchtype={matchtype}&creative={creative}&sitelink=01
 [2]: http://www.absen.cn/a-display.html?utm_source=sitelinks&utm_term={keyword}&utm_medium={matchtype}&utm_campaign={creative}&utm_content=01