---
title: 掌握谷歌分析自定义变量
author: 54jack
layout: post
permalink: /google-analytics/mastering-google-analytics-custom-variables/
sina_t:
  - 'true'
views:
  - 5860
  - 5860
qq_t:
  - 'true'
duoshuo_thread_id:
  - 511886
ratings_users:
  - 0
ratings_score:
  - 0
ratings_average:
  - 0
yourls_shorturl:
  - http://t.xiaoq.in/26
ta-thumbnail:
  - http://blog.xiaoq.in/thumb/cache/2011/5/451-1.png;http://blog.xiaoq.in/thumb/cache/2011/5/451-2.png;http://blog.xiaoq.in/thumb/cache/2011/5/451-3.png;http://blog.xiaoq.in/thumb/cache/2011/5/451-4.jpg;
categories:
  - Google Analytics
tags:
  - 事件跟踪
  - 自定义变量
  - 自定义报告
---
<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="谷歌分析" target="_blank">谷歌分析</a></span>的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>被各大网站使用，比如豆瓣，赶集，58同城等，主要应用在记录注册会员的站内行为，网站区域及类别，通过分析可以得出网站用户的兴趣，用户关注话题及活跃区域等。当然，博客网站也可以使用这个功能来跟踪关注度高的分类或去除管理员登陆等。

下文由<span class='wp_keywordlink'><a href="http://www.yeezhe.com/" title="译者" target="_blank">译者</a></span><span class='wp_keywordlink'><a href="http://blog.xiaoq.in/" title="肖庆" target="_blank">肖庆</a></span>原创翻译自Justin Cutroni的博客（Analytics Talk ），原文请点击<a title="掌握谷歌分析自定义变量" href="http://cutroni.com/blog/2011/05/18/mastering-google-analytics-custom-variables/" target="_blank">此处</a>，版权归原作者所有。

I’ve got a stack of posts that I want to write, and realized that the all deal with Custom Variables. So, to make sure that we’re all on the same page when it comes to custom vars, here’s my guide to Mastering <span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span> Custom Variables.

我有很多文章想写，并且意识到它们都是关于<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>的。因此，为了使我们在说<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>的时候得到同样的页面，下面将引导你掌握谷歌分析的自定义变量。

For those of you that have not used custom variables, CVs are a way for you to insert custom data into Google Analytics. What kid of custom data? Almost any kind of data. As long as the data is available to you in the source code of a web page you can pass it to Google Analytics via a custom variable.

对没有用过自定义变量的你们来说，简历是插入自定义数据到谷歌分析中的一种途径。哪些自定义数据？几乎任何的数据。只要这些数据在网页的源文件中存在，你就可以通过自定义变量把它传递到谷歌分析中。

There are 4 parts to a custom variable:

自定义变量由四部分组成：

1. The name of the variable自定义变量的名称  
2. The values for each variable自定义变量的值  
3. The index or slot of the variable and the scope of the variable自定义变量的索引或位置  
4. The scope of the variable自定义变量的范围

**Name & Value**

**名称和值**

Custom variables are name-value pairs of data. The name is also called the “key”. To create a custom variable you define the name of a custom variable, like Favorite Baseball Team, and then assign it different values, Red Sox, Braves, Giants, etc.

自定义变量是名称与值配对的数据。自订阅变量的名称也叫“键”。为了创建一个自定义变量，你需要订阅该变量的名称，比如称之为“我最喜爱的棒球队”，然后给它赋予不同的值，如“红袜队”，“勇士队”，“巨人队”，等等。

Google Analytics will show you a list of all the custom variable names in a list and then let you drill down into the list and see all of the values.

谷歌分析将给你以列表的形式展示所有自定义变量的名称，然后你可以深入表单查看所有值。

Here’s an example. I use a custom var named “Year” to track the publication year for all my posts on this blog. I can view which year had the most popular content by finding “Year” in the Visitors > Demographic > Custom Variables report.

下面是一个例子。我使用“年”这个自定义变量来跟踪我这个博客上所有文章的发布年份。我可以通过在“访问者>受众人口统计特点>自定义变量”报告中查找年份来看到哪年有最受欢迎的内容。

