---
title: Google Analytics如何进行子域名跟踪
author: 肖庆
layout: post
permalink: /google-analytics/google_analytics_subdomain_tracking/
sina_t:
  - 'true'
ratings_users:
  - 0
ratings_score:
  - 0
ratings_average:
  - 0
views:
  - 3546
duoshuo_thread_id:
  - 511983
yourls_shorturl:
  - http://t.xiaoq.in/4l
ta-thumbnail:
  - NoMediaFound
categories:
  - Google Analytics
tags:
  - GA子域名跟踪
  - 哈希值
  - 子域名跟踪
  - 子域跟踪
  - 自身引荐
  - 跨域跟踪
---
快速搜索“<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span> Subdomain Tracking（<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ga%e5%ad%90%e5%9f%9f%e5%90%8d%e8%b7%9f%e8%b8%aa/" title="查看GA子域名跟踪中的全部文章" target="_blank">GA子域名跟踪</a></span>）”的话，你可能已经注意到很多排名靠前的结果要么是可悲地过期了，要么是让人疑惑不解。本文的目的就是针对当前版本的异步跟踪代码提供进行GA<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%ad%90%e5%9f%9f%e8%b7%9f%e8%b8%aa/" title="查看子域跟踪中的全部文章" target="_blank">子域跟踪</a></span>的个人推荐做法。

<img class="alignnone size-full wp-image-668" title="ga subdomain tracking" src="http://xiaoq.in/g/pics/2012/02/ga-subdomain-tracking.gif" alt="" width="350" height="95" />

当前在Google Code中并没有特定文章专门描述如何进行<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ga%e5%ad%90%e5%9f%9f%e5%90%8d%e8%b7%9f%e8%b8%aa/" title="查看GA子域名跟踪中的全部文章" target="_blank">GA子域名跟踪</a></span>。最接近的是[这个][1]，它推荐这样：

//Tracking code customizations only  
var \_gaq = \_gaq || [];  
\_gaq.push(['\_setAccount', 'UA-12345-1']);  
\_gaq.push(['\_setDomainName', '.example-petstore.com']);  
\_gaq.push(['\_setAllowHash', false]);  
\_gaq.push(['\_trackPageview']);

而我觉得对于大多数含子域名的网站你应该使用下面的跟踪代码：

**//Tracking code customizations only**  
var \_gaq = \_gaq || [];  
\_gaq.push(['\_setAccount', 'UA-12345-1']);  
\_gaq.push(['\_setDomainName', 'example-petstore.com']);  
\_gaq.push(['\_addIgnoredRef', 'example-petstore.com']);  
\_gaq.push(['\_trackPageview']);

那么，Google Code中推荐的代码有什么错误呢？最终证明它提供的代码存在3个问题，这可能带来不必要的问题：

<big><strong>1. 关闭<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%93%88%e5%b8%8c%e5%80%bc/" title="查看哈希值中的全部文章" target="_blank">哈希值</a></span>并不好</strong></big>

关闭<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%93%88%e5%b8%8c%e5%80%bc/" title="查看哈希值中的全部文章" target="_blank">哈希值</a></span>对于<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%b7%a8%e5%9f%9f%e8%b7%9f%e8%b8%aa/" title="查看跨域跟踪中的全部文章" target="_blank">跨域跟踪</a></span>正确运作是非常必要的，你可以通过设置 ['\_setAllowHash', false] 或 ['\_setDomainName', 'none']来实现。然而， 由于域哈希事实上非常有用，因此开启<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%93%88%e5%b8%8c%e5%80%bc/" title="查看哈希值中的全部文章" target="_blank">哈希值</a></span>是一个不幸的必要条件。

默认情况下，代码无法识别cookie的域名；该信息无法获得，除非它是cookie名称或者cookie值本身。包含哈希值会提供上述域名信息以便GA代码能够在可能存在多组哈希值时读取正确的cookie值。

关闭哈希值意味着GA跟踪代码无法获得哪组cookie是正确的那个。大多数时候只存在一组cookie值，因此这并没设么大不了的。

但是，如果你之前使用了无<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%ad%90%e5%9f%9f%e5%90%8d%e8%b7%9f%e8%b8%aa/" title="查看子域名跟踪中的全部文章" target="_blank">子域名跟踪</a></span>的GA代码，那么你可能会最终对会访客产生两组cookie值：一组由旧代码产生，一组由新代码产生。这经常发生在子域名上，但是，如果你使用 ['\_setDomainName', 'none'] 而不是 ['\_setAllowHash', false]的话，也可能发生在你的主域名上。

同时还要可能你的心GA跟踪代码将会毁掉来自你的旧GA跟踪代码的cookie值，而非创建两组cookie值，因为这两组哈希值并不匹配。这通常会发生在主域名上而非子域名上。

Eduardo Cereto发表过一篇[文章][2]更详细地探讨这个问题并且提供了\_setAllowHash会带来问题的另一种情况。这里的底线是你需要\_setAllowHash来进行<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%b7%a8%e5%9f%9f%e8%b7%9f%e8%b8%aa/" title="查看跨域跟踪中的全部文章" target="_blank">跨域跟踪</a></span>，但是如果你仅仅进行<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%ad%90%e5%9f%9f%e8%b7%9f%e8%b8%aa/" title="查看子域跟踪中的全部文章" target="_blank">子域跟踪</a></span>，这并不必要，并且还可能产生问题。

