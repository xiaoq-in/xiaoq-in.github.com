---
title: 通过GA对内容进行高级跟踪：第二部分
author: 肖庆
layout: post
permalink: /google-analytics/advanced-content-tracking-with-google-analytics-part-2/
sina_t:
  - 'true'
ratings_users:
  - 0
ratings_score:
  - 0
ratings_average:
  - 0
views:
  - 2402
duoshuo_thread_id:
  - 511984
yourls_shorturl:
  - http://t.xiaoq.in/67
ta-thumbnail:
  - http://blog.xiaoq.in/thumb/cache/2012/2/669-1.png;http://blog.xiaoq.in/thumb/cache/2012/2/669-2.png;http://blog.xiaoq.in/thumb/cache/2012/2/669-3.jpg;http://blog.xiaoq.in/thumb/cache/2012/2/669-4.jpg;http://blog.xiaoq.in/thumb/cache/2012/2/669-5.png;http://blog.xiaoq.in/thumb/cache/2012/2/669-6.png;http://blog.xiaoq.in/thumb/cache/2012/2/669-7.png;http://blog.xiaoq.in/thumb/cache/2012/2/669-8.jpg;
categories:
  - Google Analytics
tags:
  - 事件跟踪
  - 停留时间
  - 内容跟踪
  - 自定义变量
  - 跳出率
  - 高级细分
---
*这是高级<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%86%85%e5%ae%b9%e8%b7%9f%e8%b8%aa/" title="查看内容跟踪中的全部文章" target="_blank">内容跟踪</a></span>系列的第二部分。本文讲述*如何*报告和分析人们与内容进行交互的方式。*

正如我在第一部分提及的，该技巧和概念源于协作。在此感谢这些贡献者：

**Nick Mihailovski** – Developer advocate at Google (and the guys that sits across from me)  
**Thomas Baekdal** – Smart guy and publisher of <a href="http://www.baekal.com/" target="_blank">www.baekal.com</a> (you should subscribe)  
**Avinash Kaushik** – If you don’t know Avinash…  
**Joost de Valk** – Creator of the <a href="http://yoast.com/wordpress/google-analytics/" target="_blank">Google Analytics for WordPress</a> plugin (you should use it)  
**Eivind Savio** – <a href="http://www.savio.no/" target="_blank">Blogger</a> and GA consultant (read his stuff)

现在，让我们看数据：

**报告**

这个跟踪技巧使用<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>来跟踪人们在网站上滚动滚动条的行为。那么，让我们先看<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>报告。

报告位置：内容>事件>热点事件

<div id="attachment_2192">
  <img title="Reading actions in Google Analytics" src="http://cutroni.com/blog/wp-content/uploads/Top-Events-Google-Analytics.png" alt="Reading actions in Google Analytics" width="628" height="93" />
</div>

<div>
  GA中的阅读操作
</div>

所有这些事件都被打包到Reading分类中。你可能在想为什么价值如此之高。记住这些值是特定行为之间的数值，以秒为单位。这就是原因所在。稍后再多谈下这点。

点击Reading，你会在该分类中看到我们创建的所有操作（ArticleLoaded, StartReading, ContentBottom or PageBottom）。

<div id="attachment_2193">
  <a href="http://cutroni.com/blog/wp-content/uploads/Top-Events-Google-Analytics1.png"><img title="Reading actions in Google Analytics" src="http://cutroni.com/blog/wp-content/uploads/Top-Events-Google-Analytics1-e1329940131229.png" alt="Reading actions in Google Analytics" width="640" height="112" /></a>
</div>

<div>
  下钻Reading事件以查看特定的阅读操作。
</div>

让我们看下这个数据并对其进行解译。*所有加载文章中，82%的人开始阅读文章。*我认为这非常不错。其实，我认为这18%的没有开始阅读文章的访问确切是在新标签或窗口中打开文章然后超时造成的。他们离开30分钟，从而丢失了跟踪。

*所有这些开始阅读文章的访问，63%的到达内容底部。*看起来非常不错。我没有任何的阅读基准报告，因此我对于超过一半的访问到达文章底部这种情况非常满意。但是，这是我希望长期跟踪的一个趋势。稍后我也将对这个进行一些细分。

