---
title: GA跟踪代码应该放在哪个位置？
author: 肖庆
layout: post
permalink: /google-analytics/where-put-google-tracking-code/
sina_t:
  - 'true'
ratings_users:
  - 0
ratings_score:
  - 0
ratings_average:
  - 0
views:
  - 3258
duoshuo_thread_id:
  - 511978
yourls_shorturl:
  - http://t.xiaoq.in/3o
ta-thumbnail:
  - https://xiaoq.in/thumb/cache/2012/2/636-1.png;https://xiaoq.in/thumb/cache/2012/2/636-2.jpg;https://xiaoq.in/thumb/cache/2012/2/636-3.jpg;
categories:
  - Google Analytics
tags:
  - GA代码
  - 事件跟踪
  - 代码位置
  - 同步跟踪
  - 异步跟踪
  - 数据准确性
  - 自定义变量
  - 跟踪代码
  - 跳出率
  - 页面浏览
---
在我开始具体讲述之前，让我们去code.google.com看下官方推荐做法是把它们的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%b7%9f%e8%b8%aa%e4%bb%a3%e7%a0%81/" title="查看跟踪代码中的全部文章" target="_blank">跟踪代码</a></span>放在网页的哪个位置&#8230;.

> *分析代码片段是一小段的黏贴于你网页的javascript代码。它通过插入ga.js文件到页面中而激活GA跟踪。要在页面中使用它，复制如下代码，替换其中的UA-XXXX-1为你的配置文件ID。把它黏贴于你网站模板页面的</head>标签之前。*

<div id="attachment_8414">
  <a href="http://www.lunametrics.com/wp-content/uploads/2012/02/trackingcode.png"><img title="Google Analytics Asynchronous Tracking Code" src="http://www.lunametrics.com/wp-content/uploads/2012/02/trackingcode.png" alt="Google Analytics Asynchronous Tracking Code" width="661" height="199" /></a>
</div>

<div>
  GA<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%bc%82%e6%ad%a5%e8%b7%9f%e8%b8%aa/" title="查看异步跟踪中的全部文章" target="_blank">异步跟踪</a></span>代码
</div>

好！谢谢阅读，下次再见！

开个玩笑而已，当然没那么简单。

**那么，言归正传，我到底应该把我的GA<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%b7%9f%e8%b8%aa%e4%bb%a3%e7%a0%81/" title="查看跟踪代码中的全部文章" target="_blank">跟踪代码</a></span>放到哪个位置？**

事实上，我们经常被问到这个问题。这是我们评估时首要查看的元素之一。你使用哪种版本的跟踪代码，把它放在页面哪个位置。有很多不同版本，但是如果没有与时俱进的话，最常见的便是使用同步（或传统）跟踪代码，并且放置在页面底部。因此，当我们在评估时说：“我们建议你更新到<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%bc%82%e6%ad%a5%e8%b7%9f%e8%b8%aa/" title="查看异步跟踪中的全部文章" target="_blank">异步跟踪</a></span>代码，并且把它放到<head>区域，而不是页面的<body>区域”，人们有些疑虑。

**把GA跟踪代码放置在页面底部不好吗？我曾看到说你应该把代码放在网页底部，而不是放在head区域，因为这会使你的网站更快。**

<div id="attachment_8418">
  <img title="The Body" src="http://www.lunametrics.com/wp-content/uploads/2012/02/body.jpg" alt="Headless fish bodies" width="360" height="270" />
</div>

<div>
  你应该把跟踪代码放在<body>区域吗？
</div>

快速而“肮脏”的回答是把新代码放置到网页的任何位置都是可以的，并且对于99%的用户，你可能希望使用异步跟踪代码并把它放置于文件顶部。稍后我将讲述一些特例/修改。

不太快速的回答是，把传统跟踪代码放在网页顶部曾经是不好的，因此如果你阅读到一些书籍或博客声称为了加速你的网站，吹捧把<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ga%e4%bb%a3%e7%a0%81/" title="查看GA代码中的全部文章" target="_blank">GA代码</a></span>放到网页底部的有点，那么他们可能曾经是正确的，但是已经不再是正确的了。网速，已经今非昔比了。

Google在2009年12月1日发布异步跟踪代码。在此之前，我们有的只是传统代码，并且它同其他基本的javascript代码一样运行。也就是说它将会一次运行一行代码。因此，如果你的浏览器加载一行代码，它将只加载那行，然后等到该行被完全加载。然后，仅仅是然后，它才会移动到下一行，再加载下一行，依次加载。就像一条传送带。那种设计的问题是，如果你遇到一个小问题，整个网页将被挂起。因此，如果Google的跟踪代码当时被放在网页顶部，那么你网页的加载速度部分取决于Google发送该段代码的速度。如果花费Google10秒钟来发送那段代码，那么你的访客将不得不多等待10秒钟以浏览网页。这就是为什么把跟踪代码放在网页底部这种做法被推荐使用。那样的话，如果在加载来自Google的文件时失速的话，至少你的网页先被加载。