<img title="Google Analytics custom variables report" src="http://cutroni.com/blog/wp-content/uploads/Screen-shot-2011-05-16-at-10.21.36-PM.png" alt="Google Analytics custom variables report" width="778" height="256" />

Then I can click on “Year” to a get a list of all the values:

然后我可以点击“年份”来得到一份所有值的清单：

<img title="Values for a Google Analytics Custom Variable" src="http://cutroni.com/blog/wp-content/uploads/Screen-shot-2011-05-16-at-10.23.56-PM.png" alt="Values for a Google Analytics Custom Variable" width="779" height="365" />

Custom variables can also be used in custom reports and advanced segments. The name of the custom variable becomes the “Key” dimension and the value of the custom variable becomes the “Custom Variable Value” dimension.

自定义变量可以用在<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e6%8a%a5%e5%91%8a/" title="查看自定义报告中的全部文章" target="_blank">自定义报告</a></span>和高级细分中。自定义变量的名称变为“键”，自定义变量的值也变为“自定义变量值”维度。

<img title="Google Analytics Custom Variable Dimensions" src="http://cutroni.com/blog/wp-content/uploads/Screen-shot-2011-05-18-at-8.18.09-AM.png" alt="Google Analytics Custom Variable Dimensions" width="190" height="254" />

**Index or Slot**

**索引或位置**

The index is a way to organize your custom variables. Index is also referred to as “slot”. At a basic level, you get 5 custom variables. But this can actually be misleading. Think of the index as a parking lot with 5 parking space. You can put or “park” a custom variable in each space.

索引是组织你的自定义变量的一种方式。索引也称作“位置”。在基础层次，你可以获得5个自定义变量。但是这可能会造成误解。把索引看成一个有5个停车位的停车场。你可以在每个空间放置或者“停靠”一个自定义变量。

You can technically have more than 5 custom variables, but we need to discuss the next concept, scope, and how it impacts the index.

在技术上来说，你可以有超过5个自定义变量，但是我们需要讨论下一个概念，范围，以及它如何影响索引。

**Scope**

**范围**

The key to mastering custom variables is understanding the scope. The scope of a custom variables determine how long the custom variable will persist.

掌握自定义变量的核心在于理解范围。自定义变量的范围决定了该自定义变量能生存多久。

If we use the parking lot analogy, the scope determines how long a car will stay parked in the custom variable parking lot.

如果我们使用停车场这个比喻，范围决定了一辆汽车能够在自定义变量这个停车场中停靠多久。

There are three different scopes for Google Analytics Custom Variables:

对谷歌分析自定义变量而言，有三种不同的范围：

*Page Level: A page level custom variable will only persist for as the visitor is viewing the page where the custom variable has been set. Once the visitor moves to a new page the custom variable will expire.*

*页面级：页面级自定义变量仅当访问者浏览设置了自定义变量的页面时*

*Visit Level: A visit level custom variable will persist for the visitor’s entire visit. Once the visit ends the custom variable will expire.*

访问级：访问级自定义变量会在整个访问期间保留。一旦访问终止，该自定义变量将过期。

*Visitor Level: A visitor level custom variable will persist for 24 months as a cookie on the visitor’s machine until the visitor deleted her cookies.*

访问者级：除非被访问者删除，访问者级自定义变量会以cookie形式在访问者的设备上存在24个月。

Where scope really gets complicated is when we use it with the index. Remember, you have 5 slots that can hold a custom variable. Once you place a custom var in a slot that *SLOT BECOMES FILLED* and you can not place another custom var into the slot.

当与索引同时使用时，范围变得复杂起来。记住，你有5个位置来放置自定义变量。一旦你再某个位置放置了一个自定义变量，那个位置变为字段，而且你无法放置另外一个自定义变量到该位置。

Scope and index work in tandem to determine how many custom variables you have available at any given time.

范围和索引同时运行来决定在任意指定时间有多少自定义变量。

Let’s start with a visitor level custom variable.

让我们从访问者级自定义变量开始。

<img title="Google Analytics Custom Variables: Index or Slot" src="http://cutroni.com/blog/wp-content/uploads/ParkingLot1-300x225.jpg" alt="Think of the index as a parking lot with 5 spaces." width="300" height="225" />

