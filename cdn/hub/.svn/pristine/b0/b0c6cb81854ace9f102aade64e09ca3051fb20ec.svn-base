---
title: 在谷歌分析中跟踪谷歌位置搜索的流量来源
author: 54jack
layout: post
permalink: /google-analytics/tracking-traffic-from-google-places-in-google-analytics/
sina_t:
  - 'true'
views:
  - 2224
  - 2224
qq_t:
  - 'true'
duoshuo_thread_id:
  - 511789
yourls_shorturl:
  - http://t.xiaoq.in/a
ta-thumbnail:
  - http://blog.xiaoq.in/thumb/cache/2011/4/259-1.jpg;http://blog.xiaoq.in/thumb/cache/2011/4/259-2.jpg;http://blog.xiaoq.in/thumb/cache/2011/4/259-3.jpg;http://blog.xiaoq.in/thumb/cache/2011/4/259-4.jpg;http://blog.xiaoq.in/thumb/cache/2011/4/259-5.jpg;http://blog.xiaoq.in/thumb/cache/2011/4/259-6.jpg;http://blog.xiaoq.in/thumb/cache/2011/4/259-7.jpg;http://blog.xiaoq.in/thumb/cache/2011/4/259-8.jpg;
categories:
  - Google Analytics
tags:
  - 7-pack
  - Google Boost
  - Google Places
  - Google Tags
  - SERPs
  - 位置搜索
  - 引荐网址
  - 本地商户
  - 本地搜索
  - 网址构建器
  - 谷歌分析
  - 高级细分
---
**本文由<span class='wp_keywordlink'><a href="http://www.yeezhe.com/" title="译者" target="_blank">译者</a></span><span class='wp_keywordlink'><a href="http://blog.xiaoq.in/" title="肖庆" target="_blank">肖庆</a></span>原创翻译，转载请注明出处，谢谢。**

Google has gone to great lengths lately to incorporate local data wherever it can. Google Place Search rolled out in late October and services such as <span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/google-tags/" title="查看Google Tags中的全部文章" target="_blank">Google Tags</a></span> and <span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/google-boost/" title="查看Google Boost中的全部文章" target="_blank">Google Boost</a></span> offer increased visibility, for a price. It’s only natural that we would want to know if investing in these add-ons is actually worthwhile.

谷歌最近在尽可能地整合本地数据方面做了很大努力。谷歌<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e4%bd%8d%e7%bd%ae%e6%90%9c%e7%b4%a2/" title="查看位置搜索中的全部文章" target="_blank">位置搜索</a></span>在（去年）十月下旬发布，如<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/google-tags/" title="查看Google Tags中的全部文章" target="_blank">Google Tags</a></span> 和 <span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/google-boost/" title="查看Google Boost中的全部文章" target="_blank">Google Boost</a></span>等提供可见性提升服务，当然这是要钱的。很自然地，我们希望知道投资在这些附加产品上是否真的值得。

Most of us naturally would turn to <span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span> for the answer, but what can you do when your referral URL says only that it’s from Google? That’s a rather vague answer with a lot of different possibilities. How can we narrow it down to traffic referred only from <span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/google-places/" title="查看Google Places中的全部文章" target="_blank">Google Places</a></span>?

我们中的大部分会很自然地求诸Google Analytics寻找答案，但是当引荐网站只是表明它们来自Google之时，你可以做什么呢？我们怎样才能把其限制到引荐流量仅来自<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/google-places/" title="查看Google Places中的全部文章" target="_blank">Google Places</a></span>？

To better justify the time and money spent on <span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/google-places/" title="查看Google Places中的全部文章" target="_blank">Google Places</a></span> for our clients, I set out to find an answer.

为了更好地节约我们客户花费在Google Places的时间和金钱，我们开始寻找一个答案。

**Method #1: Redirected Landing Page**

**方法一：重定向着陆页面**

My search for a reliable tracking method began with a question: How can we track Google Places without manual tagging? I wanted to avoid tagging initially since, as an agency, my company manages hundreds of profiles. Tagging all of them would be a huge multi-departmental project. Obviously I was going to look for a simpler way first. One method suggested to me was to use a nonexistent page on the website as the URL, then 301 redirect it to the index page. It wasn’t going to solve my “huge multi-departmental project” problem, but it was an interesting thought.

