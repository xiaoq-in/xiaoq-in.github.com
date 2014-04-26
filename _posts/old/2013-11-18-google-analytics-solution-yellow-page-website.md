---
title: 数据分析解决方案之：分类网站
author: 肖庆
layout: post
permalink: /analytics/google-analytics-solution-yellow-page-website/
yourls_shorturl:
  - http://t.xiaoq.in/86
ta-thumbnail:
  - http://blog.xiaoq.in/cdn/2013/11/分类网站.gif;
views:
  - 398
ratings_users:
  - 0
ratings_score:
  - 0
ratings_average:
  - 0
categories:
  - 数据分析
tags:
  - GA
  - GAIQ
  - GTM
  - UA
  - 分类网站
  - 数据分析方案
  - 数据分析解决方案
  - 百姓网
---
今天不经意间发现国内<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/gaiq/" title="查看GAIQ中的全部文章" target="_blank">GAIQ</a></span>认证通过人数最多的公司是某<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%88%86%e7%b1%bb%e7%bd%91%e7%ab%99/" title="查看分类网站中的全部文章" target="_blank">分类网站</a></span>（总共112其占了19个），感到很惊讶。早上看资讯时候也刚好看到国外一家<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span> Partner一篇关于他们帮助黄页网站（Yellow Pages NZ）提供数据分析服务的简单说明，Yellow Pages NZ（以下简称YP）之前用的是**Adobe SiteCatalyst Analytics**，经过专家的迁移和部署，虽然用的是Google Analytics，但他们却能够获得更多的有价值数据（<a title="Yellow Pages Group New Zealand Upgrades to Universal Analytics" href="http://www.blastam.com/blog/index.php/2013/05/universal-analytics-yellowpages/" target="_blank">详情点击</a>）。

<img class="alignnone size-full wp-image-1436" alt="分类网站" src="http://blog.xiaoq.in/cdn/2013/11/分类网站.gif" width="290" height="170" />

&nbsp;

下面，就这个案例简单编译一下。

我们看到YP使用了Google Tag Manager并且采用<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>和<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ua/" title="查看UA中的全部文章" target="_blank">UA</a></span>版本并行的方案。这是一个值得推荐的方式，因为<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ua/" title="查看UA中的全部文章" target="_blank">UA</a></span>在目前来说还无法进行再营销投放，内容实验等，而<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ua/" title="查看UA中的全部文章" target="_blank">UA</a></span>的自定义维度和指标，简短的cookie值和后端的数据控制，也非常强大而便利。同时使用<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>和UA版本并不会产生冲突。

以下是一个搜索页面的跟踪代码，前半部分是通用的，定义的跟踪ID，域名，会员ID。

**var dataLayer = new Object();**  
**dataLayer.gaID = &#8216;UA-5159414-1&#8242;;**  
**dataLayer.UAgaID = &#8216;UA-35952421-1&#8242;;**  
**dataLayer.hostname = &#8216;.yellow.co.nz&#8217;;**  
**dataLayer.loginId = &#8217;0&#8242;;**  
dataLayer.pageType = &#8216;SearchResultsPage&#8217;;

