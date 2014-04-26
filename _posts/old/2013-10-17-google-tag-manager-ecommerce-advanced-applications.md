---
title: Google Tag Manager在电子商务网站中的高级应用
author: 肖庆
layout: post
permalink: /google-analytics/google-tag-manager-ecommerce-advanced-applications/
yourls_shorturl:
  - http://t.xiaoq.in/7y
views:
  - 1352
ratings_users:
  - 0
ratings_score:
  - 0
ratings_average:
  - 0
ta-thumbnail:
  - http://blog.xiaoq.in/thumb/cache/2013/10/1350-1.png;
categories:
  - Google Analytics
tags:
  - Google AdWords
  - Google Analytics
  - Google Tag Manager
  - 会员跟踪
  - 再营销
  - 动态再营销
  - 电子商务跟踪
  - 转化跟踪
  - 页面类型跟踪
---
<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/google-tag-manager/" title="查看Google Tag Manager中的全部文章" target="_blank">Google Tag Manager</a></span>是一个非常强大的代码管理工具，对于刚刚接触并使用它的人来说，可能会认为它充其量就只是一个代码容器，把很多段代码扔进去然后前端显示很漂亮，就觉得这个工具很赞了。不过，它的作用绝不仅仅停留在这么简单，它在帮助你高效便捷管理代码的同时，还能够实现更多的扩展功能，帮助提供更深入的数据透视。

<img class="alignnone  wp-image-1365" alt="clientId-ABC" src="http://blog.xiaoq.in/cdn/2013/10/clientId-ABC.png" width="650" />

<p style="text-align: center;">
  不同客户ID的ABC（获取-行为-转化）数据示例
</p>

&nbsp;

就“<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/google-tag-manager/" title="查看Google Tag Manager中的全部文章" target="_blank">Google Tag Manager</a></span>在电子商务网站中的高级应用”这个话题思考和探索了几天，本想直接丢一大堆的代码在这里，不过本博客的受众应该大多数还是跟我一样的技术菜鸟，怕大家反感或者看不懂，反而偏离了我的初衷，让大家反而觉得太高深不敢用了。

这里就实例来说主要针对外贸电商，因为Google Shopping在国内貌似不能使用，因此无法使用<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%8a%a8%e6%80%81%e5%86%8d%e8%90%a5%e9%94%80/" title="查看动态再营销中的全部文章" target="_blank">动态再营销</a></span>，其实也可以扩展到国内（看到京东、中粮、凡客那些都有<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%8a%a8%e6%80%81%e5%86%8d%e8%90%a5%e9%94%80/" title="查看动态再营销中的全部文章" target="_blank">动态再营销</a></span>广告，不过好像是通过DSP来实现的），电子商务网站分析的数据维度一般更多，但并不排除其他类型的网站有类似的需求，因此也可以扩展到各个行业领域。

最初使用GTM的时候，主要是由于代码太多了，然后技术大哥也太忙了影响效率。于是最初的实际使用就是：将十几段<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%86%8d%e8%90%a5%e9%94%80/" title="查看再营销中的全部文章" target="_blank">再营销</a></span>代码和转化代码扔进去了（游戏运营公司，主要是为了充分利用自身不同游戏类似的用户群进行交叉营销，这种思路大家也可以借鉴下）。

这种最简单的使用方式，相信大家都已经了解了。没接触过的话，看下帮助中心，跟着步骤来就是了。基本半天也能够研究透。 现在，我们来说说电子商务网站在代码部署中会遇到的一些代码，以及在GTM中的基本设置方法：