When you place a visitor level custom var in a slot that slot remains filled until you delete the custom var. Remember a visitor level var is stored as a cookie so you have to actually delete the cookie. So, if you set a visitor scoped custom variable in slot 1 you can NEVER use slot one again. Unless you want to erase the custom var you set in slot 1.

当你在某个位置放置一个访问者级自定义变量时，那个位置就被填充，指定你删除该自定义变量。记住，访问者级变量作为cookie被存储，除非你真的删除了它。因此，如果你在位置1设置了一个访问者范围的自定义变量，你将无法再使用位置1。除非你想清除位置1的自定义变量。

Every time the visitor comes back to your website slot 1 will be filled because there is a cookie (named __utmv) on the visitor machine.

每次访问者来到你的网站，位置1将被填充，因为在访问者的设备上有一个cookie（称为_utmv）。

*PARKING ANALOGY:* There is a car in parking space 1. The car has no tires… and no engine… it’s not going anywhere soon… unless it gets towed.

停车比喻：在停车位1有1辆车。这车没有轮胎&#8230;而且没有引擎&#8230;它哪也不会去，除非被拖走。

When you create a visit level custom variable and place it in a slot, that slot remains full for the entire visit. Once the visit ends that slot opens up and you can place another variable in that slot.

当你创建一个访问级自定义变量并把它放置在一个位置，该位置会在整次访问中保持填充状态。一旦该访问终止，那个位置将会开启，然后你可以放置另外一个变量到那个位置。

Unlike the visitor scope custom variable there is no cookie. So when the visitor comes back to your site that slot is open.

与访问者访问自定义变量不同的是，它没有cookie。因此当访问者回到网站时，那个位置会开启。

*PARKING ANALOGY:* There is a car in a parking space 1, but just for the day. The spot will be vacated at the end of the day and someone else can park there.

停车比喻：在停车位1有1辆车，但只停当天。那个位置会在这天结束时空出来，然后其他人可以在该处停车。

When you create a page level custom variable and place it in a slot that slot remains filled until the visitor moves to another page. Once the visitor moves to another page the slot opens up and you can place another variable in the slot.

当你创建页面级自定义变量并把它放置到一个位置时，除非访问者转到另外一页，该位置会保持填充状态。一旦访问者转到另外一页，那个位置会开启，然后你可以放置另外一个变量到该位置。

*PARKING ANALOGY:* There is a car in a parking space 1, but someone is just running into a store. The engine is idling and the spot will open up in 5 minutes.

停车比喻：在一号停车位有一辆车，但是开车人只是跑进一家商店而已。引擎仍然在空转，那个位置会在5分钟后空出。

Let’s look at a couple of examples:

让我们看一些例子：

Example 1: A visitor on a news site logs in. I set 5 visitor scoped custom variables. This means that whenever the visitor comes back to the website ALL five slots are filled. I can never use any other custom variables unless I erase or over-write one of the existing variables.

例一：一个新闻网站的访问者登录。我设置了5个访问者级自定义变量。这意味着无论这个访问者何时回到网站，所有的五个位置被填充。我无法使用任何其他的自定义变量，除非我清除或者覆盖存在的一个变量。

Example 2: A visitor is on a blog. Each blog post is categorized 3 ways using a page level custom variable. on every page I set the same 3 custom variables. When a visitor logs in I set a visitor custom variable to identify them as a member. So now I have 3 page level variables and one visitor level variable. The slot that contains the visitor level variable will always remain full, so I need to make sure that I always place my page level variables in the same slots.

例二：访问者在一个博客上。每篇博客文章都通过一个页面级自定义变量分类，在每个页面我设置了3个自定义变量。当访问者登录进来，我设置一个访问者级自定义变量来识别其为会员。因此，现在我有3个页面级变量，以及一个访问者级变量。包含访问者级的自定义变量会一直保持填充状态，因为我需要区别我总是把我的页面级变量放置到相同的位置。

Example 3: A visitor logs into a news site. I set 5 page level custom variables when they log in to record various pieces of information about their membership. One the next page I fire of 5 different custom variables to record information about their past browsing history. In this senario I have actually set 10 custom variables. How? Because they are all page level custom variables. The slots associated with a page level custom var open up when the visitor moves to a new page.

