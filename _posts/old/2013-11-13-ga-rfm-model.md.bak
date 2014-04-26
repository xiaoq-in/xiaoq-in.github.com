---
title: 如何基于GA建立RFM模型
author: 肖庆
layout: post
permalink: /google-analytics/ga-rfm-model/
yourls_shorturl:
  - http://t.xiaoq.in/84
ta-thumbnail:
  - https://xiaoq.in/cdn/2013/11/customer-segmentation.png;https://xiaoq.in/cdn/2013/11/customer-device4.png;https://xiaoq.in/cdn/2013/11/customer-browser.png;https://xiaoq.in/cdn/2013/11/聚类分析后产生的_8个客户类别.jpg;
views:
  - 531
ratings_users:
  - 2
ratings_score:
  - 6
ratings_average:
  - 3
categories:
  - Google Analytics
tags:
  - GA
  - RFM
  - RFM模型
  - 用户跟踪
  - 电子商务跟踪
  - 自定义变量
  - 跨屏幕跟踪
  - 跨设备跟踪
---
细分是一种常见的数据分析方法，如果有了解过CRM系统，那么你应该知道<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/rfm/" title="查看RFM中的全部文章" target="_blank">RFM</a></span>这种模型，在数据分析来说算是一种细分方式。不管你有没有听说过这个名词，你可能都在不经意地使用这种方法，比如你会关注客单价、客户总购买金额、用户忠诚度、用户购买频次等数据。

在<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/rfm/" title="查看RFM中的全部文章" target="_blank">RFM</a></span>模式中，R(Recency)表示客户最近一次购买的时间有多远，F(Frequency)表示客户在最近一段时间内购买的次数，M (Monetary)表示客户在最近一段时间内购买的金额。一般的分析型CRM着重在对于客户贡献度的分析，<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/rfm/" title="查看RFM中的全部文章" target="_blank">RFM</a></span>则强调以客户的行为来区分客户。（引用自智库百科）

在<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>现有的高级细分中，我们基本上是可以按照这种模型来进行细分的，如下图：

<img class="alignnone  wp-image-1420" alt="customer segmentation" src="https://xiaoq.in/cdn/2013/11/customer-segmentation.png" width="600" />

不过，尽管<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>升级后是按访客层级进行统计的，但它还是基于cookie来的，基本还是不能解决如下所述的比较复杂的问题。并且出来的数据也只是概览数据，无法再深入进行挖掘。另外，购买时间这个记录也是没有的（我们只能分日去查看，但是没有这个具体指标），需要我们再通过标记去记录。

这是一个非常纠结的数字营销时代。从刚刚过去的双十一，回想一下你的抢购体验，体会就更加深刻了。大部分人（特别是女性）可能会这样：提前一周在家里的笔记本电脑随便逛逛，看中相中的先收藏或者加入购物车，静候五折；第二天上班，地铁或公交上再瞧瞧；上班了午休前可能再逛逛，上班时候可能也偷偷逛逛（一般使用多个浏览器）；双十一前夕收到邮件或短信，里面有优惠码。这个过程其实非常复杂，概括起来就是：多浏览器、多设备、周期长、线下线上结合，浏览器与APP结合。

一般的电商网站跟踪，浏览器或者APP的跟踪都是单独进行的，很少会进行整合，这样出来的数据可能就是：实际新用户其实没那么多，用户其实比你看到的更忠诚、用户其实比你看到的更纠结，品牌词和直接来源吞没了大多数的辅助转化功劳。

在建立<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/rfm%e6%a8%a1%e5%9e%8b/" title="查看RFM模型中的全部文章" target="_blank">RFM模型</a></span>之前，我们最主要的是要收集到相关数据，用户识别和自定义标记是主要的思路，具体方法之前的文章也有介绍，可以去看下如何实现。

如果你之前看到我的相关博客，进行了<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>等相关设置，那么你通过一些简单的数据筛选和汇总，可能会发现（以下数据仅供参考，根据公司推广方式和行业可能并不相同）：1)使用多个设备的用户大概可能会占据1/10左右；2)使用多个浏览器的用户大概可能也会占据10%左右；3）同时使用多个设备且多个浏览器的用户可能占据2%左右（3个及以上维度的交叉组合建议使用<span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span> Query Explorer或Excellent Analytics插件或自行开发API进行获取，在此不示例）。另外需要注意的是，<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>的浏览器和设备跟踪数据其实并不准确的，市场上的浏览器版本太多，设备也太多，更新又快，然后又有各种“伪装”（360是最好的例子），造成有些归类是有问题的，不过我们知道下，主要看趋势就好。

<img class="alignnone size-full wp-image-1414" alt="customer device" src="https://xiaoq.in/cdn/2013/11/customer-device4.png" width="500" height="250" /><img class="alignnone size-full wp-image-1415" alt="customer browser" src="https://xiaoq.in/cdn/2013/11/customer-browser.png" width="500" height="285" />

以上说的是用户识别时候需要注意的，当我们把用户的整个浏览轨迹贯通之后，精准性提高，接下来的数据获取和分析也相对简单很多了。另外需要注意的是，用户可能在第一次来到网站并不会进行注册，因此如果我们能够通过cookie值进行对接的话，那么数据的精准性也会提高很多。

上面还说到线上和线下的交互问题，这个主要通过对接CRM系统来进行操作，给线下的会员生成一个唯一ID，然后通过这个ID进行对接，这个独立于会员ID，有点类似于网站用户的cookie id，因为线下会员和线上会员可能采取的不同会员系统和编号，并且也并不都是自动就线下注册为线上或线上注册为线下的。对于线下活动的来源渠道对接，一般就是使用独特优惠码或生成专属URL的方式来进行跟踪（UTM标记然后转化为短网址）了。

<img class="alignnone size-full wp-image-1416" alt="聚类分析后产生的_8个客户类别" src="https://xiaoq.in/cdn/2013/11/聚类分析后产生的_8个客户类别.jpg" width="586" height="398" />

在通过一系列的技术手段获取到相关数据之后，我们最终的主要目的就是对用户进行分类，大体可以分为以上8个类型（将这几种类型放到象限图或对比视图中，对比效果会更明显）。细分之后，我们就可以更深入地透视数据发现问题，制定和执行相应的营销策略（如再营销细分、EDM发送、重点客户跟进、有效推广渠道挖掘与强化、页面个性化定制等），进行更相关的、更精准的广告推送。

当然，我们还可以结合其他维度去进行组合细分，比如我们除了可以看购买频次和购买次数之外，还可以看访问频次、访问次数等。

这里，免费工具的话，推荐使用GTM的和UA的自定义维度和指标进行跟踪数据收集，会方便很多。数据分析建立起一套分析模型和数据模板会比较麻烦，但是好了之后就轻松很多了，也能更好地符合业务需求。

从标准报告到自定义报告，你看的更全面；从标准维度指标到自定义维度指标，你看的更透彻。两者结合，全面而透彻的数据分析算是迈出了坚定而有力的第一步。