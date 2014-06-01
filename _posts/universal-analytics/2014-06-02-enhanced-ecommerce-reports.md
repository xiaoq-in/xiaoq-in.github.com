---
layout: post
title: 增强版电商报告造福零售电商
permalink: /universal-analytics/enhanced-ecommerce-reports/
category : Universal Analytics
tags : [Enhanced Ecommerce Reports, Universal Analytics, 增强型电商报告]
---
{% include JB/setup %}

如果你还没有听过，Google[发布了一套新的Universal Analytics电商报告](http://analytics.blogspot.com/2014/05/google-analytics-summit-2014-whats-next.html)功能，旨在让用户对电商购物行为和运营形成更深层次的理解。Blast公司有机会与一个大型零售电商合作，在Google的保密测试版本发布期间尝试这些新功能。

鉴于所有这些电商功能和报告的广度，我觉得最好还是写几篇博客文章，每篇涵盖这些新电商报告和功能的不同视角。在这个Google Analytics增强版电商系列（共四篇）的第一篇，我将着重讲述电商概览报告。保持关注，因为我将在之后的三篇分别讲述：购物行为，购物车行为，以及产品效果。

电商概览报告（四篇连载之一）
-------------

![beta-ecomm-13.png](http://cdn.xiaoq.in/images/beta-ecomm-13.png)


像其他概览报告一样，Google Analytics提供了相当数量的概览层级信息，一目了然。

电商概览报告打开后的默认图表是在一个图中同时显示收入和转化率。棒极了！这个图的左边坐标轴用美元符号，右边坐标轴用百分比。

在图表下方，是一个当前报告时段内的规划得更好的电商KPI数据（即关键性财务数据）。我喜欢收入被放在左边并且显示在第一位，右边是其他关键性表现数据。同时，之前的唯一身份购买次数和购买的产品数量，现在改成了平均数量（每笔交易购买的产品数量）。

![beta-ecomm-2.png](http://cdn.xiaoq.in/images/beta-ecomm-2.png)

为了对比，下面是老版本的电商KPI格式。

![beta-ecomm-3.png](http://cdn.xiaoq.in/images/beta-ecomm-3.png)

打住，这是什么？

在关键性财务数据下面，现在有一个全新的概览区域，产品经理和市场经理应该会很感兴趣。


![beta-ecomm-14.png](http://cdn.xiaoq.in/images/beta-ecomm-14.png)


让我们来细看一下。首先，我马上看到了一个“广告系列”的标签，基于我的点击偏好，这是一个链接，指向“流量获取”的“广告系列”报告，并显示每个系列的表现。


![beta-ecomm-51.png](http://cdn.xiaoq.in/images/beta-ecomm-51.png)


报告的层次是ABC（流量获取-用户行为-目标转化）模式。注意，在“转化”区域，有一个下拉项，你可以快速选择一个特定的电商目标并进行切换查看。

http://cdn.xiaoq.in/images/ beta-ecomm-7.png

我偏离主题了，但是出发点是好的。现在，回到电商概览报告，我得尝试点击下“内部促销”，哦，对了，它也是一个链接。我点击了这个链接，并且现在看到了一个新的报告，这个报告显示了内部CTA（Call To Action，行为号召）的表现，包括：浏览次数、点击次数、点击率。我突然觉得电商分析的术语与AdWords非常类似—我喜欢（作者在这里玩了个双关语，impression除了表示觉得，也是AdWords中展示次数的意思）。
![beta-ecomm-9.png](http://cdn.xiaoq.in/images/beta-ecomm-9.png)

接下来是“订单促销代码”。又是一个链接，这次我点击之后被带到了一个列表，其中显示了所有被使用过的促销代码。请注意，所有未使用过促销代码的销售都被显示为(not set)。我超喜欢。


![beta-ecomm-8.png](http://cdn.xiaoq.in/images/beta-ecomm-8.png)


新区域的最右边链接是“联属机构”。链接指向一个超棒的电商报告，显示的是按联署机构划分的销售。我想我不再需要建立一个自定义报告来查看分联署机构的表现了，因为这个超有用的报告只需一个点击即可查看。我被说服了。

![beta-ecomm-10.png](http://cdn.xiaoq.in/images/beta-ecomm-10.png)

最后，这个新的电商概览报告现在显示了热门收入来源（如原来的电商概览报告）。这又有一些需要注意的变化，新版的核心关注点是收入而非购买的产品数量，所有默认排序都是收入的降序，并且热门收入来源的细分维度从“产品、SKU、类别、来源/媒介”改成了“产品、类别、品牌”。

![beta-ecomm-11.png](http://cdn.xiaoq.in/images/beta-ecomm-11.png)

接下来是什么？
-------------

我非常享受这个新改变，因为Google进行了巨大的投入和清晰的承诺来支持零售电商的需求。在我的下篇文章中，我将深入这个新的购物分析部分，其中包括了涵盖购物行为和购物车行为的报告。老实来说，这些稳健的报告需要深入挖掘的文章。作为一个预告，下面是我下篇文章将要讲述的购物分析报告的截屏。


![beta-ecomm-15.png](http://cdn.xiaoq.in/images/beta-ecomm-15.png)

Google承诺过会加强电商报告，此前有人对此表示怀疑，现在，你将看到切实增加的新报告数据，并可以基于这些报告来处理和优化你的电商销售漏斗。

增强型电商设置
-------------

请注意，为了在Google Analytics中获取这些有价值的、新的电商数据，你需要做以下事情：

1. 评估你的网站流程来确定购物漏斗中的关键性元素（比如，产品类别浏览，产品详情浏览，添加到购物车操作，结算，交易）。
2. 部署Universal Analytics。

3. 使用ec.js插件来标记网站。

4. 对每个“视图”开启增强型电商。

另外，采取下列操作后，你还可以在Google Analytics中深入挖掘并获取更多价值：

*  导入产品ID元数据。
*  导入退款数据。

如果你需要帮助部署这些变更后的Google Analytics跟踪代码，以及/或者想了解这些新的电商报告，请联系我们。

请关注GA增强版电商系列的第二部分：购物行为分析。

【原创翻译自[Enhanced Ecommerce Reports Empower Ecommerce Retailers](http://www.blastam.com/blog/index.php/2014/05/google-analytics-enhanced-ecommerce-reports/)，转载请注明出处，您的支持是我翻译/写作的动力】
