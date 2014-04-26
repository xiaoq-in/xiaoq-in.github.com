---
title: 使用谷歌分析跟踪内部广告系列
author: 54jack
layout: post
permalink: /google-analytics/tracking-internal-campaigns-with-google-analytics/
sina_t:
  - 'true'
views:
  - 2301
  - 2301
qq_t:
  - 'true'
duoshuo_thread_id:
  - 511883
yourls_shorturl:
  - http://t.xiaoq.in/6f
ta-thumbnail:
  - http://blog.xiaoq.in/thumb/cache/2011/5/427-1.png;http://blog.xiaoq.in/thumb/cache/2011/5/427-2.png;http://blog.xiaoq.in/thumb/cache/2011/5/427-3.png;http://blog.xiaoq.in/thumb/cache/2011/5/427-4.png;http://blog.xiaoq.in/thumb/cache/2011/5/427-5.png;http://blog.xiaoq.in/thumb/cache/2011/5/427-6.png;
categories:
  - Google Analytics
tags:
  - 事件跟踪
  - 内部广告系列
  - 外部广告系列
  - 广告系列
  - 搜索字词
  - 搜索类别
  - 网站搜索
  - 自定义变量
  - 谷歌分析
---
Internal campaigns are marketing efforts that are run on your site and promote your products and services. Here’s an example from the Boton Red Sox site. They’re using ads on the homepage to promote ticket sales.

<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%86%85%e9%83%a8%e5%b9%bf%e5%91%8a%e7%b3%bb%e5%88%97/" title="查看内部广告系列中的全部文章" target="_blank">内部广告系列</a></span>是运行在你网站上促销产品或服务的营销策略。下面是来自Boton Red Sox（<http://boston.redsox.mlb.com/>）这个网站的一个例子。他们在首页使用广告来促销门票。

[<img title="Internal ticket sale campaign on RedSox.com" src="http://cutroni.com/blog/wp-content/uploads/2010/03/Picture-1.png" alt="" width="738" height="488" />][1]

Companies should track how people react to these campaigns and which ones are most successful. But what’s the best way to do this with <span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>?

公司应该跟踪人们是如何对这些<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%b9%bf%e5%91%8a%e7%b3%bb%e5%88%97/" title="查看广告系列中的全部文章" target="_blank">广告系列</a></span>做出反应，了解哪些是最成功的。但是，使用<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="谷歌分析" target="_blank">谷歌分析</a></span>来实现这个目标的最好方法是什么呢？

Some people use the standard campaign tracking to track internal campaigns. THIS IS INCORRECT AND SHOULD NEVER BE DONE. Using the standard campaign tracking for internal campaigns will cause problems with your source data. So don’t do it!

有些人使用标准的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%b9%bf%e5%91%8a%e7%b3%bb%e5%88%97/" title="查看广告系列中的全部文章" target="_blank">广告系列</a></span>跟踪来跟踪这些<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%86%85%e9%83%a8%e5%b9%bf%e5%91%8a%e7%b3%bb%e5%88%97/" title="查看内部广告系列中的全部文章" target="_blank">内部广告系列</a></span>。**这是不正确的，切勿如此。**因为那样会造成原始数据的一些问题。因此，别那样做！

There are a few correct ways to track internal campaigns. You could use [Event Tracking][2], [Custom Variables][3] or Virtual Pageviews. But I like to use GA’s internal campaign tracking tool.

有些正确的方法可以尝试。你可以使用<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>，<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>或者虚拟页面浏览。但是我喜欢使用GA的内部<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%b9%bf%e5%91%8a%e7%b3%bb%e5%88%97/" title="查看广告系列中的全部文章" target="_blank">广告系列</a></span>跟踪工具。

What? You’ve never seen or used the GA’s internal campaign tracker? It’s in the profile settings and it’s called Site Search tracking! Did I fool you <img src="http://xiaoq.in/wp-includes/images/smilies/icon_wink.gif" alt=";)" class="wp-smiley" /> 

什么？你从未见过或者使用GA的内部广告系列跟踪工具？它在配置文件设置里面，叫做<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%bd%91%e7%ab%99%e6%90%9c%e7%b4%a2/" title="查看网站搜索中的全部文章" target="_blank">网站搜索</a></span>跟踪！被骗到没有:)

Site Search can easily be configured to track internal campaigns. Let’s walk through the steps to set it up and then the data and analysis.

