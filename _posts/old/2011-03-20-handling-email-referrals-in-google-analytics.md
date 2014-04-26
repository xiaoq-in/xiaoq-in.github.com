---
title: 如何处理谷歌分析中来自邮件的引荐网址
author: 54jack
layout: post
permalink: /google-analytics/handling-email-referrals-in-google-analytics/
sina_t:
  - 'true'
views:
  - 1008
  - 1008
qq_t:
  - 'true'
duoshuo_thread_id:
  - 511756
yourls_shorturl:
  - http://t.xiaoq.in/4d
ta-thumbnail:
  - https://xiaoq.in/thumb/cache/2011/3/201-1.png;https://xiaoq.in/thumb/cache/2011/3/201-2.png;https://xiaoq.in/thumb/cache/2011/3/201-3.png;https://xiaoq.in/thumb/cache/2011/3/201-4.png;https://xiaoq.in/thumb/cache/2011/3/201-5.png;
categories:
  - Google Analytics
tags:
  - 媒介
  - 引荐网址
  - 流量来源
  - 谷歌分析
  - 邮件
---
If you&#8217;ve spent any time looking through your traffic sources in <span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>, particularly your referral sources, you may have noticed a lot of your traffic coming various mail sources:

如果你花些时间查看你的<span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="谷歌分析" target="_blank">谷歌分析</a></span>中的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e6%b5%81%e9%87%8f%e6%9d%a5%e6%ba%90/" title="查看流量来源中的全部文章" target="_blank">流量来源</a></span>，尤其是其中的网址来源，你可能会发现很多的流量来自于<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e9%82%ae%e4%bb%b6/" title="查看邮件中的全部文章" target="_blank">邮件</a></span>：

<img src="http://www.roirevolution.com/blog/2011/01/24/a/mail_sources_1.png" alt="mail_sources_1.png" width="398" height="343" />

Clearly it&#8217;s not terribly useful to see your traffic broken out this way. At the very least, you would want to consolidate all of those mail.yahoo.com sources.

很显然，查看像这样乱七八糟显示的流量并不太有用。至少来说，你会想合并所有的来自mail.yahoo.com的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e6%b5%81%e9%87%8f%e6%9d%a5%e6%ba%90/" title="查看流量来源中的全部文章" target="_blank">流量来源</a></span>。

But if you think about it, it probably doesn&#8217;t matter a whole lot which email service provider a visitor happened to be using when they clicked to your site. Perhaps it&#8217;d be better if we just consolidate all of those email sources into one entry. Not only would this significantly clean up reports, but it would also allow you to see the overall impact of traffic coming from email to your site.

但在如果你仔细思量，点击进入网站的用户使用哪个<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e9%82%ae%e4%bb%b6/" title="查看邮件中的全部文章" target="_blank">邮件</a></span>服务提供商其实并不太重要。或许，我们只需合并所有这些邮件来源到一个记录会更好些。这不仅会很明显地清理报告，还能够让你看到来自邮件的整体流量报告。

The easiest way to handle this is by using filters:

最简单的方法是使用过滤器：

The easiest way to handle this is by using filters:

<img src="http://www.roirevolution.com/blog/2011/01/24/b/mail_sources_2.png" alt="mail_sources_2.png" width="476" height="542" />

While this is called a custom advanced filter, it&#8217;s fairly straightforward. If you noticed in the first screenshot, all of traffic coming from email had &#8220;mail&#8221; somewhere in the source and &#8220;referral&#8221; as the medium. So this filter takes all of that traffic and changes the source of that traffic to webmail.

尽管这叫做高级自定义过滤器，其实很简单明了。如果你在第一个截图中注意了，会发现所有来自邮件的流量在<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e6%b5%81%e9%87%8f%e6%9d%a5%e6%ba%90/" title="查看流量来源中的全部文章" target="_blank">流量来源</a></span>中的某个位置有“mail”，<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%aa%92%e4%bb%8b/" title="查看媒介中的全部文章" target="_blank">媒介</a></span>是“referral”。因此，这个过滤器将采纳所有的那些流量并把它转化为webmail。

Also note that we set &#8220;Field B Required&#8221; to &#8220;Yes&#8221; and &#8220;Override Output Field&#8221; to &#8220;Yes&#8221;. Both of these settings are necessary in order for this filter to work. The first setting ensures that we only change data for visits that fit the requirement we set in Field B, while the second one ensures that all visits that meet the filter requirements will have their source overridden with &#8220;webmail&#8221;.

