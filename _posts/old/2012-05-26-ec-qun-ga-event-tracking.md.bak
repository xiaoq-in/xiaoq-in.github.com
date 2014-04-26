---
title: EC客户通GA事件跟踪代码解析
author: 肖庆
layout: post
permalink: /google-analytics/ec-qun-ga-event-tracking/
sina_t:
  - 'true'
ratings_users:
  - 1
ratings_score:
  - 5
ratings_average:
  - 5
views:
  - 2191
yourls_shorturl:
  - http://t.xiaoq.in/3u
ta-thumbnail:
  - NoMediaFound
categories:
  - Google Analytics
tags:
  - .eq()
  - .live()
  - EC客户通
  - JavaScript控制台
  - jQuery
  - 事件跟踪
  - 商务通
---
首先声明，**<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ec%e5%ae%a2%e6%88%b7%e9%80%9a/" title="查看EC客户通中的全部文章" target="_blank">EC客户通</a></span>的GA<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>代码并非本人所写**，代码的作者是我在上家公司<a href="http://www.teamtopseo.com/" title="天拓SEO" target="_blank">天拓</a>的一位技术同事所写，参照了cloga的这篇文章：<a href="http://www.cloga.info/archives/1446.html" title="使用GA监测商务通等在线客服的对话" target="_blank">使用GA监测商务通等在线客服的对话</a>。

EC是深圳市六度人和科技有限公司开发的一款在线客服系统，曾经获得腾讯的天使投资，现今被众多企业所使用。

目标设置是进行任何网络推广的第一步，对于大大多数企业网站来说，最为关键的目标就是在线咨询数，我们或许能够在一些在线咨询软件中看到关于咨询者的一些数据，比如来源IP，咨询时间，用户的计算机分辨率等数据，有些软件还能看到关键词等数据，但是如何把这些数据与我们的推广活动进行贯通，则需要借助于我们的一些高级配置。

在这里，我们就是使用<span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>对网站内各个在线咨询按钮的点击情况进行跟踪，这些数据可以在热点事件中查看，并且我们可以进一步对这些事件设置为目标。

以下是<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ec%e5%ae%a2%e6%88%b7%e9%80%9a/" title="查看EC客户通中的全部文章" target="_blank">EC客户通</a></span>的GA<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>代码：

/\* ec客服监听点击 \*/  
(function() {  
$(&#8216;#ec\_cs\_pannel\_mid .ec\_qq:eq(0)&#8217;).live(&#8216;click&#8217;, function() {  
\_gaq.push(['\_trackEvent', 'chat', 'qq', 'soso-huang',1,true]);  
});  
$(&#8216;#ec\_cs\_pannel\_mid .ec\_qq:eq(1)&#8217;).live(&#8216;click&#8217;, function() {  
\_gaq.push(['\_trackEvent', 'chat', 'qq', 'soso-zhou',1,true]);  
});  
$(&#8216;#ec\_cs\_pannel\_mid .ec\_qq:eq(2)&#8217;).live(&#8216;click&#8217;, function() {  
\_gaq.push(['\_trackEvent', 'chat', 'qq', 'soso-chu',1,true]);  
});  
$(&#8216;#ec\_cs\_pannel_mid div:eq(0) span&#8217;).live(&#8216;click&#8217;, function() {  
\_gaq.push(['\_trackEvent', 'chat', 'left', 'soso-huang',1,true]);  
});  
$(&#8216;#ec\_cs\_pannel_mid div:eq(1) span&#8217;).live(&#8216;click&#8217;, function() {  
\_gaq.push(['\_trackEvent', 'chat', 'left', 'soso-zhou',1,true]);  
});  
$(&#8216;#ec\_cs\_pannel_mid div:eq(2) span&#8217;).live(&#8216;click&#8217;, function() {  
\_gaq.push(['\_trackEvent', 'chat', 'left', 'soso-chu',1,true]);  
});  
})();

我并未系统学习过任何代码，就参照网上的一些教程，进行了如下通俗解释：  
这段代码主要使用了jquery的两个函数，<a href="http://www.w3school.com.cn/jquery/traversing_eq.asp" title=".eq()" target="_blank">.eq()</a>和<a href="http://www.w3school.com.cn/jquery/event_live.asp" title=".live()" target="_blank">.live()</a>。首先使用<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/jquery/" title="查看jQuery中的全部文章" target="_blank">jQuery</a></span> 选择器选择div id=ec\_css\_pannel\_mid中class为ec\_qq的元素，以及内部div中的span元素，然后再使用<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/eq/" title="查看.eq()中的全部文章" target="_blank">.eq()</a></span>遍历各个元素，并通过<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/live/" title="查看.live()中的全部文章" target="_blank">.live()</a></span>附加上trackEvent的点击事件。至于这些元素的获取，你可将鼠标放在相应的按钮上，然后使用谷歌浏览器的“工具-<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/javascript%e6%8e%a7%e5%88%b6%e5%8f%b0/" title="查看JavaScript控制台中的全部文章" target="_blank">JavaScript控制台</a></span>”来查看。

作为一个数据分析师，你没有必要懂得写代码，你只需要把你的思路告诉技术人员，由他们帮你实现，然后你再负责监控效果。当然，如果能够看懂一些基本的代码，也是大有裨益的。