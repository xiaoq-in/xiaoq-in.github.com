---
title: Google Analytics高级应用之Magento
author: 肖庆
layout: post
permalink: /google-analytics/advanced-google-analytics-application-magento/
ratings_users:
  - 4
ratings_score:
  - 16
ratings_average:
  - 4
views:
  - 2212
yourls_shorturl:
  - http://t.xiaoq.in/n
ta-thumbnail:
  - https://xiaoq.in/thumb/cache/2012/10/936-1.jpg;
categories:
  - Google Analytics
tags:
  - GA
  - Magento
  - 事件跟踪
  - 外贸B2C
  - 电子商务跟踪
  - 自定义变量
  - 虚拟页面跟踪
  - 谷歌分析
---
<a title="Magento演示" href="http://go.xiaoq.in/" target="_blank">Magento</a>可以说是<a title="外贸主机" href="http://client.xiaoq.in/" target="_blank">外贸建站</a>中最流行的一款免费开源程序，流行度相当于<a title="WordPress演示" href="http://mars.xiaoq.in/" target="_blank">WordPress</a>在<a title="独立博客主机" href="http://client.xiaoq.in/" target="_blank">独立博客</a>建站中的应用。<span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>同样是大多数<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%a4%96%e8%b4%b8b2c/" title="查看外贸B2C中的全部文章" target="_blank">外贸B2C</a></span>网站的数据分析首选，本文主要讲述Google Analytics在<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/magento/" title="查看Magento中的全部文章" target="_blank">Magento</a></span>系统中的高级应用。

<img class="alignnone size-full wp-image-937" title="magento-google-analytics" src="http://cdn.xiaoq.in/2012/10/magento-google-analytics.jpg" alt="" width="600" height="200" />

对于大多数<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>的初级用户而言，使用<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>貌似很简单，复制GA后台的跟踪代码到程序模版中就算完事了，然后就看流量，跳出率等基本维度数据，做的好点的可能会添加一个订单成功的页面目标，然后就算完事了。

但是，电子商务是一个真刀实枪的战场，你应该做更多，挖掘更多有价值的数据，了解网站和用户，改善网站体验和提升体验，从而进一步减少浪费（转化成本），提升转化率和转化价值。那么，本文将按照这个思路进行讲解：获得数据——了解数据——改进数据。

我们需要获得怎样的数据？怎么获得这些数据？基础的数据获取当然非常简单了，但是这是远远不够的；要获得这些额外的数据，其实也并不困难。主要使用以下几个高级跟踪技术：

<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%94%b5%e5%ad%90%e5%95%86%e5%8a%a1%e8%b7%9f%e8%b8%aa/" title="查看电子商务跟踪中的全部文章" target="_blank">电子商务跟踪</a></span>：

毫无疑问，这是任何电子商务网站必须首要关注的，你需要了解每日的订单趋势及其来源渠道，产品销量数据。当然，你可以通过网站的后台系统获得一些数据，但是关键是如何对接这些数据，将用户行为和产品销售进行对接，就得依靠<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%94%b5%e5%ad%90%e5%95%86%e5%8a%a1%e8%b7%9f%e8%b8%aa/" title="查看电子商务跟踪中的全部文章" target="_blank">电子商务跟踪</a></span>了。（注：本人非程序员出身，因此代码具体实现方式请找相关程序员，本文仅阐述方法，对于一般程序员来说，实现起来并不困难，大多数只是动态值的替换而已）