同时也请注意，我们设置”字段B为必填”为“是”，“覆盖输出字段”为“是”。这两个设置对于过滤器运行是必需的。第一个设置是确保我们仅仅改变满足“字段B”设置的条件的数据，而第二个是为了确保所有满足该过滤器条件的访问者其来源用“webmail”来替换。

Once you&#8217;ve applied this filter to your reports, your email visits going forward will be consolidated into a single entry:

webmail / referral

一旦你在报告中应用了该过滤器，来自邮件的访问将被合并成一个单一记录：

webmail / referral

Now if you tend to look at your traffic sources by medium, you&#8217;ll notice that even after this filter, webmail traffic is still included with the rest of your referral traffic:

现在，如果你打算通过<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%aa%92%e4%bb%8b/" title="查看媒介中的全部文章" target="_blank">媒介</a></span>查询流量来源，你将注意到即使在此过滤器正常运行之后，webmail的来源依然还包含在你其他的网址引荐流量中。

<img src="http://www.roirevolution.com/blog/2011/01/24/mail_sources_3.png" alt="mail_sources_3.png" width="342" height="253" />

If you&#8217;re OK with this, that&#8217;s fine, but it is possible to separate your email traffic out by adding a second filter in addition to the first filter:

如果你满足于此，没问题，但是还可能通过在第一个过滤器的基础上再增加第二个过滤器来分离你的邮件流量。

<img src="http://www.roirevolution.com/blog/2011/01/31/mail_sources_6.png" alt="mail_sources_6.png" width="483" height="556" />

This is similar to our previous filter, but here we specify that we want to filter on visits with a source of &#8220;webmail&#8221; and change the medium of those visits to &#8220;webmail&#8221;. Filters build on each other, so it&#8217;s important that this filter come after the previous filter, otherwise it won&#8217;t find any visits with &#8220;webmail&#8221; as the source.

这跟我们之前的过滤器类似，但是在此我们特定想通过“webmail”的流量来源过滤访问，并且把那些访问的媒介转换为“webmail”。过滤器建立在彼此之上，因此这个过滤器排在前一个之后是非常重要的，否则你不会看到任何来自“webmail”的流量来源。

After you make this change, your report on mediums should look more like the following:

在更改之后，你流量来源中的媒介报告将会如下面这样：

<img src="http://www.roirevolution.com/blog/2011/01/24/mail_sources_5.png" alt="mail_sources_5.png" width="351" height="284" />

This makes it much easier to differentiate between true site referrals and traffic that&#8217;s coming from email.

这使真实的网址引荐及来自邮件的流量区分开来，让事情简单多了。

Here are a couple final considerations:

这是一些最后要考虑的东西：

1. It&#8217;s possible to use advanced filters to break out webmail traffic by source. That is, you could have yahoo / webmail, aol / webmail, etc. The filters for this are much more complicated, however, and you may have trouble finding a good reason for knowing that an email visit came from aol instead of yahoo.

1.使用高级过滤器通过流量来源来区分各种邮件是可能的。也就是说你可以拥有yahoo/webmail,aol/webmail，等等。这些过滤器要复杂得多，而且，为什么需要知道邮件访问是来自aol还是yahoo，这也可能是一个问题。

2. Getting a lot of webmail traffic may also be a sign that you aren&#8217;t properly tagging your emails. If these are emails that you are sending out, especially from some type of autoresponder, then you should consider tagging these in some way.

 2.获得很多邮件来源也可能是你没有正确标注邮件的一个征兆。如果这些是你发出去的邮件，特别是来自某些自动发送器，那么你应该考虑用某种方法标注它们。

<span class='wp_keywordlink'><a href="http://www.yeezhe.com/" title="译者" target="_blank">译者</a></span>：<span class='wp_keywordlink'><a href="https://xiaoq.in/" title="肖庆" target="_blank">肖庆</a></span>。翻译自：<a title="Handling Email Referrals in Google Analytics" href="http://www.roirevolution.com/blog/2011/01/handling_email_referrals_in_google_analytics.php" target="_blank">http://www.roirevolution.com/blog/2011/01/handling_email_referrals_in_google_analytics.php</a>