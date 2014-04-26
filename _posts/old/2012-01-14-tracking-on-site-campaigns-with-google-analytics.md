---
title: 使用Google Analytics跟踪站内广告系列
author: 肖庆
layout: post
permalink: /google-analytics/tracking-on-site-campaigns-with-google-analytics/
sina_t:
  - 'true'
views:
  - 7321
ratings_users:
  - 1
ratings_score:
  - 5
ratings_average:
  - 5
duoshuo_thread_id:
  - 511944
yourls_shorturl:
  - http://t.xiaoq.in/5
ta-thumbnail:
  - https://xiaoq.in/thumb/cache/2012/1/589-1.jpg;
categories:
  - Google Analytics
tags:
  - GA
  - 事件操作
  - 事件标签
  - 事件类别
  - 事件跟踪
  - 内部广告系列
  - 网站搜索
  - 虚拟页面跟踪
---
<span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>（<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>）没有内置的方法来监控站内广告系列的表现，这是它的一个弊端，但是这可以通过一点“破解”（高级设置）来克服&#8230;尽管<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>提供一些确实好用的工具来跟踪外部广告系列，但是我对这种奇怪的忽视感到有些震惊，竟然没有一种跟踪<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%86%85%e9%83%a8%e5%b9%bf%e5%91%8a%e7%b3%bb%e5%88%97/" title="查看内部广告系列中的全部文章" target="_blank">内部广告系列</a></span>的备选方案。

<center>
  <img src="http://techpad.co.uk/custom/images/medium/4ef394b052a07.jpg" alt="Tracking on-site campaigns with Google Analytics" width="426" height="293" />
</center>

<p style="text-align: center;">
  Copyright © House of Fraser
</p>

或许<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%86%85%e9%83%a8%e5%b9%bf%e5%91%8a%e7%b3%bb%e5%88%97/" title="查看内部广告系列中的全部文章" target="_blank">内部广告系列</a></span>跟踪工具将会成为<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>小组几乎每个月开发的众多新功能之一？

它没有提及（是我还是要说，尽管存在一些冒险的建议）使用utm_campagin跟踪参数来跟踪<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%86%85%e9%83%a8%e5%b9%bf%e5%91%8a%e7%b3%bb%e5%88%97/" title="查看内部广告系列中的全部文章" target="_blank">内部广告系列</a></span>着实是一个糟糕的主意，因为当用户点击已经以这种方式标记的内部链接时，这会覆盖它们的原始来源，从而丢失GA历史数据。

还有一个风险是附加在URL后的额外广告系列参数可能会产生重复文本的问题。Google SERPS（搜索结果排名页）中存在太多这样的例子。Google或许忽视这些，但是其他搜索引擎可能不会。

### 广告指标

如果你思考过，其实内部广告系列实际上是一种站内广告，那么我认为我们应该使用与我们监控付费广告营销的表现相同的指标和KPI来测量它们。

GA实际需要，但是目前缺乏的，是用一个简单的方案来监控内部广告系列，以便营销人员可以看到总体的展现量，点击率，转化率，每次点击价值，广告系列总收益，平均每单价值以及众多的其他指标。

能够看到所有的这些将意味着我们可以更好地优化站内营销。

然而，除非我们写一些代码来扩展默认的跟踪并且发送这些数据到GA中，或者（有据可依的）写一些额外的暧昧来导出GA的数据进行外部分析，否则要做到这个并不容易。

### 我应该测量什么？

**总体展现量**  
为了测量我们内部广告系列的点击率（CTR），我们将需要对每次广告被展示进行记录，从而测量这个广告展示给了多少访客。

**点击率**  
为了决定我们的广告对于吸引客户点击的效果，我们将需要测量每个广告单元的点击，然后测量每个展现的广告的点击率

**交易**  
为了让我们看到一个广告带来了多少交易，我们将需要记录从广告点击带来的所有交易，或者哪些交易应该归属于广告。

**广告系列收益**  
我们还需要了解该广告系列创建带来的总收益。那需要基于我们对交易测量设置的类似标准。

**平均每单价值**

****这个广告创意带来的所有交易的平均每单价值是多少？我们可以通过交易总价值除以交易总数量来得出。

**转化率**  
为了获得我们的转化率，以让我们了解该广告对于促进点击了广告的客户转化为购买者的效果，我们只需要了解唯一点击和交易的数量。

### 我们如何来测量它？

到配置一个系统来在GA中记录所有需要的数据，我们有三个选项：<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%99%9a%e6%8b%9f%e9%a1%b5%e9%9d%a2%e8%b7%9f%e8%b8%aa/" title="查看虚拟页面跟踪中的全部文章" target="_blank">虚拟页面跟踪</a></span>，站内搜索和<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>。

需要页面跟踪也可以让我们捕捉到一些数据，但是他们对于这些问题有限限制。

