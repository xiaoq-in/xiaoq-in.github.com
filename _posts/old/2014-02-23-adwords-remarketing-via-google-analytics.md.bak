---
title: 如何用Google Analytics投放AdWords再营销广告
author: 肖庆
layout: post
permalink: /google-analytics/adwords-remarketing-via-google-analytics/
ratings_users:
  - 1
ratings_score:
  - 5
ratings_average:
  - 5
views:
  - 303
ta-thumbnail:
  - https://xiaoq.in/cdn/2014/02/adwords-remarketing-types.gif;https://xiaoq.in/cdn/2014/02/ga-remarketing.gif;https://xiaoq.in/cdn/2014/02/ga-remarketing-7day-active-non-vip.gif;https://xiaoq.in/cdn/2014/02/geographic-targeting.gif;https://xiaoq.in/cdn/2014/02/youku-cpm.gif;https://xiaoq.in/cdn/2014/02/first-visit-time.gif;
categories:
  - Google AdWords
  - Google Analytics
tags:
  - 再营销
---
如果你的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%86%8d%e8%90%a5%e9%94%80/" title="查看再营销中的全部文章" target="_blank">再营销</a></span>用户列表非常庞大，尝试过AdWords后台的各种细分方式，但还是抱怨效果并不太理想，那么本文提供<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%86%8d%e8%90%a5%e9%94%80/" title="查看再营销中的全部文章" target="_blank">再营销</a></span>的另外一种细分思路：用户细分，主要通过<span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%86%8d%e8%90%a5%e9%94%80/" title="查看再营销中的全部文章" target="_blank">再营销</a></span>功能来实现。

*注：*

1.  *由于Universal Analytics暂时无法支持GA的再营销，因为请暂时不要升级GA的版本，或者采取GA+UA并行的方式，从而充分利用两者的各种优势，并且保证后续全面升级的时候可以很快地切换，UA版本是大势所趋，但限于有些功能在新的版本暂时还未实现，暂时只能这样了。*
2.  请更新您的 Google Analytics（分析）跟踪代码以支持展示广告，具体方法参照<a title="更新您的 Google Analytics（分析）跟踪代码以支持展示广告" href="https://support.google.com/analytics/answer/2444872" target="_blank">帮助中心</a>。

我们知道，在AdWords后台中，目前主要有如下几种细分方式，其中组合方式和成员资格有效期又可以延伸出无限种细分。

<img class="alignnone  wp-image-1600" alt="adwords remarketing types" src="https://xiaoq.in/cdn/2014/02/adwords-remarketing-types.gif" width="600" />

而在Google Analytics中，我们则有以下的细分选项，其中最后一项：利用细分功能自行创建再营销类型，相当于AdWords中的自定义组合，但是更强大。

<img alt="ga remarketing" src="https://xiaoq.in/cdn/2014/02/ga-remarketing.gif" width="600" />

我们看到，AdWords的筛选规则，除了cookie机制，主要是基于URL。因此事件跟踪之类的，它是没有办法的。可以说AdWords后台能够实现的 再营销，Google Analytics也都可以，至少我是没有发现无法实现的，如有，欢迎留言。

首先，毫无疑问的是这些细分方式已经非常强大，能够满足大多数的营销需求。然而，还是存在一些不足，如果你意识到了这种不足，为了弥补这些不足，我们可以借助Google Analytics来进行再营销，具体的不足和可以采取的措施主要如下：