<big><strong>2. 前置点号带来cookie重置</strong></big>

Google Code提供了在使用_setDomainName时使用使用前置点号的[解释][3]，如下：

”..如果你想跟踪次级二级域名：

* dogs.petstore.example.com  
* cats.petstore.example.com,

前置点号是必要的。“

如果你的网站确实使用次级二级域名，那么你确实需要使用前置点号以让<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%ad%90%e5%9f%9f%e5%90%8d%e8%b7%9f%e8%b8%aa/" title="查看子域名跟踪中的全部文章" target="_blank">子域名跟踪</a></span>运行。然而，如果你的网站不适用次级二级域名，那么不适用前置点号会更好些。

原因又回到了哈希值。在使用前置点号时GA跟踪代码产生的哈希值与你不使用前置点时产生的哈希值并不相同。但是如果你在主站上不进行任何子域名跟踪的话，其产生的哈希值与你使用子域名跟踪但不使用前置点时是一样的。

也就是说，如果你之前并未运行任何子域名跟踪，使用前置点号将会造成你的新GA跟踪代码毁掉旧的cookie值，因为哈希值并不匹配。

如果不是必要的话，那就别包含前置点号，这意味着你将让更少的cookie重置，而这将让子域名跟踪转换更容易些。

<big><strong>3. 无<strong>_addIgnoredRef进行子域名跟踪会造成<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e8%ba%ab%e5%bc%95%e8%8d%90/" title="查看自身引荐中的全部文章" target="_blank">自身引荐</a></span></strong></strong></big>

如果你的网站没有任何子域名，GA跟踪代码可以识别访客在页面浏览时会话过期，并且避免使用<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e8%ba%ab%e5%bc%95%e8%8d%90/" title="查看自身引荐中的全部文章" target="_blank">自身引荐</a></span>或者来自自己网站的内部引荐覆盖他们之前的引荐信息。

然而，当你有子域名时，即使你的代码是标准的子域名跟踪代码，安全卫士被移除了（即会污染引荐流量）。这会造成特别高比例的自身引荐，尽管看起来你已经把所有事情都做好了。

解决方案是使用 _addIgnoredRef，但是如何使用它却被经常误解。Google代码中心的[推荐][4]是使用类似下面的东西：

\_gaq.push(['\_addIgnoredRef', 'www.sister-site.com']);

我仔细看了下ga.js代码基础，并且观察到上述代码并不会运行。因为GA跟踪代码把www.sister-site.com和sisiter-site.com视作等同，因此添加www.sister-site.com作为忽视的引荐网址并不会解决什么问题。在此使用前置点号也不奏效。但是这个代码相当不错：

\_gaq.push(['\_addIgnoredRef', 'sister-site.com']);

并且事实上，这也行：

\_gaq.push(['\_addIgnoredRef', 'sister-site']);

GA跟踪代码检查你添加的每个忽视的引荐字符并且使用indexOf方式决定该字符串是否包含在引荐域名中。如果其中的任何一个检查返回值为true，那么引荐被忽略。由于不包含前置点号的根层次域名将会包含在任何子域名中，那么把该值传递到\_addIgnoredRef刚好有效。这也减少了针对每个子域名添加单独\_addIgnoredRef 声明的需求。

然而，尽管使用\_addIgnoredRef，你还是有可能会看到自身引荐，虽然这个量并没有不使用子域名跟踪产生的那么多。因为，只有当cookie值包含了一个存在的引荐信息时，\_addIgnoredRef才会运行。如果一个新访客通过一个没有安装GA跟踪代码的页面进入你的网站，然后进入一个安装了GA跟踪代码的页面，那么这应该会造成一个自身引荐，无论是否是跨域子域名。

然而，这些类型的自身引荐可以通过确保每个页面均安装GA代码来实现。那么，如果有任何的页面存在这个问题，你可以查看GA报告数据并且确切地决定哪些页面对这个问题负责。由于你在使用_addIgnoredRef，找到这些页面会更简单些，因为你不用出来那些无理由存在的自身引擎干扰数据。

这里的关键点是_addIgnoredRef应该是子域名跟踪的标配，而不管你是否注意到自身引荐。这将在第一步就帮助你避免不需要的自身引荐。

希望这篇文章解答了你关于GA子域名跟踪的相关疑惑。欢迎评论或提问。

<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/" title="肖庆" target="_blank">肖庆</a></span>原创翻译自：<a title="Google Analytics Subdomain Tracking" href="www.roirevolution.com/blog/2011/01/google_analytics_subdomain_tracking.php" target="_blank">www.roirevolution.com/blog/2011/01/google_analytics_subdomain_tracking.php</a>

 [1]: http://code.google.com/apis/analytics/docs/tracking/gaTrackingSite.html#domainSubDomains
 [2]: http://eduardo.cereto.net/google-analytics-_setallowhash-bug
 [3]: http://code.google.com/apis/analytics/docs/gaJS/gaJSApiDomainDirectory.html#_gat.GA_Tracker_._setDomainName
 [4]: http://code.google.com/apis/analytics/docs/gaJS/gaJSApiSearchEngines.html#_gat.GA_Tracker_._addIgnoredRef