Justin Cutroni的<a title="站内搜索跟踪内部广告系列" href="http://xiaoq.in/google-analytics/tracking-internal-campaigns-with-google-analytics/" target="_blank">站内搜索方案</a>是另外一个选项。它通过在每个广告系列的URL后附加一个额外的自定义参数，然后传递这些数据到一个独立的配置文件，最后再通过GA内置的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%bd%91%e7%ab%99%e6%90%9c%e7%b4%a2/" title="查看网站搜索中的全部文章" target="_blank">网站搜索</a></span>功能来对数据进行分解。

然而，<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>可以让你捕捉机会上述的每个数据集，而且比其他两个方法更利索。

它可以用来跟踪广告展现量，点击数，产生的购买及其价值。

而且它也很容易植入你的电子商务平台，以便你可以无需在GA账户中设置任何东西来设置永久性的跟踪应用。

让我们设想你正在我们的网站首页使用一个幻灯片促销，并且希望设置<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>来记录所有这些数据。我们怎么样才能设置好呢？

### 第一步：记录广告展现量

为了记录广告展现量，我们需要添加事件跟踪代码到展现每个促销幻灯的JavaScrip代码中。

我们希望，每次这个广告系列幻灯被展示在页面上时，在GA中都记录为一个事件，以便我们能够记录幻灯小工具中的每个幻灯展现的总数。

使用事件跟踪来跟踪这种被动事件曾经会造成非跳出，从而影响征战的跳出率并且污染你的数据。

然而，一个叫做opt_noninteraction的新参数现在让“不影响跳出率进行被动事件跟踪”更可行。

每次一个新的幻灯展示，你需要激活如这种代码：\_gaq.push(['\_trackEvent','Campaign impressions','Home page slider','Summer sale','',true]);

在此，我们针对所有展示数据创建一个叫做“&#8217;Campaign impressions&#8217;”的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e7%b1%bb%e5%88%ab/" title="查看事件类别中的全部文章" target="_blank">事件类别</a></span>，<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e6%93%8d%e4%bd%9c/" title="查看事件操作中的全部文章" target="_blank">事件操作</a></span>为“Home page slider”，<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e6%a0%87%e7%ad%be/" title="查看事件标签中的全部文章" target="_blank">事件标签</a></span>为“Summer sale”，传递一个空值，并且设置非互动值为true是十分重要的。

这将记录所有幻灯的展示，所有特定夏季促销幻灯片的展示，通过这些我们可以计算出其他的指标。

### 第二步：记录广告点击

记录广告点击非常直接了当，因为我们可以仅需对这个广告系列把我们的代码添加到href的一个onclick处理器中。比如onclick=&#8221;\_gaq.push(['\_trackEvent','Campaign clicks','Home page slider','Summer sale','',false]);&#8221;

除了在事件中记录原始点击事件，我还推荐添加一个_setCustomVar()的页面级别范围的函数。

如果一个用户点击率首页幻灯中的“Summer sale”，我们将可以看到他们是否通过该这个点击进行了购买，从而可以让我哦们了解到每个幻灯的转化率。

### 第三步：计算来自数据的指标

**总展现量**：在幻灯中每个幻灯片的总展现量可以再内容>事件跟踪>类别>Slider name > Slide name中看到。

**总点击数**：我们可以再内容>事件跟踪>类别> Campaign clicks >Slider name > Slide name中看到。

**点击率**：总点击数除以总展现量 。

**广告系列价值**：内容>事件跟踪>类别> Campaign clicks > Slider name > Slide name，然后在价值选项卡下的电子商务跟踪中查看。

**平均每单价值**：  查看某个特定幻灯的平均每单价值：平均每单价值：内容>事件跟踪>类别> Campaign clicks > Slider name > Slide name，平均价值。

**转化率**：总点击数除以100，然后乘以交易总数，从而获得每个幻灯的转化率。

### 我们能够怎样更好地提升效果？

现在你已经获得了这些重要的指标，你将可以看到促销幻灯及各个幻灯的表现，以及哪个有效，哪个无效。

然后你可以开始逐步调整以查看你是否可以提升它们的效果。

A/B测试或者多变量测试是测试不同变体的很好方式，如果你集成了网站优化工具和GA，你还可以利用细分来查看底线以上的趋势。

如果你知道来者某个维度的客户更有可能对一个不同的创意做出反应，那么你需要尝试并定位他们。

<span class='wp_keywordlink'><a href="http://www.yeezhe.com/" title="译者" target="_blank">译者</a></span><span class='wp_keywordlink'><a href="https://xiaoq.in/" title="肖庆" target="_blank">肖庆</a></span>，原创翻译自：<a title="使用GA跟踪内部广告系列" href="http://techpad.co.uk/content.php?sid=189" target="_blank">http://techpad.co.uk/content.php?sid=189</a>