---
title: 使用网站速度分析报告测量页面加载速度
author: 54jack
layout: post
permalink: /sem/measure-page-load-time-with-site-speed/
sina_t:
  - 'true'
views:
  - 1024
  - 1024
qq_t:
  - 'true'
duoshuo_thread_id:
  - 511880
yourls_shorturl:
  - http://t.xiaoq.in/6e
ta-thumbnail:
  - NoMediaFound
categories:
  - 搜索引擎营销
tags:
  - 加载速度
  - 新版谷歌分析
  - 网站速度
  - 网站速度分析报告
  - 自定义报告
  - 谷歌分析
  - 跟踪代码
  - 页面速度
---
<div>
  <em>This is part of our <a href="http://analytics.blogspot.com/search/label/New%20Google%20Analytics?utm_source=gablog&utm_medium=blog&utm_campaign=newga-blog&utm_content=sitespeed">series of posts</a> highlighting <a href="http://analytics.blogspot.com/2011/03/looking-towards-future-of-google.html?utm_source=gablog&utm_medium=blog&utm_campaign=newga-blog&utm_content=sitespeed">the new Google Analytics</a>. The new version of <span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span> is currently available in beta to all Analytics users. And <a href="http://twitter.com/#!/googleanalytics">follow Google Analytics on Twitter for the latest updates</a>. This week we’re sharing a new feature, the Site Speed report.</em>
</div>

<div>
  <em>这是我们新版<span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="谷歌分析" target="_blank">谷歌分析</a></span>专题系列的一部分。<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e6%96%b0%e7%89%88%e8%b0%b7%e6%ad%8c%e5%88%86%e6%9e%90/" title="查看新版谷歌分析中的全部文章" target="_blank">新版谷歌分析</a></span>现在对所有<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%b0%b7%e6%ad%8c%e5%88%86%e6%9e%90/" title="查看谷歌分析中的全部文章" target="_blank">谷歌分析</a></span>用户都开放测试版本了。你可以追随我们的twitter获取最新更新。本周我们分析一个新功能：<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%bd%91%e7%ab%99%e9%80%9f%e5%ba%a6/" title="查看网站速度中的全部文章" target="_blank">网站速度</a></span>报告。</em>
</div>

<div>
  At Google, <a href="http://www.youtube.com/watch?v=IWWBnJEsUtU&feature=player_embedded#at=19">we are passionate about speed and making the web faster</a>, and we are glad to see that many website owners share the same idea. A faster web is better for both users and businesses. A slow loading landing page not only impacts your conversion rate, but can also impact <a href="http://adwords.google.com/support/aw/bin/answer.py?hl=en&answer=87144">AdWords Landing Page Quality</a> and <a href="http://googlewebmastercentral.blogspot.com/2010/04/using-site-speed-in-web-search-ranking.html">ranking in Google search</a>.
</div>

<div>
  在谷歌，我们对速度充满激情并不断使网络更快，我们非常高兴第看到很多网站主跟我们的观点是一致的。更快的网站同时有利于用户及企业。缓慢加载的着陆页面不仅影响转化率，同时也会影响Adwords的着陆页面质量及其在谷歌搜索中的排名。
</div>

<div>
  To improve the performance of your pages, you first need to measure and diagnose the speed of a page, which can be a difficult task. Furthermore, even with page speed measurements, it’s critical to look at page speed in context of other web analytics data.
</div>

<div>
  为了提升你网页的表现，你首先需要测量及诊断一个页面的速度，这会是一个很艰难的任务。而且，测量<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e9%a1%b5%e9%9d%a2%e9%80%9f%e5%ba%a6/" title="查看页面速度中的全部文章" target="_blank">页面速度</a></span>，在其他分析数据的环境中查看是非常重要的。
</div>

<div>
  Therefore, we are thrilled to announce the availability of the Site Speed report in the <a href="http://analytics.blogspot.com/2011/04/new-google-analytics-available-to.html?utm_source=gablog&utm_medium=blog&utm_campaign=newga-blog&utm_content=sitespeed">new Google Analytics platform</a>. With the Site Speed report you can measure the page load time across your site.
</div>

<div>
  因此，我们激动第宣布<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%bd%91%e7%ab%99%e9%80%9f%e5%ba%a6/" title="查看网站速度中的全部文章" target="_blank">网站速度</a></span>报告在<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e6%96%b0%e7%89%88%e8%b0%b7%e6%ad%8c%e5%88%86%e6%9e%90/" title="查看新版谷歌分析中的全部文章" target="_blank">新版谷歌分析</a></span>平台中已经可用了。通过<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%bd%91%e7%ab%99%e9%80%9f%e5%ba%a6/" title="查看网站速度中的全部文章" target="_blank">网站速度</a></span>报告，你可用测量网站所有页面的加载时间。
</div>

<div>
  <strong>Uses for the Site Speed Report</strong>
</div>

<div>
  <strong>网站速度报告使用</strong>
</div>