<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%bd%91%e7%ab%99%e6%90%9c%e7%b4%a2/" title="查看网站搜索中的全部文章" target="_blank">网站搜索</a></span>可以很轻易地配置用来跟踪站内广告系列。让我们一步步来，先设置，然后查看数据，再分析。

## Step 1: Create a New Profile

第一步：创建新配置文件

Because we’re using Site Search for an unintended purpose it’s best to configure these settings on a new profile. It’s not possible to use Site Search for both tracking internal campaigns and internal site search within the same profile. You need to have a separate profile to track internal campaigns.

因为我们将使用<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%bd%91%e7%ab%99%e6%90%9c%e7%b4%a2/" title="查看网站搜索中的全部文章" target="_blank">网站搜索</a></span>来做其他用途，最好创建一个新的配置文件来设置。在同一个配置文件中使用网站搜索来同时跟踪站内广告系列和内部网站搜索是不可能的。你需要有一个单独的配置文件来跟踪内部广告系列。

[<img title="New Google Analytics Profile for Internal Campaigns" src="http://cutroni.com/blog/wp-content/uploads/2010/03/Picture-2.png" alt="" width="392" height="69" />][4]

## Step 2: Tag your Internal Campaigns

第二步：标记内部广告系列

Once you’ve created your new profile it’s time to tag your internal campaigns. Internal campaigns need to be tagged in a similar manner to external campaigns: you need to add query string parameterrs to your internal ad.

一旦创建完新的配置文件，接下来就是配置内部广告系列了。内部广告系列的标记方式与<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%a4%96%e9%83%a8%e5%b9%bf%e5%91%8a%e7%b3%bb%e5%88%97/" title="查看外部广告系列中的全部文章" target="_blank">外部广告系列</a></span>的基本类似：你需要添加查询参数字符串到内部广告链接中。

However, unlike external campaigns you do not use the standard link tagging parameters (`utm_campaign`, `utm_medium`, etc.). You get to make up your own parameters!

然而，同<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%a4%96%e9%83%a8%e5%b9%bf%e5%91%8a%e7%b3%bb%e5%88%97/" title="查看外部广告系列中的全部文章" target="_blank">外部广告系列</a></span>不同的是，你不需要使用标准的链接标记参数（`utm_campaign`, `utm_medium`, 等）。你可以使用自己的参数！

You can use one or two parameters for internal campaign tracking and you can name then anything you want. The reason you can use one or two parameters is that GA’s site search configuration uses two parameters, one for the search phrase and one for the search category.

你可以使用一个或者两个参数来跟踪内部广告系列，而且你可以任意命名它们。你可以使用一个或者两个的原因是，在GA的网站搜索设置中，它使用两个参数：一个是<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e6%90%9c%e7%b4%a2%e5%ad%97%e8%af%8d/" title="查看搜索字词中的全部文章" target="_blank">搜索字词</a></span>，一个是<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e6%90%9c%e7%b4%a2%e7%b1%bb%e5%88%ab/" title="查看搜索类别中的全部文章" target="_blank">搜索类别</a></span>。

Whatever you choose, make sure the parameters are not used for anything else.

无论你选择哪个，确保这些参数没有被做其他用途。

*TIP: Check your Top Content report for a complete list of your site’s query string parameters. Verify that the parameters you create are NOT in this list.*

*贴士：在“热门内容”中核查完整的查询字符参数。确认你创建的参数**没有**出现在这个名单中。*

For the sake of this post I’ll use the parameter `icn` (shor for internal campaign name). This parameter will holds the name of the internal campaign. I’m going to use the following format for the value of the campaign name parameter

在这篇文章中，我将使用icn参数（内部广告系列名称的英文首字母简写）。这个参数将作为内部广告系列使用。我将使用以下格式来确定广告系列名称参数。

`icn=[internal-campaign-name]`

I mentioned that you can use two paramters. You don’t need to use two, but GA’s site search can be confiugured to track the internal site search phrase and a site search category. We’ll use the category paramter to track the internal campaign name.

上面提到你可以使用两个参数。你不需要使用两个，但是GA的网站搜索可以配置成跟踪网站<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e6%90%9c%e7%b4%a2%e5%ad%97%e8%af%8d/" title="查看搜索字词中的全部文章" target="_blank">搜索字词</a></span>和类别。我们将使用类别参数跟踪内部广告系列的名称。

