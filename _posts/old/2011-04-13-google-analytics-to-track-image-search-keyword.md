---
title: 谷歌分析跟踪图片搜索关键词
author: 54jack
layout: post
permalink: /google-analytics/google-analytics-to-track-image-search-keyword/
sina_t:
  - 'true'
views:
  - 922
  - 922
qq_t:
  - 'true'
duoshuo_thread_id:
  - 511777
yourls_shorturl:
  - http://t.xiaoq.in/5c
ta-thumbnail:
  - NoMediaFound
categories:
  - Google Analytics
tags:
  - sitemap
  - WordPress
  - 图片搜索
  - 图片营销
  - 外贸营销
  - 整合营销
  - 正则表达式
  - 谷歌分析
---
谷歌目前有多款产品，网页搜索只是其中的一个方面，在这个角度或许我们的竞争过于激烈，那么扩展一下你的搜索着陆点不愧是一个很好的方式。

谷歌<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%9b%be%e7%89%87%e6%90%9c%e7%b4%a2/" title="查看图片搜索中的全部文章" target="_blank">图片搜索</a></span>的市场占有率还是比较大的，左侧位置仅次于所有结果，如果能够抓住这个窗口，必能获得不少额外流量，并且如果用户搜索相关产品图片时，发现上面都是你公司的，带有你们的logo，这岂不是一个很好的营销手段？  
<img src="http://cdn.54jack.com/images/2011/04/google-images.gif" alt="" title="google images" width="500" height="215" class="alignnone size-full wp-image-250" />

那么，<span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="谷歌分析" target="_blank">谷歌分析</a></span>是非常强大的，通过以下的代码改造可以显示谷歌<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%9b%be%e7%89%87%e6%90%9c%e7%b4%a2/" title="查看图片搜索中的全部文章" target="_blank">图片搜索</a></span>的关键词。鉴于各人的写法不一样，贴上以下代码仅供参考，如果你懂<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e6%ad%a3%e5%88%99%e8%a1%a8%e8%be%be%e5%bc%8f/" title="查看正则表达式中的全部文章" target="_blank">正则表达式</a></span>，尝试自己再写一个百度图片搜索或者Bing等更多的搜索引擎的图片搜索关键词跟踪代码，是一个很好的学习机会。

var ref = document.referrer;  
if (ref.search(/images.google/) != -1 &#038;&#038; ref.search(/prev/) != -1) {  
var regex = new RegExp(&#8220;images.google.([^/]+).*&#038;prev=([^&#038;]+)&#8221;);  
var match = regex.exec(ref);  
\_gaq.push(['\_clearOrganic']);  
\_gaq.push(['\_addOrganic','images.google.'+match[1],&#8217;q&#8217;]);  
\_gaq.push(['\_setReferrerOverride', 'http://images.google.'+match[1]+unescape(match[2])]);  
}

pageTracker._initData();  
// Change the referrer to have the right keyword in it  
if (pageTracker.qa.search(/images.google/) != -1 &#038;&#038;  
pageTracker.qa.search(/prev/) != -1) {  
regex = new RegExp(&#8220;images.google.([^/]+).*&#038;prev=([^&#038;]+)&#8221;);  
var match = regex.exec(pageTracker.qa);  
pageTracker.qa = &#8220;http://images.google.&#8221; + match[1] + unescape(match[2]);  
}

var ref = document.referrer;  
if (ref.search(/images.google/) != -1 &#038;&#038; ref.search(/prev/) != -1) {  
var regex = new RegExp(&#8220;images.google.([^/]+).*&#038;prev=([^&#038;]+)&#8221;);  
var match = regex.exec(ref);  
\_gaq.push(['\_clearOrganic']);  
\_gaq.push(['\_addOrganic','images.google.'+match[1],&#8217;q&#8217;]);  
\_gaq.push(['\_setReferrerOverride', 'http://images.google.'+match[1]+unescape(match[2])]);  
}

pageTracker._initData();  
var ref = document.referrer;  
if (ref.search(/images.google/) != -1 &#038;&#038; ref.search(/prev/) != -1) {  
var regex = new RegExp(&#8220;images.google.([^/]+).*&#038;prev=([^&#038;]+)&#8221;);  
var match = regex.exec(ref);  
pageTracker._clearOrganic();  
pageTracker._addOrganic(&#8220;images.google.&#8221;+ match[1],&#8221;q&#8221;);  
pageTracker._setReferrerOverride(&#8220;http://images.google.&#8221; + match[1] + unescape(match[2]));  
}

var ref = document.referrer;  
if (ref.search(/(images|www).google.([^/]+)/(images|imghp|imgres|imglanding)/) != -1 &#038;&#038; ref.search(/prev/) != -1) {  
var regex = new RegExp(&#8220;google.([^/]+)/.*&#038;prev=([^&#038;]+)&#038;&#8221;),  
var match = regex.exec(ref);

\_gaq.push(['\_addOrganic','images.google.'+match[1]+,&#8217;q&#8217;,true]);  
\_gaq.push(['\_setReferrerOverride', 'http://images.google.'+match[1]+unescape(match[2])]);  
}

网上看到的几种代码（其中有两组分别适用于老版本和异步跟踪版本），建议用最后一种，因为谷歌图片搜索的地址可以通过不同网站访问。  
<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/wordpress/" title="查看WordPress中的全部文章" target="_blank">WordPress</a></span>有一个非常不错的插件，叫做Google XML Sitemap for Images，可以生成图片的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/sitemap/" title="查看sitemap中的全部文章" target="_blank">sitemap</a></span>.xml，可以用来在谷歌站长工具中提及给谷歌搜索引擎爬虫。<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/wordpress/" title="查看WordPress中的全部文章" target="_blank">WordPress</a></span>是无所不能的，哈哈。