<div>
  <ul>
    <li>
      Content: Which landing pages are slowest?内容：哪些着陆页面是最慢的？
    </li>
    <li>
      Traffic sources: Which campaigns correspond to faster page loads overall?流量来源：哪个广告系列对应更快的页面加载？
    </li>
    <li>
      Visitor: How does page load time vary across geographies?访客：页面加载时间在不同地区有何差异？
    </li>
    <li>
      Technology: Does your site load faster or slower for different browsers?技术：你的网站是否在不同浏览器中<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%8a%a0%e8%bd%bd%e9%80%9f%e5%ba%a6/" title="查看加载速度中的全部文章" target="_blank">加载速度</a></span>有快有慢？
    </li>
  </ul>
</div>

<div>
  One effective use of the Site Speed report is to measure speed for your most critical pages. For example, you might learn that the target audience of your site is located in a geographic region that experiences slower page speed. Or, you might learn that certain pages on your site run slower in some browsers. In addition to the Site Speed report, we’ve created a custom report that you can use to help answer these questions: <a href="http://goo.gl/MBofH">view the Site Speed custom report</a>.
</div>

<div>
  <a href="http://4.bp.blogspot.com/-RoXO31TXnJE/TcCHhjJbQuI/AAAAAAAABNk/So-Ra5CM6Dc/s1600/galt_blog.png"></a>
</div>

<div>
  网站速度报告的一个高效应用是测量你最重要页面的速度。比如，你可能知道你网站目标客户来自某个经历着网站页面加载缓慢的地理位置。或者你可能知道你网站上面的某些页面在某些浏览器中运行缓慢。除了网站速度报告，我们还创建了一个<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e6%8a%a5%e5%91%8a/" title="查看自定义报告中的全部文章" target="_blank">自定义报告</a></span>，你可以用它来帮助回答这些问题：查看网站速度<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e6%8a%a5%e5%91%8a/" title="查看自定义报告中的全部文章" target="_blank">自定义报告</a></span>。
</div>

<div>
  <strong> </strong> 
</div>

<div>
  <strong><img class="alignnone size-full wp-image-404" title="galt_blog" src="http://cdn.54jack.com/images/2011/05/galt_blog.png" alt="" width="400" height="246" /></strong>
</div>

<div>
  <strong>Setting up the Site Speed Report</strong>
</div>

<div>
  <strong>设置网站速度报告</strong>
</div>

<div>
  By default, page speed measurement is turned off, so you’ll only see 0’s in the Site Speed report until you’ve enabled it. To start measuring site speed, you need to make a small change to your Analytics tracking code. We have detailed instructions in the <a href="http://www.google.com/support/analyticshelp/bin/answer.py?hl=en&answer=1205784&topic=1120718&utm_source=gablog&utm_medium=blog&utm_campaign=newga-blog&utm_content=sitespeed">Site Speed article in the Analytics Help Center</a>. Once you’ve updated your tracking code, a small sample of pageviews will be used to calculate the page load time.
</div>

<div>
  默认情况下，网页速度报告测量是关闭的，因此在开启它之前，你将只能在网站速度报告中看到“0”。为了开赛测量网站速度，你需要对分析<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%b7%9f%e8%b8%aa%e4%bb%a3%e7%a0%81/" title="查看跟踪代码中的全部文章" target="_blank">跟踪代码</a></span>做一个小的更改。我们在分析帮助中心中有关于网站速度的详细指南。
</div>

<div>
  We’re excited to bring this important metric into Google Analytics as part of the new Google Analytics platform. Please continue to <a href="https://services.google.com/fb/forms/newanalyticsfeedback/?utm_source=gablog&utm_medium=blog&utm_campaign=newga-blog&utm_content=sitespeed">send us feedback</a> on Site Speed and the rest of the new Google Analytics.
</div>

<div>
  我们非常兴奋带来了这个重要的指标到<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%b0%b7%e6%ad%8c%e5%88%86%e6%9e%90/" title="查看谷歌分析中的全部文章" target="_blank">谷歌分析</a></span>中，使之成为新版<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%b0%b7%e6%ad%8c%e5%88%86%e6%9e%90/" title="查看谷歌分析中的全部文章" target="_blank">谷歌分析</a></span>平台的一部分。情继续给我们发送关于网站速度及谷歌分析新版其他问题的反馈。
</div>

<div>
  By Zhiheng Wang, Phil Mui on behalf of the Google Analytics team and the Make the Web Faster team.
</div>

<div>
  作者：王志恒（音译），Phil Mui，代表谷歌分析小组及网站加速小组
</div>

<div>
  <span class='wp_keywordlink'><a href="http://www.yeezhe.com/" title="译者" target="_blank">译者</a></span>：<span class='wp_keywordlink'><a href="https://xiaoq.in/" title="肖庆" target="_blank">肖庆</a></span>。
</div>

<div>
  谷歌分析官方博客原文：<a title="使用网站速度分析报告测量网页加载速度" href="http://analytics.blogspot.com/2011/05/measure-page-load-time-with-site-speed.html?utm_source=feedburner&utm_medium=feed&utm_campaign=54jack.com" target="_blank">http://analytics.blogspot.com/2011/05/measure-page-load-time-with-site-speed.html?utm_source=feedburner&utm_medium=feed&utm_campaign=54jack.com</a>
</div>

Posted by Trevor Claiborne, Google Analytics Team

由谷歌分析小组Trevor Claiborne发表。