然而，异步跟踪代码的运行方法截然不同。这不是类似一条传送带，现在是类似于多条，并且不管获取来自Google的数据需要多久，页面的其它部分还是可以加载。新的跟踪代码在自己的传送带上加载，而网页的其它部分仍然同时在加载。

并且很重要的是异步跟踪代码被设计为只需从Google下载一次即可，然后它从缓存中读取文件（即它保存在你的电脑并且你不必再次下载它），这使得它更快。

**你把我弄糊涂了，那对我到底意味着什么？**

它意味着，异步跟踪代码平均而言在跟踪数据方面有5%的提升，某些网站在数据方面有10%到20%的提升。如果你使用AdWords，那么使用异步跟踪代码的准确性接近100%。[<span class='wp_keywordlink'><a href="http://www.yeezhe.com/" title="译者" target="_blank">译者</a></span>注：adwords也在使用GA，因此cookie预先已被下载到了缓存并且说明你的浏览器支持javascript代码]

异步跟踪代码更快，因为你获得关于有多少人确实访问了你网站的更准确数据。

**如果我有<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>或者发生在页面上的东西呢，我应该在哪里记录用户行为，跟踪代码还未被加载吗？**

好吧，如果你的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%90%8c%e6%ad%a5%e8%b7%9f%e8%b8%aa/" title="查看同步跟踪中的全部文章" target="_blank">同步跟踪</a></span>代码在网页底部运行，那个问题也将会产生，但是使用异步跟踪代码会好很多。尽管从Google加载ga.js需要时间，但是它已经在网页中设置好了跟踪变量，并且它会在实际的文件被加载之前存储你运行的事件。一旦文件加载，那么所有后台记录的事件将会发送给Google。这并不完美，但是大多数情况下，它将捕捉发生在<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ga%e4%bb%a3%e7%a0%81/" title="查看GA代码中的全部文章" target="_blank">GA代码</a></span>完成加载之前的事件，然后待代码加载完成之后把这些事件发送出去。

**那么，我需要把它移到我所有页面的head区域吗？我有很多页面，那得花很多时间。**

<div id="attachment_8419">
  <img title="Fish Heads" src="http://www.lunametrics.com/wp-content/uploads/2012/02/head.jpg" alt="Fish heads" width="360" height="270" />
</div>

<div>
  你可以把代码放到任意位置，但是放到<head>区域会好些
</div>

不。你事实上可以把代码放到任意位置，而且无论它位于head区域还是body区域等任何位置，它都将运行。然而还是推荐你把它放到head区域，因为这将使数据尽量准确。

你看，<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e9%a1%b5%e9%9d%a2%e6%b5%8f%e8%a7%88/" title="查看页面浏览中的全部文章" target="_blank">页面浏览</a></span>尽在每次代码加载之后才被记录。因此代码越早加载，<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e9%a1%b5%e9%9d%a2%e6%b5%8f%e8%a7%88/" title="查看页面浏览中的全部文章" target="_blank">页面浏览</a></span>也越早被记录。比如你有一个巨大的博客页面，并且加载比较慢，甚至花费10到20秒才能加载完所有数据。如果你的Google代码直到最后才加载，它将会被挂起，就如同旧的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%90%8c%e6%ad%a5%e8%b7%9f%e8%b8%aa/" title="查看同步跟踪中的全部文章" target="_blank">同步跟踪</a></span>代码挂起其他代码行一样。只是现在它挂起了跟踪代码。如果你网站的一个访客进入了一个页面，然后在跟踪代码释放Pageview之前就离开，那么该访客不会被记录。无论这些访客进入你网站的哪个页面，他们现在都成为一个新的直接访客。这将使你网站的所有数据不准确。

因此，最佳实践是使用异步跟踪代码并将其放置到页面head球。它不会减慢你网页其他部分的加载速度，并且把代码放在那里，它也不会因为网页的其他部分而变得更慢，因此它将更快释放，而且你将获得关于你的访客访问了哪些页面的更准确数据。

**那么例外是什么？何时在head区域运行跟踪代码是不好的？**

我上面提到过确实有一些例外。其中之一便是如果你在页面中设置了<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>。

如果你在网页中使用<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>，那么它将会保留在你的页面中，等待pageview的跟踪或者event的调用。如果你在某个页面设置了一个<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>，并且没有在它之后跟踪一个页面或者事件，那么该自定义变量将不会被传递给Google。有时你可能不会在某个页面中跟踪任何事件，但是你会想设置一个自定义变量。由于代码发送的方式不同，很可能该自定义变量仅会在head文档之后才会生成。通常一个页面可以被编码，以使让这些自定义变量可以在HTML代码被发送之前决定，然后你也可以让自定义变量在文档的顶部创建。或许理论上它可以被放到head区域，但是开发人员不会那样创建页面，并且你不想或者无法让他们重做所有事情。在这些情况下，你可以在页面的任意位置设置一个自定义变量，然后你不用在head区域中跟踪<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e9%a1%b5%e9%9d%a2%e6%b5%8f%e8%a7%88/" title="查看页面浏览中的全部文章" target="_blank">页面浏览</a></span>，而是把该行：