1.  AdWords并非是真正面向用户的，它只是基于有效期内单个浏览器的cookie。因此，我们可以使用GA中的自定义变量方式标记实际的用户（会员），并以此来创建再营销列表。当我们设置好了自定义变量（下图假设自定义变量2的值是会员ID）之后，我们就可以根据用户属性类进行用户分类，最基本的比如：会员-非会员。<img class="alignnone  wp-image-1602" alt="ga remarketing 7day active non-vip" src="https://xiaoq.in/cdn/2014/02/ga-remarketing-7day-active-non-vip.gif" width="600" />更细化的比如：男性-女性；高价值会员-低价值会员等。另外，我们可以设置一个有效期，比如只定位那些七天内访问过网站的非会员，另外再结合用户访问页数或停留时间（比如唯一身份浏览量按用户大于或等于2），筛选出最有可能成为网站会员的用户，进行更频繁和针对性的广告投放。
2.   AdWords只能定位那些**固定时间范围**内访问过网站的用户，并不能定位**某个时间周期**内访问过网站的用户。固定时间范围意味着我必须定期地新建这个列表来保持用户的新鲜度，而某个时间周期则意味着我可以定位那些对网站最感兴趣的活跃用户。首先，“具体日期之间的网页访问者”这个功能已经是基于一种初级层次的队列分析（Cohort Analysis），如果你在某个时间进行了特定的广告促销，那么使用这种定位方式是再合适不过了。但是，你可能并不想天天给那些不可能或基本不可能成为实际客户的用户浪费无谓的广告展示或者广告点击，从而降低广告点击率、广告质量、从而增加广告的成本吧。
3.  基于Google的内部共享数据，按照受众特征进行细分。这个在AdWords后台我们也可以进行定位方式组合的形式来实现（需要单独设置很多项，需要单独建立广告组），而在GA中我们是可以放在一个广告组中进行投放的（设置的时候尽量避免用户重叠，或者使用梯度出价），看到数据列表的预估值，并且一般我们也是通过GA的数据来进行不同受众特征的效果评估（查看标准报告中”受众群体”中的“受众特征”报告），用GA会简单一些。可设置的选项如下：<img class="alignnone  wp-image-1603" alt="geographic targeting" src="https://xiaoq.in/cdn/2014/02/geographic-targeting.gif" width="600" />
4.  序列化细分用户或访问，更多的细分维度，自由组合。比如我们通过来源媒介报告发现，曾经点击过优酷CPM广告的用户，如果访问过2个以上页面，并且是最近30天内访问的用户，表现最佳，那么我们可以筛选出这部分人群进行定位。一方面加大优酷的广告投放，另外一方面再做好收尾工作，把用户尽量保留下来。来源/媒介筛选，在AdWords中我们也可以使用“引荐来源网址”规则实现，但是无法组合其他网站表现维度，这种灵活的组合方式也是本文的中心所在。<img class="alignnone  wp-image-1604" alt="youku-cpm" src="https://xiaoq.in/cdn/2014/02/youku-cpm.gif" width="600" />
5.  第一次访问的时间。这种定位方式，对于全新的网站，或者主要以吸收新用户为主的网站来说比较有价值（比如新游戏开服，新渠道测试），因为GA中记录的数据其实是在统计周期内第一次访问的时间。比如，我们可以定位那些第一次访问的时间在2月份的用户，这部分用户由于都是全新导入过来的流量，我们可以再给他们来一次高度密集的营销活动，做最后的收尾，再评定最终的效果（比如我们的活动有效期截止到本月底）。<img class="alignnone  wp-image-1605" alt="first visit time" src="https://xiaoq.in/cdn/2014/02/first-visit-time.gif" width="600" />

&nbsp;

上面介绍的只是通过Google Analytics进行再营销广告投放的几种简单的应用，做再营销广告的核心理念是对受众特征的准确把握，而这种把握也绝不是只根据过往的经验来一概而论，我们需要做更多角度的综合分析，才能制定适合自己的的营销方式。

当然，本文并不是说AdWords的再营销可以完全抛弃了，很多人可能并没有充分挖掘其中的潜力，对于业务复杂程度并不高的中小企业来说，AdWords界面的那些细分组合已经完全够用，并且简单易用。如果只是个别功能非得在GA中才能实现，我们也可以同时使用两个界面的再营销。并且，通过<a title="如何向再营销代码添加自定义参数" href="https://support.google.com/adwords/answer/3111920#standard_parameters" target="_blank">向再营销代码添加自定义参数</a>，我们也可以在AdWords后台类似上述的部分细分。只不过，如果同时要做一些高级的数据分析定制，用传统的代码部署方式，可能就是两套代码了，会稍微繁复一些。使用GTM，部署起来可能会复杂点，但维护起来会简单很多。

如果我们的营销需求比较复杂，并且有足够的人手，希望尽量简单代码部署，尽量在一个平台实现前后端数据的贯通，并且具有更灵活的定位和组合方式，那么单独使用GA来设置可能会简单高效点。而且，我们也可以参照再营销的自定义参数，转换为GA来实现，因为这些不光是对我们投放广告有用，对于网站分析来说，同样有很大的价值。

具体选择哪种方式看自己的需求和实现难易程度吧，适合自己的才是最好的。最后，再附上一个<a title="利用 Google Analytics™ 实现再营销" href="http://static.googleusercontent.com/media/www.google.cn/zh-CN/cn/intl/zh-CN_ALL/analytics/features/remarketing_GA_factsheet.pdf" target="_blank">官方介绍文档</a>。