*开始阅读文章的访问中，有18%的到达了页面底部。*

信不信由你，18%是一个很高的数字。平均而言，到达文章底部的比例是在3%到5%之间，这是我通过对几个网站5天的数据进行观察得出来的。

啊！对我而言，那太糟糕了！我本以为更多人阅读评论。我想我错了。评论似乎并不能吸引太多人。

但是记住，这是总数据。我们需要进行一些西方以了解哪些内容驱动这些指标。

**页面级阅读指标**

还是看热点事件曝光，我们添加一个“网页”的次级维度，从而查看开始加载、开始阅读和完成阅读频率最高的文章分别有哪些。

注：我将对结果进行过滤以只包含一篇文章，这将会使查看报告更简单。你可以使用高级过滤器来仅仅聚焦你感兴趣的数据。

<div id="attachment_2195">
  <a href="http://cutroni.com/blog/wp-content/uploads/Screen-Shot-2012-02-22-at-2.42.12-PM.png"><img title="Page level interaction metrics in Google Analytics." src="http://cutroni.com/blog/wp-content/uploads/Screen-Shot-2012-02-22-at-2.42.12-PM-e1329939904247.png" alt="Page level interaction metrics in Google Analytics." width="640" height="134" /></a>
</div>

<div>
  查看GA中单一内容的交互操作
</div>

在此你可以看到一篇文章的加载次数，开始阅读词，到达内容底部的次数，到达页面底部的次数。

<div id="attachment_2199">
  <a href="http://cutroni.com/blog/wp-content/uploads/TimeMeasurements.jpg"><img title="Time to action measurements in Google Analytics" src="http://cutroni.com/blog/wp-content/uploads/TimeMeasurements.jpg" alt="Time to action measurements in Google Analytics" width="642" height="195" /></a>
</div>

<div>
  与内容进行交互的平均时间
</div>

非常酷。

把这个数据与平均数据进行比较，我可以看到这两者的基本趋势是一致的。

*   加载过文章的访问大约82%开始阅读（日平均值是82%）
*   大约55%访问到达内容底部（日平均值是63%）
*   大约14%访问到达页面底部（日平均值是18%）

我建议查看文章并检查比如评论数量等东西以更好地理解数据。

在此让我们花点时间看看事件价值。事件价值单位为秒。这些时间测量值带班以下时间间隔：

*   页面加载到开始阅读（即滚动页面）的时间
*   开始阅读到到达文章底部的时间
*   开始阅读到到达页面底部的时间

蹦出来的第一个事情是滚动前的时间。大约5分钟！（时间单位是秒，因为要除以60）。通过和一些人聊过之后，我们相信这个时间差是因为人们在标签中打开文章页面并稍后阅读而造成的。

一旦访客开始阅读，大概花费6.5秒钟到达文章底部，9.5秒钟到达页面底部。再次，这取决于很多东西，比如评论，文章的复杂性，等等。但是你可以将这些数据与网站平均值进行比较。

或者更好的话，创建一个针对内容分类的平均值，从而比较阅读某篇技术文章的时间和阅读技术类文章的时间平均值。

*注意：极端者很容易使这些指标数据不准。*

如果一些人打开标签然后离开，这将会真正甩掉这些指标。

好，更多报告。

让我们查看流量来源报告。记住，我创建了一个基于这些事件的目标。现在你可以查看目标标签并且马上看到有多少流量到达文章或页面底部：

<div id="attachment_2202">
  <a href="http://cutroni.com/blog/wp-content/uploads/MeasureSourcesBasedOnReading.jpg"><img title="Google Analytics Traffic Sources Report" src="http://cutroni.com/blog/wp-content/uploads/MeasureSourcesBasedOnReading.jpg" alt="Google Analytics Traffic Sources Report" width="615" height="272" /></a>
</div>

<div>
  基于实际阅读指标测量流量来源
</div>