我寻找一个可靠的跟踪方法以一个问题开始：如何才能不手动构建网址来跟踪Google Places？我起初想避免构建网址，因为作为一家公司，我们管理着数百个配置文件。构建所有的回是一个跨部门的大工程。显然我将先寻找一个简单点的方法。其中的被建议的一个方式就是使用一个网站上不存在的网址，然后做301重定向到首页。这不会解决“跨部门工程”的问题，但是这是一个有趣的想法。

**Pros:** It would be relatively easy to set up, easier than manual tags. The resulting URL would be clean, visually speaking.

优点：设置会相对更简单，比手动添加标记简单多了。最终的网址在视觉上看也非常简洁。

**Cons:** Given the nature of the new blended algorithm, I’m reluctant to 301 the primary landing page I’m presenting to Google. It could be downgraded at best, and regarded as a doorway page at worst.

缺点：考虑到新的混合算法的特点，我不愿意使用301重定向至展现给Google的着陆页面。最好的结局是被降权，最坏会被认为这是桥页。

Ultimately, we didn’t test this method. The risks were simply too great.

最终，我们没有测试这种方法。风险太大了。

**Method #2: Manual Tagging**

**方法二：手动标记**

So I tested manual tagging instead. The [Google URL Builder][1] is a terrific tool:

于是我还是测试了手动标记。谷歌<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%bd%91%e5%9d%80%e6%9e%84%e5%bb%ba%e5%99%a8/" title="查看网址构建器中的全部文章" target="_blank">网址构建器</a></span>是一个很棒的工具：

 <img src="http://i587.photobucket.com/albums/ss315/RebeccaSEO/12-15-10%20google%20places%20tracking/1-url-builder.jpg" border="1" alt="" width="620" height="312" />

In the example above, I’m using the Content field to differentiate one office location from another, but this could also be done in the Campaign field. The resulting URL is then added to the Google Places profile.

在上面的例子中，我在使用Content字段区分不同的办事处地点，但是在同样也可以在Campaign中完成。生成的网址然后会被添加到Google Places的资料中。

**Pros: **Not only is the setup relatively easy, the data presentation in Google Analytics is really clean and easy to slice up. Different business locations are easily segmented out for deeper analysis of which locations are the biggest drivers.

优点：设置相对简单，展现在Google Analytics中的数据也非常简洁并容易切分。不同的商业地址可以很容易地细分出来做深入分析从而判断哪个地址带来最大流量。

 <img src="http://i587.photobucket.com/albums/ss315/RebeccaSEO/12-15-10%20google%20places%20tracking/2-campaign-source-medium.jpg" alt="" width="620" height="131" />

Isn’t it beautiful? The first thing I did once I had this was to add keywords to the mix:

不是很漂亮吗？我一看到这里做的第一件事情便是增加关键字细分。

 <img src="http://i587.photobucket.com/albums/ss315/RebeccaSEO/12-15-10%20google%20places%20tracking/3-campaign-keyword.jpg" alt="" width="620" height="298" />

Oooh… ahhh…

哦…啊…

**Cons:** It appears that adding a tracking URL triggers the dreaded “Pending Review” status instead of immediately going Active. Luckily, the change was approved within a week of submission when tested. Phew! I can’t guarantee such a short wait for everyone, of course, but the Google Places team does seem to be on top of things at the moment.

缺点：似乎添加跟踪代码触发了可怕的“正在审核”状态，而不是立即生效。幸运的是，这个改变在测试是是提交后的一周内就审核通过了。唷！当然，我不敢保证每个人都是如此短的等待，但是Google Places小组目前似乎是高高在上。

A second con is that tagging can only be used to track listings which you control. We often run up against Google Places profiles which were claimed by our predecessors who are no longer contactable, or which the clients claimed once upon a time but can’t find the login info for, or which are controlled by third parties who are still working with our client on other sites… you get the idea. In a perfect world, this wouldn’t be an issue. But it is, and until those others are magically relinquished to us, we can’t track them.