例三：访问者登录到一个新闻站点。当他们登录进来时，我设置5个页面级自定义变量来记录关于他们会员关系的种种信息。在下一页，我释放出5个不同的自定义变量来记录关于他们过往浏览记录的信息。在这里我实际设置了10个自定义变量。如何做到的呢？因为他们都是页面级自定义变量。与页面级自定义变量相关的位置在访问者访问新页面时候释放出来。

Hopefully this explains how you can technically have more than 5 custom variables.

但愿这些解释了如何技术上拥有超过5个自定义变量。

**The Code**

**代码**

Like everything else in Google Analytics, you implement Custom Variables using JavaScript. All of the topics we discussed above, index, name, value and scope, are all part of the JavaScript.

如谷歌分析中其他的任何东西，你使用JavaScript来应用自定变量。所有的话题都在上面讨论过了，索引，名称，值，范围，他们都是JavaScript的一部分。

Here’s the standard Async code snippet:

这是标准的异步代码片段：

`_gaq.push('_setCustomVar',index,'name','value', scope);`

The index is a number, from 1 through 5.

索引的值是从1到5的数字。

The scope is also a number. A value of 1 indicates a visitor scoped custom variable, a value of 2 indicates a visit level custom variable, and a value of 3 indicates a page level custom variable.

范围同样是数字。值1表明是访问者级自定义变量，<span style="color: #ff0000;">值2</span>表明是访问级自定义变量，值3表明是页面级自定变量。

The name and the value are just plain text. Whatever you enter into the code above will be pulled into Google Analytics.

名称和值都是普通文本，无论你填入上面值，它们都会被填充到谷歌分析中。

Where do you put this code? That’s the hard part. You place this code when you want to create a custom variable. You may want to categorize all of the pages on your site using a page level custom variable. In this case you might place the custom var code in the standard GA code snippet, like this:

把这些代码放置在哪里呢？这是难点。当你需要创建自定义变量时，你放置这个代码。你可能想对你网站的所有页面通过使用页面级自定义变量来分类。在这种情况下，你可以把自定义变量放到GA的代码片段中，像下面这样：

`<script type="text/javascript">// <![CDATA[<br />
var _gaq = _gaq || [];<br />
_gaq.push(['_setAccount', 'UA-XXXXXX-1']);<br />
_gaq.push(['_setCustomVar',1,'PageCategory','Sports', 3]);<br />
_gaq.push(['_trackPageview']); `