\_gaq.push(['\_trackPageview']);  
// e-commerce tracking begin  
\_gaq.push(['\_addTrans', 'test1234', // order ID - required  
'test1234', // affiliation or store name  
'12.34', // total - required  
'12.34', // tax  
'12.34', // shipping  
'test1234', // city  
'test1234', // state or province  
'AU' // country  
]);  
// add item might be called for every item in the shopping cart  
// where your ecommerce engine loops through each item in the cart and  
// prints out _addItem for each  
\_gaq.push(['\_addItem', 'test1234', // order ID - required  
'test1234', // SKU/code - required  
'test1234', // product name  
'test1234', // category or variation  
'12.34', // unit price - required  
'12' // quantity - required  
]);  
\_gaq.push(['\_addItem', 'test1234', // order ID - required  
'test1234', // SKU/code - required  
'test1234', // product name  
'test1234', // category or variation  
'12.34', // unit price - required  
'12' // quantity - required  
]);  
\_gaq.push(['\_trackTrans']); //submits transaction to the Analytics servers  
// e-commerce tracking end  
(function () {

此段代码插入到GA代码的相应位置，并且放到订单跳转去支付的前一个页面，放到跳转前的好处是数据最全，缺点是可能部分订单最终并未支付。当然你也可以安装到支付成功的返回页面，这种方式优点是可以跟踪所有成功的订单，确定是可能部分用户不正常返回。最佳解决方案是2个位置均放置代码，使用2个GA的ID，然后分别查看数据。

转化渠道跟踪：

<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/magento/" title="查看Magento中的全部文章" target="_blank">Magento</a></span>系统一般来说主要有2种支付模式，分页支付或者单页支付（onepage），前者比较好办，直接添加相应的URL到目标渠道即可，后者的话，就需要使用<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%99%9a%e6%8b%9f%e9%a1%b5%e9%9d%a2%e8%b7%9f%e8%b8%aa/" title="查看虚拟页面跟踪中的全部文章" target="_blank">虚拟页面跟踪</a></span>了。分别在各个按钮的位置添加<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%99%9a%e6%8b%9f%e9%a1%b5%e9%9d%a2%e8%b7%9f%e8%b8%aa/" title="查看虚拟页面跟踪中的全部文章" target="_blank">虚拟页面跟踪</a></span>，使用onclick事件并定位容易理解的虚拟URL，然后将这个URL同理添加到URL页面形式的目标渠道中即可。主要代码如下：

onclick = &#8220;shipping.save();\_gaq.push(['\_trackPageview', '/order/shipping_info']);&#8221;  
onclick = &#8220;shippingMethod.save();\_gaq.push(['\_trackPageview', '/order/shipping_method']);&#8221;  
onclick = &#8220;payment.save();\_gaq.push(['\_trackPageview', '/order/payment']);&#8221;  
onclick = &#8220;review.save();\_gaq.push(['\_trackPageview', '/order/review']);&#8221;

搜索页面路径转化，大多数外贸网站会依靠SEO，因此可能会对页面进行伪静态处理，出现一个问题就是搜索结果页面没有?cat=category&q=keyword这种字符参数，因此，你就需要对这些页面的URL进行转化，将伪静态的URL转化成可被GA搜索配置中识别的参数形式。

代码范例如下：

\_gaq.push(['\_trackPageview', '?cat=category&q=keyword']);

错误页面这个经常被忽略，其实通过GA的虚拟页面跟踪，可以很方便的了解哪些页面出错了。代码如下：

\_gaq.push(['\_trackPageview', '/404.html?page=' + document.location.pathname + document.location.search + '&from=' + document.referrer]);

结果在内容页中搜索404.html，后面的值分别为出错路径和引荐来源，可导出使用Excel的分列功能分析数据。

虚拟页面的另外一个应用就是外链的跟踪，比如链接到facebook，twitter等sns社区的链接，paypal认证及其他认证的的外部链接，等等。

说完虚拟页面跟踪，就不得不说<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>了，大多数情况下，建议使用<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>，尤其是站内的一些点击事件，因为虚拟页面跟踪的一个很大弊端是会产生更多的页面浏览，会影响跳出率及停留时间等基础数据。而是用<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>的话，基于今年出的一个事件跟踪赋值，它可以对跳出率不产生影响。事件跟踪的另外一个好处是它有更多的参数，因此对于一些稍微复杂的应用，事件跟踪会更好用一些。比如下面说到的导航菜单点击事件跟踪，购物车按钮点击跟踪，快速支付点击跟踪。

导航菜单的点击事件跟踪，在很多网站都可以看到应用，比如小米网，铁血网（百度开放统计还拿它做案例，其实人家用的是GA），敦煌网卖家平台。代码范例如下（事件跟踪须特别注意大小写及空值的处理，转化价值的空值直接使用空格，不得使用&#8217; &#8216;，另外事件价值必须为整数数字，不得使用小数点及单位）：

onclick = &#8220;\_gaq.push(['\_trackEvent','menu','category','sub', ,true]);

购物车按钮的跟踪，购物车也是一种转化，虽然它离转化还有一些距离，但是极具参考价值。代码范例如下：

onclick = &#8220;productAddToCartForm.submit(this);\_gaq.push(['\_trackEvent', 'add to cart','category', 'sku-id','1234',true]);

快捷支付，大多数外贸网站都会使用PayPal进行收款，但是普通的付款方式有时候有些麻烦，各种表单填写，因此采用快捷支付在某种程度上会提升整体的转化率，就如大多数国内电商均采用支付宝或新浪微博或qq号等账号直接登录一个道理。注：这里使用onmousedown而不适用onclick主要是为了避免跟踪代码来不及加载而统计不到部分数据，当然你也可以通过进行延时处理来实现。

onmousedown = &#8220;\_gaq.push(['\_trackEvent','paypal','category','sku-id',1234,true]);

<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>：

<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>主要作用是对会员行为进行分析，如果广泛而言，你可以分为2大类，会员和非会员。当然，为了更细致了解相关用户行为，你可以对每个会员进行跟踪，将各个会员的ID添加到访客级<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>中。主要代码（会员记录会员号，非会员记录cookie值）：

\_gaq.push(['\_setCustomVar', 1, 'vip/non-vip', 'id/cookie', 1]);

自定义变量不光可以用来记录会员信息，还可以跟踪语言，货币，国际或城市（读取会员地址信息或根据IP进行转化），浏览的产品及其对应类别，等等，根据具体应用范围，可使用访客、访问、页面等三级别的自定义变量。

以上就是主要的几个高级应用了，希望对<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%a4%96%e8%b4%b8b2c/" title="查看外贸B2C中的全部文章" target="_blank">外贸B2C</a></span>的童鞋们有帮助，通过使用GA的这些高级功能，是不是又发现了一片新天地了？你可以做更具针对性的营销策略，更科学有效的成本控制，更合理的产品及页面调整。

当然，以上只是告诉你如何获取数据，关于如何使用这些数据，如何利用这些数据给你带来真正的商业价值，请听下回分解。