另外一个缺点是标记仅能用在你控制这的列表跟踪。我们通常管理的Google Places账户或者是被我们的上任认证了并且无法联系他们，或者是客户在之前某个时候认证了但是无法找到其登录信息，再或者是这些账户被第三方控制着，他们还仍然在与我们客户合作并处理客户其他的网站…你知道的。在一个完美世界，这本应该不是一个问题。但是，在这些其他人魔力般地放手交给我们之前，我们无法跟踪它们。

A third con is that it’s impossible to tell the difference between traffic which came from the Places profile versus traffic that came from the <span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/7-pack/" title="查看7-pack中的全部文章" target="_blank">7-pack</a></span> search results. Google sometimes pulls the URL from its index, and other times pulls it from the Places profile. To see this in action for yourself, run a search for “Houston Breast Augmentation” and hover on the first result. It goes to a “naked” URL, with no tracking on it, exactly as you would expect. Now take a look at the <span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/serps/" title="查看SERPs中的全部文章" target="_blank">SERPs</a></span> for “best plastic surgeons in Houston” where you find the the same business: 

第三个缺点是无法区分来自Google Places账户与<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/7-pack/" title="查看7-pack中的全部文章" target="_blank">7-pack</a></span>搜索结果的流量。Google有时从索引中拉取网址，有时又从Google Places账户中拉取。亲眼目睹这种情况，请搜索“Houston Breast Augmentation”然后把鼠标放在第一个结果上。这是一个“裸露”的网址，并无标记在上面，正如你所期望的那样。现在看看“best plastic surgeons in Houston”的搜索结果页面，你会发现同样的情况。

 ![][2]

Aha. So this isn’t going to filter out all traffic from the <span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/serps/" title="查看SERPs中的全部文章" target="_blank">SERPs</a></span>. And it’s kinda ugly, too.

啊。因此，这并不会完全过滤掉来自搜索结果页面的流量。

<span style="color: #ff0000;"><strong>本文由译者肖庆原创翻译，转载请注明出处，谢谢。</strong></span>

**Method #3: Capturing The Full Referring URL + Advanced Segmentation Or On-Page Filtering**

**方法三：捕捉完整的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%bc%95%e8%8d%90%e7%bd%91%e5%9d%80/" title="查看引荐网址中的全部文章" target="_blank">引荐网址</a></span>+<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e9%ab%98%e7%ba%a7%e7%bb%86%e5%88%86/" title="查看高级细分中的全部文章" target="_blank">高级细分</a></span>或者页面内过滤**

Manual tagging wasn’t going to provide me with exactly what I was after, but I remembered seeing David Harry refer to [a method of capturing full referring URLs][3]. It occurred to me that Google Places listings probably have a unique element in their URL structure which I could segment out from the rest of the noise if I (a) had the full URL and (b) knew what that unique element was.

手动标签并不会给我提供我所追求的东西，但是我记得看过David Harry提到过一种拉取完整<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%bc%95%e8%8d%90%e7%bd%91%e5%9d%80/" title="查看引荐网址中的全部文章" target="_blank">引荐网址</a></span>的方法。我突然想到Google Places列表可能有一个独特的元素在它们的网址结构中，我可以从其他干扰项中细分出来，如果我（1）有完整的网址（2）知道这个独特元素到底是什么。

I’m not going into how to set up the full referrer capture filter. Go to Reuben Yau’s post (linked in the paragraph above) to see how it’s done.

我不打算研究如何设置完整的引荐捕捉过滤器。去Reuben Yau’s的文章（在本段落上面有链接）看怎么做吧。

Once that has been set up, create an advanced segment or an on-page filter to pull out the Google Places referrals.

一旦上述设置完成，创建一个<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e9%ab%98%e7%ba%a7%e7%bb%86%e5%88%86/" title="查看高级细分中的全部文章" target="_blank">高级细分</a></span>或者页面内过滤器来拉取Google Places的引荐。

 <img src="http://i587.photobucket.com/albums/ss315/RebeccaSEO/12-15-10%20google%20places%20tracking/55-full-ref-example.jpg" alt="" width="620" height="257" />