I’m going to name the second paraeter `ici` (short for internal campaign info). Again make sure the parameter you’re using does not already exist. This second parameter let’s me collect details about the ad the visitor clicked on and the location of the ad.

我将把第二个参数命名为ici（内部广告系列信息的英文首字母简写）。同样，确认这个参数之前未被使用过。第二个参数允许我收集访问者点击的广告名称和位置的详细信息。

Here’s a basic format:

这是基本格式：

`ici=[ad-creative]_[location-on-the-page]`

You can see that I’m stuffing a lot of information into the parameter. You can put whatever you want and GA will gladly suck it in. By adding more information we’ll get a granluar view of how the internal campaigns perform and which locations and variations lead to tbe most conversions.

你可以看到我加入了很多信息到这个参数中。你可以加入任何东西，GA海纳百川。通过加入更多信息，我们将获得内部广告系列表现如何，哪些位置和广告带来最佳转化率的精细化视图。

If you don’t have different types of internal ads, or just don’t care about this level of detail, then you can ignore the add internal campaign info parameter. It blank, it’s up to you!

如果你没有不同类型的内部广告，或者根本就不关心这么细致的层面，那么你可以忽视添加内部广告系列信息参数。那么这些数据将是空白，你决定！

Now you need to define the values for all the ads. Thic can get messy if you’re running a lot of internal campaign. But you can do it, just be organized! Use a spreadsheet to keep track of all the values you use.

现在你需要订阅所有广告的价值。如果你运行很多内部广告系列，那么这可能会变得十分杂乱。但是你可以做到条理清晰，只需组织下！使用一个电子表格来记录所有使用的值。

Once you’ve got al your parameters it’s time to tag your links. The exact process depends on your site. You may need to change static links, like this:

得到所有的参数之后，是时候标记链接了。确切的步骤取决于你的网站。你可能需要改变静态链接，像这样的：

< a href=”/internal-page.php?icn=2010-spring-sale&ici=stubs_home-roller >

Or if you have complicate flash ads you may need to get inside the Flash code. It depends on your site.

或者如果你使用辅助的flash广告，你可能需要深入flash代码。这取决于你的网站。

The bottom line is when somone clicks on an internal ad you want to see your internal campaign parameter on the next page. If you don’t see the parameter in the URL then you did something wrong.

底线是当某人点击某个内部广告时，你可以在下一个页面网址中看到你的内部广告系列参数。如果你没有在网址中看到希望看到的参数，之前肯定出错了。

You can use the sample spread sheet below to track the different parameters you use for your internal campaigns. The spread sheet also has a formula in column D to automatically add the parameters to your URLs.

你可以使用下面的电子表格范例来跟踪不同的内部广告系列参数。这个电子表格在D单元格中还有一个自动添加参数到网址的公式。

NOTE: There is an iFrame in this post. If you can not see it, you can view the original post [here][5] or view the Google Spreadsheet [here][6].

Once youe’ve got the parameters added to your links it’s itme to configure the Site Search settings.

注：本文使用了内部嵌套。如果你无法看到它，你可以在这里查看原始文章或者在这里查看谷歌电子表格。

## Step 3: Configure Site Search Settings

第三步：配置网站搜索的设置

Remeber, we’re configuring these settings on a new profile so we don’t break the site search in our main reporting profile.

记住，我们将在一个全新的配置文件中配置这些设置以免损坏我们主报告配置文件中的网站搜索。

Site search has three settings. First, turn site search on.

网站搜索有三个设置。第一，开启网站搜索。

Next, tell GA the name of the paramter that holds the site search phrase (in this case it’s out internal campaign name) by adding the parameter to the ‘Query Parameter’ filed.

然后，通过添加参数到“查询参数”字段来告诉GA代表网站搜索字符的参数（在这里是我们的站内广告系列名称）。

Next, choose Strip Query String Parameters. This setting will remove the parameter from the URL after GA processes the data. This is a good idea because it reduces duplicate pages in your top content reports.

接着，选择“是的，从网址中去除查询参数”。该设置将会在GA处理该数据后从网址中删除这个参数。这样做可以减少在热门内容报告中的重复内容。

*TIP: You probably want to exclude your internal campaign name parameter, and internal campaign information parameter, from your other profiles. It can really mess up your pageview data.*