(function() { var ga = document.createElement(&#8216;script&#8217;); ga.type = &#8216;text/javascript&#8217;; ga.async = true; ga.src = (&#8216;https:&#8217; == document.location.protocol ? &#8216;https://ssl&#8217; : &#8216;http://www&#8217;) + &#8216;.google-analytics.com/ga.js&#8217;; var s = document.getElementsByTagName(&#8216;script&#8217;)[0]; s.parentNode.insertBefore(ga, s); })();  
// ]]>  
</script>

Or, if you’re going to identify someone as a ‘member’ of your site, you might place the code on a page after the visitor logs in. Like this:

或者，如果你想识别网站的访问者是否为会员，你可以把代码放到访问者登录后的页面，像这样：

`<script type="text/javascript">// <![CDATA[<br />
var _gaq = _gaq || [];<br />
_gaq.push(['_setAccount', 'UA-XXXXXX-1']);<br />
_gaq.push(['_setCustomVar',1,'VisitorType','Member', 1]);<br />
_gaq.push(['_trackPageview']); `

(function() { var ga = document.createElement(&#8216;script&#8217;); ga.type = &#8216;text/javascript&#8217;; ga.async = true; ga.src = (&#8216;https:&#8217; == document.location.protocol ? &#8216;https://ssl&#8217; : &#8216;http://www&#8217;) + &#8216;.google-analytics.com/ga.js&#8217;; var s = document.getElementsByTagName(&#8216;script&#8217;)[0]; s.parentNode.insertBefore(ga, s); })();  
// ]]>  
</script>

But you can also attach the code to visitor action, like `onClick` events.

但是你还可以把这些代码附加到访问动作，比如onClick事件。

You can also create custom variables for mobile devices using the [iOS SDK and the Android SDK][1]. How cool is that!

你还可以使用iOS SDK及Android SDK为移动设备创建自定义变量。多酷啊！

And some of the super nerds I work with at [Cardinal Path][2] have been able to hack custom variables and set them using the Google Analytics Mobile Tracking code for low-end mobile devices.

而且，我在Cardinal Path的超级电脑迷同事已经能够hack自定义变量并且使用谷歌分析移动跟踪代码来跟踪低端移动设备。

Regardless of the platform that you’re tracking, you can probably use a custom variable.

无论你跟踪什么平台，你几乎都可以使用自定义变量。

**Super Nerd Stuff**

超级讨厌的东西

Custom variables are not without their limitations and oddities. Here are a few things you need to be aware of when implementing:

自定义变量同事也有其限制和古怪。下面是在应用时需要注意的一些事情：

1. What happens if you place a custom variable in a slot that is already filled? The last value placed in the slot is applied to the visit.如果你放置了一个自定义变量到已经被填充的位置，会怎样？最后放置到该位置的值会被应用到访问。

2. Custom variables are sent to Google using the same invisible image request. In the old days (ie two months ago) the size of this request was limited to 2048 characters by the browser. Because this limitation can really restrict data collection, Google decided to limit the size of your custom variable. This means that the name – value combination must be less than 64 characters. I know, this sucks.自定义变量使用相同的不可见图片请求而发送到谷歌。在之前（即两个月前），该图片请求大小被浏览器限制在2048个字符。因为该限制确实限制了数据收集，谷歌决定限制限制你自定义变量的大小。这就意味着，名称-值的组合必须少于64个字符。我知道，这太糟糕了。

BUT, Google has since changed how it collects data. The size of the image request is now 8000 + characters. So, in theory, Google could kill the 64 character CV limit. But they have not…

**但是**，谷歌已经改变了其收集数据的方式。图片请求的大小限制是8000多个字符。因此，理论上说，谷歌可以去除64个字符的限制。但是，他们却没有&#8230;&#8230;

3. Custom Variable processing lags the standard data processing by about 24 hours. However, if you add a custom variable to a custom report it will be visible. I know, completely weird.自定义变量和标准数据相比有大概24小时的延迟。然后，如果你添加一个自定义变量到<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e6%8a%a5%e5%91%8a/" title="查看自定义报告中的全部文章" target="_blank">自定义报告</a></span>，它会显现出来。我知道，完全不可思议。

4. Page level custom variables are more-or-less the same as an event. When you create an Advanced Segment using a page-level custom variable, GA will return the number of visits that included that custom var. So, if you don’t have enough slots available you may want to consider using an event.页面级自定义变量或多或是与事件是一样的。当你使用一个页面级自定义变量创建高级细分时，GA会返回包含该自定义变量访问的数值。因此，如果你没有足够的可用位置，你或许可以考虑使用<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>。

5. When you set a custom variable the data is sent immediately back to Google Analytics via an image request. This means that if you set a custom variable, on the last page of a visit and AFTER the pageview is recorded, that custom variable will NOT be collected by Google Analytics. If you can, put your custom variable code BEFORE `_trackPageview()`.当你设置一个自定义变量时，数据会迅速通过一次图片请求发送回谷歌分析。这就意味着如你设置了一个自定义变量，在一次访问的最后一页并且该页面访问被记录**之后**，该自定义变量不会被谷歌分析收集。如果可能的话，把自定义变量的代码放置在_trackPageview()**之前**。

That’s ALL I have to say about custom variables. Hopefully this gives you a good baseline understanding of how they work and how to implement them.

这是关于自定义变量我想说的。希望这会对你在理解自定义变量是如何工作以及如何应用它们方面提供一个很好的基础。

If you’re using custom variables leave a comment. I’d love to hear how you’re using them.

如果你正在使用自定义变量，请评论吧。我希望听到你们是如何使用它们的。

 [1]: http://code.google.com/mobile/analytics/docs/#mobilesdks
 [2]: http://cardinalpath.com/