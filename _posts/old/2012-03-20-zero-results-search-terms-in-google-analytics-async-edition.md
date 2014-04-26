---
title: 搜索无结果关键词跟踪（GA异步版）
author: 肖庆
layout: post
permalink: /google-analytics/zero-results-search-terms-in-google-analytics-async-edition/
sina_t:
  - 'true'
ratings_users:
  - 0
ratings_score:
  - 0
ratings_average:
  - 0
views:
  - 3591
duoshuo_thread_id:
  - 648140
yourls_shorturl:
  - http://t.xiaoq.in/5v
ta-thumbnail:
  - http://blog.xiaoq.in/thumb/cache/2012/3/714-1.gif;
categories:
  - Google Analytics
tags:
  - 事件跟踪
  - 搜索字词
  - 搜索跟踪
  - 网站搜索
  - 自定义变量
---
最近遇到的一个问题，在GA帮助中心找到<a href="http://support.google.com/analytics/bin/answer.py?hl=zh-Hans&hlrm=en&answer=1645406" target="_blank">相关介绍</a>，却没有中文版的，于是翻译了一下（JUSTIN CUTRONI曾在09年写过<a href="http://cutroni.com/blog/2009/09/08/tracking-ero-result-searches-in-google-analytics/" target="_blank">一篇文章</a>，思路与下面的类似，但仅适用于旧版本的GA代码；<a href="http://www.fulcrumtech.net/blog/using-google-analytics-to-track-zero-results-found-for-site-searches/" target="_blank">这篇文章</a>采取的是<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>方式）：

<img class="alignnone size-full wp-image-715" title="zero-result" src="http://xiaoq.in/g/pics/2012/03/zero-result.gif" alt="" width="360" height="300" />

介绍

为什么需要跟踪搜索无结果关键词？因为，它是可执行的！

内部搜索是收集潜在客户反馈的最佳位置。他们来到你的网站，并且告诉你：

*   他们希望在那里找到什么；
*   他们在哪里放弃导航而是用搜索功能。

但是，如果看到一个空白的搜索页面，他们会怎么做呢？有些用户可能尝试优化搜索词，但是我想说这对于提升整体用户体验实在是没有任何好处的。

这可能也是提醒你做以下改善的信号：

*   发布目前不存在的内容；
*   稍微对写作方式做些改变，选用不同词进行写作
*   或者对这些搜索尝试使用人工添加的结果。

## 前提

这篇文章意在介绍可能的解决方案，使用的是更新的异步版本GA跟踪代码，代码放置在网站的head区域。

GA默认情况下并不会提供这个报告。因此，我们将不得不做一些额外的工作来实现这个目的。首先需要做的是确保你能够用程序自动识别搜索结果为零的页面。``

其次，你必须能够对GA跟踪代码进行一些改造或者包含一段额外的JavaScript代码到被跟踪页面。

## 可供考虑的选项

你当然不想使用一个额外的`_trackPageview请求，因为这会污染你的数据（特别是每次访问页数指标）。`

在某些情况下，你其实可能能够修改被跟踪URL，但是这仅能够在某些特定的内容管理系统中实现，它们可以将所有来自该页面的变量传递到所生成页面的任意模板片段中。如果有这种功能的话，那么你可以如<a href="http://cutroni.com/blog/2009/09/08/tracking-ero-result-searches-in-google-analytics/" target="_blank">这篇文章</a>中描述的那样操作被跟踪URL。产生的代码类似这样：

<pre>&lt;script type="text/javascript"&gt;
       var _gaq = _gaq || [],
             p = document.location.pathname,
             s = document.location.search;

       _gaq.push(['_setAccount', 'UA-15436952-1']);
&lt;? if (resultsCount == 0) { ?&gt;
       _gaq.push(['_trackPageview', p + s + '&category=no-results']);
&lt;? } else {?&gt;
       _gaq.push(['_trackPageview']);
&lt;? } ?&gt;
       (function() {
             ...you know this part...
       })();
&lt;/script&gt;</pre>

然后，你可以按照Justin的文章中的说明进行站内搜索功能的配置。

如果你还没用如此好用的CMS，你仍然可以测量一些额外的数据，只需使用GA的以下两个功能：

### <span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>

这种方法已经在Bob Scavilla的<a href="http://www.fulcrumtech.net/blog/using-google-analytics-to-track-zero-results-found-for-site-searches/" target="_blank">这篇文章</a>中介绍过。我只想说如果确切的搜索词能够由CMS生成的话，那么你就不必为使用正则表达式而烦恼了。使用CMS系统的话，结果页面的代码类似下面，较为简单：

<pre>&lt;? if (resultsCount == 0) { ?&gt;
&lt;script type="text/javascript"&gt;
       _gaq.push([
              '_trackEvent',
              'Search',
              'No-results',
              '&lt;?=$searchTerm?&gt;'
       ]);
&lt;/script&gt;
&lt;? } ?&gt;</pre>

### <span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>

The first thing you can do is to use a page-level custom variable. You can store the actual zero results search terms like this:你可要做的第一件事情便是使用页面级<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>。你可要像这样存储确切的零结果搜索词：

<pre>&lt;? if (resultsCount == 0) { ?&gt;
&lt;script type="text/javascript"&gt;
       _gaq.push([
       		'_setCustomVar',
		1,
		'No-results',
		'&lt;?=$searchTerm?&gt;',
		3
	]);
&lt;/script&gt;
&lt;? } ?&gt;</pre>

或者，你可以存储特定的搜索次数：

<pre>&lt;script type="text/javascript"&gt;
       _gaq.push([
       		'_setCustomVar',
		1,
		'Results-count',
		'&lt;?=$resultsCount?&gt;',
		3
	]);
&lt;/script&gt;</pre>

然后，如果你玩得更高级点的话，你可以使用API在一个报告中显示所有搜索词和它们的搜索次数（使用ga:searchKeyword、ga:customVarValue1指标和ga:pageviews指标）。``

## 总结

这些方法中的某几种存在的唯一弊端是，在站内搜索词报告中仍然包括所有的搜索，其中包括无结果的并且你无法确切地区分它们。