dataLayer.searchType = &#8216;Category Search&#8217;;  
dataLayer.searchTermInterpretation = &#8216;Restaurants&#8217;;  
dataLayer.searchTermActual = &#8216;restaurants&#8217;;  
dataLayer.searchOutcome = &#8216;Successful&#8217;;  
dataLayer.searchLocationInterpretation = &#8216;Auckland City&#8217;;  
dataLayer.searchLocationActual = &#8216;auckland-city&#8217;;  
dataLayer.refinements = [];  
dataLayer.pageNumber = &#8217;1&#8242;;  
dataLayer.listings = {&#8216;sideRunnerAds&#8217; : [], &#8216;platinumAds&#8217; : []};  
dataLayer.listings.resultsAds = ['103565976\_1403\_gold\_01', '101138587\_1403\_gold\_02', '101711337\_1403\_gold\_03', '101322153\_1403\_gold\_04', '103889633\_1403\_gold\_05', '103440246\_1403\_gold\_06', '101016618\_1403\_gold\_07', '103838212\_1403\_gold\_08', '103118370\_1403\_gold\_09', '101024436\_1403\_gold\_10', '103903907\_1403\_gold\_11', '103112073\_1403\_gold\_12', '101711335\_1403\_gold\_13', '102579733\_1403\_gold\_14', '101322155\_1403\_gold\_15', '102436580\_1403\_gold\_16', '103564219\_1403\_gold\_17', '101322175\_1403\_gold\_18', '103809732\_1403\_gold\_19', '101322165\_1403\_gold\_20'];  
dataLayer.categoryName = &#8216;Restaurants&#8217;;  
dataLayer.categoryID = &#8217;1403&#8242;;

分别定义了：

页面类型

搜索类型

搜索词转换（应该是统一了首字母大写，进行了一定程度的数据聚合）

用户实际搜索词

搜索是否有结果

搜索城市（转换后，同上）

搜索城市（空格用-代替）

搜索优化词

当前所处第几页

侧栏广告

搜索结果广告（类似P4P结果，区分结果类型，如什么类型的广告还是普通的列表，按照排序列举）

分类名称

分类ID

——————————

这里，他们主要用到了自定义维度和事件跟踪，使用自定义维度 （而不是自定义变量）的好处是它是作为第一维度可以直接查看其数据或与其他数据进行次级维度交叉，同时也在跨平台跟踪方面支持也更好些。作为一般的搜索结果页面，我们会想到的是使用搜索类别和搜索词定义，但是对于搜索结果是否有数据，用户的翻页行为，这些都是标准配置无法得知的。

&nbsp;

另外客户希望了解每个搜索结果的点击情况，这个时候我们如果我们单纯地使用目标跟踪，可能会出现问题。因为用户在一次访问中，只能记录同一个类型的一次转化。比如用户打开了2个商家页面，然后分别点击了联系商家（完成了转化），在<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>的标准报告中，只能识别为一个转化，而其实对于这种网站来说，应该算是两个转化。因此，使用了事件跟踪，并且给每个事件加入了独特的标记（其实就是动态加入商家ID到事件操作中），最终在事件报告中，我们可以看到每个事件的独立触发数，同时也能看到总共的事件触发数，从而实现了客户需求。代码如下：

*   Event Category: Listing Interaction
*   Event Action: {Unique ID of listing}
*   Event Label: {Interaction Type}

当然，这里它这里是通过<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/gtm/" title="查看GTM中的全部文章" target="_blank">GTM</a></span>的宏定义来完成的。

我们再来看看<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%99%be%e5%a7%93%e7%bd%91/" title="查看百姓网中的全部文章" target="_blank">百姓网</a></span>的代码部署：

\_gaq.push(['\_setCustomVar', 1, 'Category', tracker.category, 3]);  
\_gaq.push(['\_setCustomVar', 2, 'City', tracker.city , 3]);

类别定义和城市定义，没啥说的。下面是一些js代码，做一些自动化监测：

ga : function (name, action, label, value) {  
_taq.push(['ga', name, action, label, value]);  
},  
setCategory : function (category) {this.category = category},  
setCity : function (city) {this.city = city},  
setCityEnglishName : function (city\_name) {this.city\_name = city_name},  
setTrackId : function (trackid) {this.trackid = trackid},  
setAdId : function (adid) {this.adid = adid},  
setVisitorId : function (visitorid) {this.visitorid = visitorid},  
setUserId : function (userid) {this.userid = userid}  
};

核心代码大抵如此，其实也无外乎是定义那些值，只是它这里通过js去拼接数据，可以一定程度减少在服务器端的查询。当然，它还做了些其他方面的跟踪，比如加载速度，广告位监测。同时，<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%99%be%e5%a7%93%e7%bd%91/" title="查看百姓网中的全部文章" target="_blank">百姓网</a></span>应该也做了一个内部的数据分析系统：gary.baixing.com，数据通过URL参数的形式（类似GA的gif文件的数据存储方式）发送到服务器，然后再处理。

综上所述，对于<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%88%86%e7%b1%bb%e7%bd%91%e7%ab%99/" title="查看分类网站中的全部文章" target="_blank">分类网站</a></span>来说，其实最主要的数据跟踪点如下：

城市、频道、页面类型、子类别、访客、会员。

其中搜索会比较关注，同时搜索后的行为也是网站运营人员比较关心的数据。

对这类网站来说，分类聚合应该是用的比较多的一个分析方法。可能某个人员运营某几个频道，他只关心这些数据，如果希望做更深入了解也会去挖掘频道内部的细节数据。而作为上层来说，可能希望关注到总体的数据，比如每个城市或每个频道的总体运营数据，做成柱状图或趋势曲线图之类的进行查看。技术人员和运维人员来说则主要关注搜索结果优化和加载速度等方面。

当然，如果是全球运营的公司，旗下有多个分站点，可能也会用到多个ID进行跟踪，一个总账号，多个子账号。

当然，如果真像上面说的那样，各频道按部门划分很明显，也可以给每个频道或多个频道（按人员分配）指定一个ID，这种方法也能够减少数据抽样率和提高数据更新速率，并且适合多个广告账户推广的投放方式。当然，过滤器也是一个办法了，只是数据量确实会比较庞大，免费版GA的一千万hit/月/账户限制恐怕很快就超过了（年费十五万美金的付费版是十亿）。

<span style="color: #ff6600;">本文仅供学习参考，本人与上文提到的公司无任何关联或关系。</span>