*贴士：你可能还希望在其他配置文件中排除内部广告系列的名称参数，以及内部广告系列信息参数。否则，这简直将是你的页面浏览量数据一片混乱。*

If you’re using an internal campaign information parameter configure the Site Search Category settings the same way. Just make sure you use your internal campaign info parameter in the ‘Category Parameter’ setting.

如果你正在使用内部广告系列信息参数，用同样的方式设置网站搜索分类。请确保你在“类别参数”设置中使用内部广告系列信息参数。

Here’s how the settings look using the parameters from my example:

下面是本例设置截图：

[<img title="Google Analytics Internal Site Search settings" src="http://cutroni.com/blog/wp-content/uploads/2010/03/Picture-3.png" alt="" width="497" height="327" />][7]

That’s it! Let’s look at the data.

搞定！让我们看数据吧。

## The Reports

报告

Let’s start by answering a simple question: do people who respond to internal camapigns convert more or less than those that do not respond to internal camapigns? To answer this question use the Content > Site Search > Usage report. Here we can see that there were only eight visits that clicked an internal campaign. Sad! But it’s just test data.

首先，让我们回答一个简单的问题：对内部广告系列做出反应的人会转化更多还是更少？要回答这个问题，请使用内容>网站搜索>使用报告。在这里我们看到只有8个访问点击了内部广告系列。伤心！不过这只是测试数据。

<img title="Success of Internal Campaigns" src="http://cutroni.com/blog/wp-content/uploads/2010/03/Picture-8.png" alt="" width="604" height="240" />

Now let’s drill deeper ad identify which inernal camapigns are most effective. Use the Content > Site Search > Search Terms report. Rather than search phrases this report contains the names of all internal campaigns. Again, what was the response to the campaign? Was it worth the effort? Don’t forget to check the Goals tab and the Ecommerce tabs (if applicable) to measure outcomes!

现在，让我们进一步深入到广告以识别那个内部广告系列是最有效的。使用内容>网站搜索>搜索字词报告。这个报告中包括了所有内部广告系列的名称而不是搜索字词。再看下，访问者对这个广告系列的反应如何？广告是否值得？别忘记查看目标选项卡以及电子商务选项卡（如果有的话）以测量回报。

<img title="Internal campaign in the Google Analytics Search Terms report." src="http://cutroni.com/blog/wp-content/uploads/2010/03/Picture-9.png" alt="" width="619" height="237" />

But let’s drill deeper to understand which ads within those campaigns are working. Click on a campaign name and choose Category from the Analyze drop down.

但是，让我们进一步深入数据，了解这些广告系列中哪些广告有效。点击广告系列名称，然后从分析下拉菜单中选择类别。

<img title="Analyze a given internal campaign by the Category data" src="http://cutroni.com/blog/wp-content/uploads/2010/03/Picture-10.png" alt="" width="491" height="135" />

Now we’re looking at all of the information that we put into the `ici` query string parameter for this particular campaign name. If we had multiple internal ads we’d be able to differentiate ad placements and creative variations.

<img title="Segmenting an internal campaign in Google Analytics." src="http://cutroni.com/blog/wp-content/uploads/2010/03/Picture-11.png" alt="" width="577" height="105" />

现在我们看到这个特定广告系列名称中所有已经添加ici查询字符串参数的信息。如果你有多个内部广告，我们就可以区分不同广告位置及创意。

Don’t forget to use the Goals and Ecommerce tabs to measure outcomes! This is what most people want to know: did internal campaigns, and specifically which internal campaigns, generated **revenue and conversions**?

别忘记使用目标及电子商务选项卡来测量回报！这是大多数人想知道的：内部广告系列，特定来说哪个内部广告系列，产生出价值及转换？

But we can do more. Now change to the Content > Site Search > Start Pages report. Now you can see which page people were on when they click on an internal ad. Again, more insight into where visitors responded to an internal campaign.

但是，我们还能做更多。现在切换到内容>网站搜索>起始网页。现在你可以看到人们点击内部广告时位于哪个页面。再次，深入查看访问者在哪里对内部广告系列做出了反应。

<img title="How to identify start pages for Internal Campaigns." src="http://cutroni.com/blog/wp-content/uploads/2010/03/Picture-13.png" alt="" width="489" height="97" />

And for all those marketing folks that are so concerned with internal campaigns, how about creating a nice custom report and automating the delivery or, better yet, use the Custom Report Sharing feature to share this report with others. People will love this because you can change the wording so it does not say Site Search it says Internal Campaigns Report.