> \_gaq.push(['\_trackPageview']);

from the Asynchronous code, and then insert it later in the page wherever you like, after the custom variables are set. That way the code loads up, it doesn’t interrupt the page load, and you can then track custom variables on the page itself anywhere they appear, as well as retaining the benefit of loading the tracking code early.从异步跟踪代码中移除，然后把它插入页面中自定义变量设置代码下面的任意位置。代码那样加载的话，它不会感染页面加载，而且你可以在页面本身中它们出现的任意位置中跟踪自定义变量，同时还能保留预先加载跟踪代码的好处。

**然而，**这样会降低准确度，因为如果一个用户在trackPageview被调用之前离开页面，那么你面临着传统跟踪代码放置在顶部而产生的同样问。<a title="Using Events to help track your Custom Variables" href="http://www.lunametrics.com/blog/2011/12/30/google-analytics-custom-variables-working/" target="_blank">另一种方式是使用事件跟踪</a>。一个释放的事件将会提交那个等待中的自定义变量，因此你可以针对该自定义变量释放一个事件。根本来说，这是一个丢弃的事件。

> \_gaq.push(['\_setCustomVar',1, 'Status', 'Logged In']);  
> \_gaq.push(['\_trackEvent', 'Custom', 'PageLoad', 'Setting Logged In State',0,true]);

对此的一些说明：

首先，我们设置自定义变量，我们把它安排到键1的位置（共5个键值），然后我们对该自定义变量命名为Status，设置自定义变量值为Logged In.它将保留在那里，知道一个事件或页面浏览被跟踪到。

因此，我们使用事件。我们把它设置为名为Custom的分类组，定义其操作为PageLoad，因为一个用户并不会特地与该事件交互，因此事件不交互性的值设置为true。然后 我们设置事件标签为该事件在做师门。我们增加了0的事件价值（如果不使用它的话，你不必在此添加一个真实的价值，但是我个人对于不传递任何值感到不适）。我们还在此添加了非交互值为true，如果你不设置为true，那么这个事件将被当做一个页面交互，从而影响着陆页面的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%b7%b3%e5%87%ba%e7%8e%87/" title="查看跳出率中的全部文章" target="_blank">跳出率</a></span>。那么当某个个进入你的页面并流量，然后点击返回按钮，它本来会当做是“跳出”，但是由于用户与网站进行了“交互”，它不会被当做跳出。因此把这个值设置为true，以便于它这样被对待。

**但是等等，我在Google自身的支持页面中看到它说我不应该这样做？**

<a title="Outdated Google Support Page" href="http://support.google.com/googleanalytics/bin/answer.py?hl=en&answer=55574" target="_blank">你是说这个吗</a>?

是的，不过尽信书不如无书，是吧？那是已经过时的支持信息。

**那么，如果我更新，它将会改变我的数据吗？比如我突然看到更多的页面浏览或者其他什么的？**

有可能。这取决于你的网站，代码的位置，速度和页面加载时间。通过更新，你应该会看到数据发生变化和，可能是一点小变化，也可能是很大的变化。但是它将会是更准确的数据。在此，我们更赞成使数据尽量准确，即使这将会在报告层次产生一小段时间的波动。

**如果我不更新，我的网站还将继续跟踪数据吗？**

当然。它可能不会那么准确，但是取决于你的网站，这很可能并不会存在巨大的数据差异。主要功能都从同一位置&#8212;ga.js文件主要区别是它如何加载，加载的速度，以及它是否被缓存在你的浏览器，最终区别是你数据的准确性。

**那么，我该怎么做？**

如果你没有使用最新的异步跟踪代码，那么你应该更新使用它。如果不更新，你肯定会遇到一些严重的问题。它需要被放置在文档的head区域码？不，把它放到底部并不会怎么样，但是如果你可以把它移到顶部，那么你应该这样做，因为这将更快并更准确。如果你无理由继续使用旧的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%90%8c%e6%ad%a5%e8%b7%9f%e8%b8%aa/" title="查看同步跟踪中的全部文章" target="_blank">同步跟踪</a></span>代码并将其放在页面底部，并且你没有使用自定义变量&#8230;那么不更新代码并将其移到页面顶部实在是没有任何理由。你将获得更准确的数据，并且你将获得更新和更好的跟踪功能。来吧，大家都在这样做。

译者<span class='wp_keywordlink'><a href="https://xiaoq.in/" title="肖庆" target="_blank">肖庆</a></span>原创翻译自：<a title="Where Should The Google Analytics Tracking Code Be Placed?" href="http://www.lunametrics.com/blog/2012/02/09/where-put-google-tracking-code/" target="_blank">http://www.lunametrics.com/blog/2012/02/09/where-put-google-tracking-code/</a>