现在，基于多少人实际看了你的内容而不是网站<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%81%9c%e7%95%99%e6%97%b6%e9%97%b4/" title="查看停留时间中的全部文章" target="_blank">停留时间</a></span>、网页<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%81%9c%e7%95%99%e6%97%b6%e9%97%b4/" title="查看停留时间中的全部文章" target="_blank">停留时间</a></span>或者访问次数，你可以真正测量某个流量来源的价值。

注意：GA对于每次访问仅仅计算一个转化。因此一旦访客到达某个文章或页面的地步，目标将会被计算。总时间是原始的数值，并且比总目标数更大。独立事件是被包含在某特定事件中的访问数量，并且应该与目标数相同。

**不要忘记<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e9%ab%98%e7%ba%a7%e7%bb%86%e5%88%86/" title="查看高级细分中的全部文章" target="_blank">高级细分</a></span>**

这只是开头。你可以做些数据的仔细分析。如果你是一个出版商，尝试类似的细分：

*   作者
*   出版日期
*   内容分类

当然，你需要这些数据点以创建这些细分。我再<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>中有这些数据（因为有[Google Analytics plugin for WordPress][1]），因此我可以做类似下面的事情：

<div id="attachment_2214">
  <a href="http://cutroni.com/blog/wp-content/uploads/Screen-Shot-2012-02-23-at-5.16.43-PM.png"><img title="Creating a Custom Advanced Segment in Google Analytics." src="http://cutroni.com/blog/wp-content/uploads/Screen-Shot-2012-02-23-at-5.16.43-PM.png" alt="Creating a Custom Advanced Segment in Google Analytics." width="644" height="284" /></a>
</div>

<div>
  你可以使用自定义<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e9%ab%98%e7%ba%a7%e7%bb%86%e5%88%86/" title="查看高级细分中的全部文章" target="_blank">高级细分</a></span>来细分你的阅读指标。
</div>

细分得出的数据非常有用，但是在界面中处理它们有些挑战。如下图：

<div id="attachment_2215">
  <a href="http://cutroni.com/blog/wp-content/uploads/Screen-Shot-2012-02-23-at-5.19.42-PM.png"><img title="Segmented data in Google Analytics." src="http://cutroni.com/blog/wp-content/uploads/Screen-Shot-2012-02-23-at-5.19.42-PM.png" alt="Segmented data in Google Analytics." width="586" height="228" /></a>
</div>

<div>
  基于分类细分阅读数据，从而获得更深入透视。
</div>

这在Excel中稍微简单些。

**高级数据分析**

.尽管你可以从这些报告中获得很多透视，这些数据渴望Excel。导出这些数据并且在Excel中国龙其实更简单，特别是如果你查看一个带有“网页”次级维度的操作。

在电子表格中，我想看到时间操作和网页URL的维度。我想查看热点事件的指标，独立事件，总事件价值（所有时间测量结果），以及平均事件价值（这也是平均时间测量结果）。

记住，事件操作是：

*   页面加载次数
*   人们开始滚动页面的次数
*   到达内容底部的次数
*   到达页面底部的次数

你首先想做的事情将会是将时间测量结果从秒为单位转换为分钟。然后开始对你的网站建立一些平均值。基于分类、作者、出版时间创建基准数。

你可能想报考更多的维度，比如分类、作者，等等。我们将从中获得一些十分有意义的数据。

你可以使用任何GA的Excel插件，比如<a href="http://www.google.com/analytics/apps/about?app_id=93002" target="_blank">NextAnalytics</a> 或者 <a href="http://www.google.com/analytics/apps/about?app_id=83001" target="_blank">GA Data Grabber</a>（其实还有<a href="http://excellentanalytics.com/" target="_blank">Excellent Analytics</a>）

<div id="attachment_2191">
  <a href="http://cutroni.com/blog/wp-content/uploads/Screen-Shot-2012-02-22-at-2.12.37-PM.png"><img title="Google Analytics Tracking of Content in Excel" src="http://cutroni.com/blog/wp-content/uploads/Screen-Shot-2012-02-22-at-2.12.37-PM-e1329946885106.png" alt="Google Analytics Tracking of Content in Excel" width="639" height="230" /></a>
</div>