对所有关注内部广告系列的营销人员来说，创建一个不错的自定义报告并自动发送或者使用自定义报告的分享功能来与其他人分享这个报告，如何？人们将喜爱这个，因为你可以改变其中的措辞，把它命名为内部广告系列报告而非网站搜索报告。

But wait, there’s more! What about using a secondary dimension to view the external marketing campaigns (or sources, or mediums) that drive visitor to react to internal campaigns. Perhaps the extrnal creative has some influence over how visitors react to the internal campaign creative. The data isn’t so hot in the image below, but you get the idea.

不过等一下，还可以做更多！使用一个次级指标来查看那些驱使访问者对内部广告系列做出反应的外部营销广告系列（或者广告来源或者广告媒介）。或许这个外部创意对于访问者对内部广告创意的反应有些影响。下面图片中的数据并不火，但是你明白意思即可。

<img title="Use a secondary dimension to view external campaigns for each internal campaign." src="http://cutroni.com/blog/wp-content/uploads/2010/03/Picture-12.png" alt="" width="602" height="73" />

And finally, the ultimate in analysis, internal campaign attribution. We can use the Search Term Refinement feature if visitors click on multiple internal campaigns. Google Analytics will track all subsequent site searches, but in our case follow up site searches are actually additional internal campaigns that the visitor responded to. Honestly, I have never found any insights from this type of analysis, but you can do it if you want!

最后，分析中的极致，内部广告系列分布。如果访问者点击了多个内部广告系列，我们可以使用搜索字词重定义功能。<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%b0%b7%e6%ad%8c%e5%88%86%e6%9e%90/" title="查看谷歌分析中的全部文章" target="_blank">谷歌分析</a></span>将跟踪所有次级网站搜索，但是在我们这个例子中随后的网站搜索事实上是访问者对额外的内部广告系列做出的反应。老实说，我从未从这类分析中领悟到任何东西，但是如果你想的话你可以做到的。

Ok, I’ve officially entered nerdville.

好吧，我已经正式步入健忘时代。（<span class='wp_keywordlink'><a href="http://www.yeezhe.com/" title="译者" target="_blank">译者</a></span>注：Neville Longbottom，纳威·隆巴，是英国作家J·K·罗琳的儿童奇幻小说《哈利·波特》系列中的人物，他成绩差的原因主要是顿常常忘东忘西）

I think you get the idea. By adding all this data you can do many different kinds of segmentation and analysis. More than enough to understand the behavior of your site visitors and how your internal campaigns perform.

我认为你已经明白。通过添加所有这些数据，你可以做很多不同的细分和分析。不要停留于理解网站访问者的行为以及你的内部广告系列表现如何。

Last but not least, I’ll mention that you can track internal campaigns using events and custom variables. But both of those solutions require coding. And that requires working with IT. Using Site Search, in most cases, will not require any code changes to your site.

最后，我提下你可以使用<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>或者<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>来跟踪内部广告系列。但是这两个解决方案需要编写代码。需要计算机基础。使用网站搜索在大部分情况下，不需要对网站的代码做任何改变。

译者：<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/" title="肖庆" target="_blank">肖庆</a></span> <span style="color: #ff6600;">原创翻译，转载请注明出处</span>

原文：<a title="使用谷歌分析跟踪内部广告系列" href="http://cutroni.com/blog/2010/03/30/tracking-internal-campaigns-with-google-analytics/" target="_blank">http://cutroni.com/blog/2010/03/30/tracking-internal-campaigns-with-google-analytics/</a>

 [1]: http://cutroni.com/blog/wp-content/uploads/2010/03/Picture-1.png
 [2]: http://cutroni.com/blog/2007/10/16/event-tracking-pt-1-overview-data-model/
 [3]: http://cutroni.com/blog/2009/10/20/google-analytics-custom-variables-overview/
 [4]: http://cutroni.com/blog/wp-content/uploads/2010/03/Picture-2.png
 [5]: http://cutroni.com/blog/2010/03/29/tracking-internal-campaigns-with-google-analytics
 [6]: http://spreadsheets.google.com/ccc?key=0AnmzEWCHMzUPdFpuRXJkOTZseW5KQVhRTUJmRUJWZlE&hl=en
 [7]: http://cutroni.com/blog/wp-content/uploads/2010/03/Picture-3.png