1.  <span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>（这里以Universal Analytics为例）基本的流量跟踪代码。新建标签，填入对应的跟踪ID，设置所有页面触发的规则，保存。后面会讲到设置自定义维度，以及其他的一些高级设置。
2.  <span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-adwords/" title="Google Adwords" target="_blank">Google Adwords</a></span><span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%bd%ac%e5%8c%96%e8%b7%9f%e8%b8%aa/" title="查看转化跟踪中的全部文章" target="_blank">转化跟踪</a></span>代码。新建标签，中填入转化ID和转化标签，转化价值先暂且随便填一个，设置触发规则（一般是支付成功页面的URL或者注册成功的URL等），保存。如何读取动态转化价值，下面会详谈。
3.  <span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/google-adwords/" title="查看Google AdWords中的全部文章" target="_blank">Google AdWords</a></span><span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%86%8d%e8%90%a5%e9%94%80/" title="查看再营销中的全部文章" target="_blank">再营销</a></span>代码（这里特指<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%8a%a8%e6%80%81%e5%86%8d%e8%90%a5%e9%94%80/" title="查看动态再营销中的全部文章" target="_blank">动态再营销</a></span>）。新建标签，填入转化ID和转化标签，选择使用Data Layer，先暂且勾选默认的not set（后面会详谈如何读取动态值），保存。
4.  事件跟踪代码。目前GTM中已经可以自动识别事件跟踪，不过为了区分事件，还需要对网站的标签进行一些规范化操作，下面详谈。
5.  其他跟踪代码，如果GTM已经有集成，根据提示设置即可；如果没有，选择HTML方式添加。需要注意的是如果代码使用了document.write，是不能放到里面的，只能是再额外单独加到网站了。

以上这些操作，应该不难。 对于电子商务网站来说，基础的流量分析是远不够的，我们希望获取到各个产品类别的以及单个产品的转化率，不同类型页面的转化效果，用户的留存率和忠诚度，回访率，注册用户与非注册用户的行为对比，更多的会员信息透视（如年龄、性别等），订单数据，等等。当然，我们也不要进入数据漩涡，一味地为了获取数据而获取。在确定网站目标的前提下，收集数据只是数据分析的一个基本步骤，如果你只是为了报告而收集数据，不去作分析，一切也都是白搭。 言归正传，对于产品转化率和会员的跟踪，在此前我们一般就是通过自定义变量来实现，而用户的跟踪基本也只是通过Cookie去对接。现在，我们完全可以转换思路，将这些数据直接存入我们的自定义维度（或指标）中。而用户的身份识别，我们也不必那么麻烦去解析cookie值了，UA中原生就有个唯一身份识别码：clientId。读取方式也很简单，如下：

<pre>ga(function(tracker) {
  var clientId = tracker.get('clientId');
});</pre>

下面，开始进入代码（本人并非技术出身，如有错误还请指正并见谅）：~ 注：以下代码都是通用配置方式，部分代码可能需要加入页面判断是否生成。这里的代码都要放在GTM代码的前面，否则需要做额外设置，不然获取不到数据。 这是动态再营销的代码，需要配置相应变量，其中还可以加入更多的自定义字段，详细参考：<a href="https://support.google.com/adwords/answer/3103357#custom_parameters" target="_blank">https://support.google.com/adwords/answer/3103357#custom_parameters </a>

<pre>&lt;script type="text/javascript"&gt;
var google_tag_params = {
ecomm_prodid: 'REPLACE_WITH_VALUE', 
ecomm_pagetype: 'REPLACE_WITH_VALUE',
ecomm_totalvalue: 'REPLACE_WITH_VALUE'
};
&lt;/script&gt;</pre>

这是定义<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%94%b5%e5%ad%90%e5%95%86%e5%8a%a1%e8%b7%9f%e8%b8%aa/" title="查看电子商务跟踪中的全部文章" target="_blank">电子商务跟踪</a></span>的，在订单号生成的页面生成，详细可以参考：<a href="https://support.google.com/tagmanager/answer/3002596?hl=en" target="_blank">https://support.google.com/tagmanager/answer/3002596?hl=en</a>

<pre>&lt;script&gt;
dataLayer = [{
    'transactionId': '1234',
    'transactionAffiliation': 'Acme Clothing',
    'transactionTotal': '11.99',
    'transactionTax': '1.29',
    'transactionShipping': '5',
    'transactionProducts': [{
        'sku': 'DD44',
        'name': 'T-Shirt',
        'category': 'Apparel',
        'price': '11.99',
        'quantity': '1'
    },{
        'sku': 'AA1243544',
        'name': 'Socks',
        'category': 'Apparel',
        'price': '9.99',
        'quantity': '2'
    }]
}];
&lt;/script&gt;</pre>

