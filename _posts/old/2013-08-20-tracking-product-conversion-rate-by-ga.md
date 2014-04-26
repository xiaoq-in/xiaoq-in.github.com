---
title: 通过GA跟踪产品转化率
author: 肖庆
layout: post
permalink: /google-analytics/tracking-product-conversion-rate-by-ga/
ratings_users:
  - 1
ratings_score:
  - 5
ratings_average:
  - 5
views:
  - 1123
yourls_shorturl:
  - http://t.xiaoq.in/6
ta-thumbnail:
  - http://blog.xiaoq.in/thumb/cache/2013/8/1263-1.png;
categories:
  - Google Analytics
tags:
  - GA
  - 产品转化率
  - 电子商务跟踪
---
下图是Piwik的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%94%b5%e5%ad%90%e5%95%86%e5%8a%a1%e8%b7%9f%e8%b8%aa/" title="查看电子商务跟踪中的全部文章" target="_blank">电子商务跟踪</a></span>中的一个报告，在<a title="Magento" href="http://go.xiaoq.in/" target="_blank">Magento</a>系统中安装对应插件自动可以获取到这种数据：<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e4%ba%a7%e5%93%81%e8%bd%ac%e5%8c%96%e7%8e%87/" title="查看产品转化率中的全部文章" target="_blank">产品转化率</a></span>。这个数据在很多专业点的网站数据分析工具中都会有，不过在<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>中，我们默认只有订购（支付）成功的订单数据，无法对应到其之前的产品浏览情况。当然，如果我们的网站URL比较简单易懂（比如http://xiaoq.in/category/sku-54.html格式的），那么我们也可以通过自定义报告或者对相关维度指标进行组合来进行计算。不过，也还是比较麻烦。

<img class="alignnone size-full wp-image-1264" alt="product conversion rate tracking" src="http://blog.xiaoq.in/cdn/2013/08/product-conversion-rate-tracking.png" width="485" height="200" />

其实，我们通过使用事件跟踪即可实现类似的功能，通过在相关页面中添加相应的事件跟踪代码，把产品的sku放到事件标签中，然后查看热门事件报告中的唯一身份事件数，再除以订单数，即可算出各个产品的转化率了。同时，如果我们在事件类别中添加产品类别，在事件操作中添加页面类型，还可以看各个产品类别或页面类型的转化率数据。这对于电子商务网站来说，这个数据对于广告投放和网站运营都是机具参考价值的。

下面给出几个范例代码，不过建议也参考Magento的插件模式去弄，而国内基本就是ecshop、shopex等，这样可以方便代码部署和后期升级改版，同时也能够减少代码执行和后期的不必要沟通及麻烦，每次看到一些分析工具的部署代码就着实头痛，其实腾讯分析的Discuz分析这方面就做的不错。【注：斜体代表动态变量，如多个产品需另起一行输出】

产品类别：\_gaq.push(['\_trackEvent','*category*','category','', ,true]);

产品页面：\_gaq.push(['\_trackEvent','*category*','product','*sku-id*',*54.49*,true]);

购物车：\_gaq.push(['\_trackEvent','*category*','cart','*sku-id*',*54.49*,true]);

订单填写：\_gaq.push(['\_trackEvent','*category*','checkout','*sku-id*',*54.49*,true]);

订单确认：\_gaq.push(['\_trackEvent','*category*','confirm','*sku-id*',*54.49*,true]);

订单成功：\_gaq.push(['\_trackEvent','*category*','success','*sku-id*',*54.49*,true]);

另外，通过结合自定义变量，还可以跟踪到访客（非注册用户使用cookie，注册用户使用用户名），同时也可以对用户进行人群属性划分（根据会员系统用户信息，比如男性/女性；根据注册时间，比如30天内注册；根据下单时间，比如7天内下单，等等），从而得到更有价值的商业数据。

<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%94%b5%e5%ad%90%e5%95%86%e5%8a%a1%e8%b7%9f%e8%b8%aa/" title="查看电子商务跟踪中的全部文章" target="_blank">电子商务跟踪</a></span>的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e4%ba%a7%e5%93%81%e8%bd%ac%e5%8c%96%e7%8e%87/" title="查看产品转化率中的全部文章" target="_blank">产品转化率</a></span>跟踪，是一个值得去挖掘的数据，要知道订单的转化率一般仅为5%左右，而到达产品页面可能会有50%左右，通过对这部分数据的挖掘，可以进一步提高转化率。同时，通过对这些数据的研究和挖掘，你也可以给用户推送更具杀伤力的相关产品，实现更高匹配度的商品推荐。