It turns out that there are two ways a Google Places listing can render. One version uses &#8220;maps&#8221; in the URL, while the other uses &#8220;place&#8221;. At least on the surface, it looks like the difference between a normal search and a mobile search. My filter looks like this: 

结果证明Google Places列表有两种呈现方法。一个版本的网址中使用maps在，另一个使用place。至少在表面上，看上去像是普通搜索和手机搜索的区别。我的过滤器是这样设置的：

 ![][4]

**Pros:** Since the filtering works on the basis of the URL structure, profile control is unnecessary.

优点：由于过滤是基于网址结构，账号控制权限就不是必需的了。

**Cons:** It took me awhile to figure out why the manual tagging method and full referrer methods were putting up different numbers, but finally I realized that the full referrer method does NOT include the <span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/7-pack/" title="查看7-pack中的全部文章" target="_blank">7-pack</a></span> results. If you want to include 7-pack clicks, the full referrer method won’t do it for you. The data isn’t presented in such a pretty, clean way, and there’s no simple way to segment out traffic coming through different office locations. It can be done, it’s just a bit of a headache since it involves filtering for specific “cid” numbers from the URLs and knowing which insanely long number belongs to which location. The setup is a little more intense, too.

缺点：明白为什么手动标记方法和完整引荐带来不同的数字花了我好一会功夫，但是最终我意识到完整引荐的方法统计的数据不包含来自7-pack的结果。如果你想包含7-pack的点击，完整引荐的方法不适合你。因为7-pack的数据并不是以一种精致、简洁的方式呈现的，而且没有细分出来自不同办公室地点流量的简单方法。可以办到，但是由于涉及到从网址中过滤特定的cid数值并且只是哪个疯狂的长数值属于哪个地点，有点头疼。设置也同样有些麻烦。

<span style="color: #ff0000;"><strong>本文由译者肖庆原创翻译，转载请注明出处，谢谢。</strong></span>

**Method #4: Using Both Manual Tagging and Full Referrer Methods Together**

**方法四：同时使用手动标记和完整引荐方法**

Using both is how I got to this:

同时使用两种方法我得到下面的数据：

<img src="http://i587.photobucket.com/albums/ss315/RebeccaSEO/12-15-10%20google%20places%20tracking/33-mashup-with-keywords.jpg" alt="" width="620" height="286" />

Between the two, you have almost everything you could ever want to slice and dice.  I used a simple filter grab Google Places and manually tagged URLs and exclude SERPs traffic:

在这两者之中，你可以有几乎想要细分的所有数据。我使用了一个简单的过滤器来撷取Google Places和手动标记网址并且排除搜索结果页面的流量：

![][5] 

The filter works because it relies on the full referring URL to provide the bits to be filtered in and out. Once it’s in place, you can slice and dice your Google Places referral data to your heart’s content.

过滤器运行是因为它依赖于完整的引荐网址，以提供将被过滤进来或者出去的那点。一旦设置好了，你可以随心所欲地细分Google Places的引荐数据。

**本文由译者肖庆原创翻译，转载请注明出处，谢谢。英文原文地址：<a title="在谷歌分析中跟踪谷歌位置搜索的流量来源" href="http://www.seomoz.org/blog/tracking-traffic-from-google-places-in-google-analytics" target="_blank">http://www.seomoz.org/blog/tracking-traffic-from-google-places-in-google-analytics</a>**

 [1]: http://www.google.com/support/analytics/bin/answer.py?hl=en&answer=55578
 [2]: http://i587.photobucket.com/albums/ss315/RebeccaSEO/12-15-10%20google%20places%20tracking/3b-tracking-in-serps.jpg
 [3]: http://www.reubenyau.com/google-analytics-hack-obtaining-full-referring-url
 [4]: http://i587.photobucket.com/albums/ss315/RebeccaSEO/12-15-10%20google%20places%20tracking/3c-on-page-filter.jpg
 [5]: http://i587.photobucket.com/albums/ss315/RebeccaSEO/12-15-10%20google%20places%20tracking/44-mashup-filter.jpg