<div>
  在Excel中处理内容交互数据非常强大
</div>

如果你是菜鸟，并且想通过使用一些代码来获得这些数据，这是我使用的API查询。你将需要改变时间范围。

> http://code.google.com/apis/analytics/docs/gdata/gdataExplorer.html?dimensions=ga%253ApagePath%252Cga%253AeventAction&metrics=ga%253AtotalEvents%252Cga%253AuniqueEvents%252Cga%253AeventValue&filters=ga%253AeventCategory%253D%253DReading&start-date=2012-02-20&end-date=2012-02-20&max-results=10000

**其他需要注意的事情**

除了上述数据，还有更多需要注意的。首先，你的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%b7%b3%e5%87%ba%e7%8e%87/" title="查看跳出率中的全部文章" target="_blank">跳出率</a></span>将会变低。变得很低。跟踪滚动的事件被记为一个交互。因此，如果放开没有看任何其他页面，他们还是**不会**被记为跳出。

其次，你的网站停留时间和网页停留时间将增加。我不会在此深入所有细节，但是对于仅仅包括一个页面浏览的访问，Google将使用当前会话中最后交互的**GIF请求**来计算时间。因此，这将会是访客到达内容或者页面底部的时间。

<div id="attachment_2204">
  <img title="Google Analytics Bounce Rate and TIme on Site" src="http://cutroni.com/blog/wp-content/uploads/Screen-Shot-2012-02-22-at-4.26.57-PM-e1329946066625.png" alt="" width="400" height="95" />
</div>

<div>
  如果你使用这个技术，你的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%b7%b3%e5%87%ba%e7%8e%87/" title="查看跳出率中的全部文章" target="_blank">跳出率</a></span>将会降低并且网站停留时间会增加。
</div>

你的时间测量结果将会**更加地**准确。

**前后对比**

为了将注意力集中于一些分析，我认为查看一些内容页面和实施该跟踪技术之前它们被察觉到的表现是十分有趣的。

以下是以一周为时间范围针对一篇文章进行比较的数据。本周是新的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%86%85%e5%ae%b9%e8%b7%9f%e8%b8%aa/" title="查看内容跟踪中的全部文章" target="_blank">内容跟踪</a></span>代码。看看这些在网页停留时间和<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%b7%b3%e5%87%ba%e7%8e%87/" title="查看跳出率中的全部文章" target="_blank">跳出率</a></span>方面的**巨大**差异。

<div id="attachment_2207">
  <a href="http://cutroni.com/blog/wp-content/uploads/ContentComparison.jpg"><img title="Comparing content before and after the code change." src="http://cutroni.com/blog/wp-content/uploads/ContentComparison-e1329962020656.jpg" alt="Comparing content before and after the code change." width="640" height="172" /></a>
</div>

<div>
  在采用这个技术之后，你的维度将会发生巨大变化。
</div>

很明显的改进，不是吗？代码改变之后，我获得更好的数据。

**<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>呢？**

如果你阅读了本系列的第一部分，那么你可能在想<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>。当用户在一分钟之后到达了页面底部，这个代码确实设定了一个自定义变量。如果他们在一分钟内到达页面底部，那么他们是快速浏览者。

在看到有那么少人确实到达页面底部之后，我想这段代码应该移到内容部分的底部。因此，我移动了代码。我还改变了代码，使其成为页面级自定义变量。

自定义变量会提供类似事件跟踪的数据。自定义变量分析需要耐心等待。

完了&#8230;.目前就这样了。

我希望你认为这很有趣。我当然是这么想的。我认为它开启了另一扇门&#8212;更准确跟踪内容的方法之门。

再次感谢所有协作贡献者。

<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/" title="肖庆" target="_blank">肖庆</a></span>原创翻译自：<a title="Advanced Content Tracking with Google Analytics: Part 2" href="http://cutroni.com/blog/2012/02/23/advanced-content-tracking-with-google-analytics-part-2/" target="_blank">http://cutroni.com/blog/2012/02/23/advanced-content-tracking-with-google-analytics-part-2/</a>

 [1]: http://yoast.com/wordpress/google-analytics/