这是页面分析和会员分析的定制代码，这里仅是例子，具体需要什么维度的数据可根据业务需要设定：

<pre>ga(function(tracker) {
var clientId = tracker.get('clientId');
});
"pageCat" : "Checkout Pages",
"pageCat2" : "",
"productCat" : "Mobile Phone",
"productCat2" : "xiaomi",
"visitorLevel" : "diamond",
"visitorState" : "Logged In",
"visitorFirstPurchDate" : "20131017",
"visitorLTV" : "1000.54"
"pageVersion" : "A001"</pre>

通过定义这些变量值，我们再将其值透过GTM的自定义维度设置，放入UA中。这样，我们需要的更深度数据就都有了。

事件跟踪的自动识别，这里主要是指对外部链接、按钮、表单的识别，不过你需要对所有需要跟踪的这些东西定义好规范的值，一般是div或span的class和id。具体可以参考这篇文章：<http://cutroni.com/blog/2013/10/07/auto-event-tracking-with-google-tag-manager/>

以上的代码并不完整，并且显得有些零散，不过可以根据需要进行整合和简化，比如动态再营销中的一些变量，也可以直接放到UA中的自定义变量。

这些数据获取之后，我们再可以建立自定义报告，将日常业务关注的重点维度指标进行组合，这将做成一个非常完美的日报/周报/月报。

拼接数据这种痛苦而枯燥无味的活，绝对不是数据分析师主要该干的，抽出更多时间去了解业务，解析数据报告吧。

这篇文章看起来还是有点乱，不过基本思路流程就是这样的，其中涉及的具体技术细节，资深些的技术人员应该可以理解，根据程序的复杂程度和技术水平，大概半天的时间应该就可以完成代码变量的设置。

另外，如果你想实现跨平台跟踪，也可以在APP或移动站点进行类似的设置，主要通过设备ID和会员ID进行关联。有兴趣的童鞋可以参考GTM的开发文档：<a href="https://developers.google.com/tag-manager/devguide" target="_blank">https://developers.google.com/tag-manager/devguide</a>

看起来似乎有点复杂，其实不难而且也都是值得的，最终还是提高效率的。 这也是目前Google主推的一种代码部署方式，跟GA、AdWords以及第三方代码的结合度也很高。在国外有很多类似Google Tag Manager的商业付费工具，一些知名的商业分析工具厂商也收购了Tag Manager公司，或者开发了自己类似的工具。

这种方式特别适用于符合以下情况的公司：

1.  <span style="font-family: Consolas, Monaco, monospace; font-size: 12px; line-height: 18px;">拥有或管理多个网站的公司：一次设置之后，都是可以进行简单的复制黏贴的。（如果业务类型类似并且网站程序相同）</span>
2.  业务系统比较庞大的公司：内部流程很复杂，改个代码可能都需要一个月时间，不如一次性搞定，并且这种方式的扩展性也很强，新增或修改代码片段也不用麻烦技术人员。
3.  使用多套分析系统的公司：即便使用其他分析工具也可以很好的进行对接。一般的分析工具收集的数据基本都是这些，一般来的都是分别直接植入不同的跟踪代码中，造成变量数据（一般都是要再重复读取数据库）的多次重复引用，浪费服务器资源并且也可能减缓加载速度。另外，如果要对接内部的CRM系统，离线电话系统等，也是轻而易举的。
4.  希望深入分析数据的公司：通过这种深度数据维度的扩展，我们可以做更深度的细分、分组、筛选过滤、对比、预测、队列分析、归因分析、A/B测试等等，都不是问题。
5.  受限于GA默认的自定义变量数量限制，并且不愿花钱买付费版本（年费近10万，功能对比来说并不明显，主要是数据量和技术支持）。
6.  希望进行跨平台（跨设备）广告效果追踪，并实现更深层次的离线追踪。

本文抛砖引玉，希望对你有用。本想基于一个开源电子商务系统（如Magento）提供相关的代码实例和实验数据，不过工程量确实太大且技术水平有限，暂且就这样吧。