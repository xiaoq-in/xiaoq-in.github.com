---
title: 谷歌分析第五版诞生记
author: 54jack
layout: post
permalink: /google-analytics/making-of-google-analytics-v5/
sina_t:
  - 'true'
views:
  - 891
  - 891
qq_t:
  - 'true'
duoshuo_thread_id:
  - 511890
yourls_shorturl:
  - http://t.xiaoq.in/6l
ta-thumbnail:
  - NoMediaFound
categories:
  - Google Analytics
tags:
  - 新版谷歌分析
  - 智能事件报告
  - 概览报告
  - 第五版
  - 网站速度报告
---
<div>
  <em><span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="谷歌分析" target="_blank">谷歌分析</a></span><span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%ac%ac%e4%ba%94%e7%89%88/" title="查看第五版中的全部文章" target="_blank">第五版</a></span>是如何诞生的，看看谷歌分析小组成员是如何评述的吧。<a title="谷歌分析第五版诞生记" href="http://analytics.blogspot.com/2011/06/making-of-google-analytics-v5.html" target="_blank">谷歌分析新版史话</a>，敬请关注本文视频中文翻译的更新。</em>
</div>

<div>
  <em><em>This is part of our <a href="http://analytics.blogspot.com/search/label/New%20Google%20Analytics?utm_source=gablog&utm_medium=blog&utm_campaign=newga-blog&utm_content=makingof">series of posts</a> highlighting the <a href="http://analytics.blogspot.com/2011/03/looking-towards-future-of-google.html?utm_source=gablog&utm_medium=blog&utm_campaign=newga-blog&utm_content=makingof">new Google Analytics</a>. The new version of <span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span> is currently available in beta to all Analytics users. And <a href="http://twitter.com/#!/googleanalytics">follow Google Analytics on Twitter</a> for the latest updates. This week we’re sharing a few new features in our Intelligence reports.</em></em>
</div>

<div>
  <em><em></em></em>这是我们<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e6%96%b0%e7%89%88%e8%b0%b7%e6%ad%8c%e5%88%86%e6%9e%90/" title="查看新版谷歌分析中的全部文章" target="_blank">新版谷歌分析</a></span>专题系列文章的一部分。<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e6%96%b0%e7%89%88%e8%b0%b7%e6%ad%8c%e5%88%86%e6%9e%90/" title="查看新版谷歌分析中的全部文章" target="_blank">新版谷歌分析</a></span>现已对所有谷歌分析师用户开放。请追随我们的Twitter以获得最近更新。本周我们分享了<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e6%99%ba%e8%83%bd%e4%ba%8b%e4%bb%b6%e6%8a%a5%e5%91%8a/" title="查看智能事件报告中的全部文章" target="_blank">智能事件报告</a></span>的一些新功能。
</div>

<div>
  <div>
    Since we launched the new Google Analytics, we&#8217;ve been talking to many of you about the new version, and <a href="https://services.google.com/fb/forms/newanalyticsfeedback/?utm_source=gablog&utm_medium=blog&utm_campaign=newga-blog&utm_content=makingof">getting your feedback</a>. One question we got was about our goals for the new version and why we made the changes we did. So, we got a few members of the Google Analytics team together to share their stories of how the new version began, our approach, and our goals in building it. Along the way, they also share a bit about what you can expect in the future from Google Analytics.
  </div>
  
  <div>
    自启动新版谷歌分析以来，我们就一直与你们中的众多进行新版的一些交流，并且获得了一些反馈。其中一个问题是，我们对新版的一个目标以及我们为什么做出这些改变。因此，我们集合了一些谷歌分析小组的成员来分享他们的故事，其中涉及新版如何开始，我们的途径以及建立新版的目标。同时，他们还分享了你们可以从未来谷歌分析中期待的一些东西。
  </div>
</div>

<div>
  <strong>The Making of Google Analytics v5</strong>
</div>

<div>
  <strong></strong>谷歌分析<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%ac%ac%e4%ba%94%e7%89%88/" title="查看第五版中的全部文章" target="_blank">第五版</a></span>诞生记
</div>

<div>
  <span style="color: #ff6600;">（视频待译）</span>
</div>

<div>
  We also put together a second video where the team runs through a few of the many new features in Google Analytics v5:
</div>

<div>
  我们还制作了另一个视频，我们小组成员运行了谷歌分析<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%ac%ac%e4%ba%94%e7%89%88/" title="查看第五版中的全部文章" target="_blank">第五版</a></span>中的一些新功能。
</div>

<div>
  <span style="color: #ff6600;">（视频待译）</span>
</div>

<div>
  You can find more information on many of these in the <a href="http://analytics.blogspot.com/search/label/New%20Google%20Analytics?utm_source=gablog&utm_medium=blog&utm_campaign=newga-blog&utm_content=makingof">New Google Analytics blog series</a>including a few that aren’t mentioned in the video like <a href="http://analytics.blogspot.com/2011/05/measure-page-load-time-with-site-speed.html?utm_source=gablog&utm_medium=blog&utm_campaign=newga-blog&utm_content=makingof">Site Speed</a> and <a href="http://analytics.blogspot.com/2011/05/new-google-analytics-overview-reports.html?utm_source=gablog&utm_medium=blog&utm_campaign=newga-blog&utm_content=makingof">new overview reports</a>. And like Sagnik says at the end of the video, there’s much more to come in Google Analytics. Stay tuned!
</div>

<div>
  你还可以在这个新版谷歌分析系列博文中找到更多信息，包括一些没有在这个视频中提及的，如网站速度，新<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e6%a6%82%e8%a7%88%e6%8a%a5%e5%91%8a/" title="查看概览报告中的全部文章" target="_blank">概览报告</a></span>。正如Sagnik在本视频结尾处说得，谷歌分析还会有更多惊喜。敬请关注！
</div>

<div>
</div>