---
title: 谷歌分析：电子商务跟踪之5大自定义变量
author: 54jack
layout: post
permalink: /google-analytics/5-google-analytics-custom-variables-for-ecommerce/
sina_t:
  - 'true'
views:
  - 2697
  - 2697
qq_t:
  - 'true'
duoshuo_thread_id:
  - 511898
ratings_users:
  - 1
ratings_score:
  - 5
ratings_average:
  - 5
yourls_shorturl:
  - http://t.xiaoq.in/72
ta-thumbnail:
  - http://blog.xiaoq.in/thumb/cache/2011/6/491-1.jpg;http://blog.xiaoq.in/thumb/cache/2011/6/491-2.jpg;http://blog.xiaoq.in/thumb/cache/2011/6/491-3.png;
categories:
  - Google Analytics
tags:
  - 自定义变量
  - 谷歌分析
  - 购买历史
  - 跟踪付款方式
  - 跟踪优惠码和促销码
  - 跟踪回头客
  - 跟踪运输方式
---
我相信每个公司都能使用<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="谷歌分析" target="_blank">谷歌分析</a></span>的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>。特别是电子商务公司。<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>插入对于高级细分至关重要的新的数据维度。作为分析师，我们需要做高级细分来了解用户行为。而电子商务网站有一些特定的独特行为，是无法通过<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%b0%b7%e6%ad%8c%e5%88%86%e6%9e%90/" title="查看谷歌分析中的全部文章" target="_blank">谷歌分析</a></span>的基本配置来跟踪的。

I believe that every business can use <span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span> custom variables. Especially ecommerce businesses. Custom variables inject new data dimensions that are crucial for segmentation. As analysts we need to do segmentation to understand user behavior. And ecommerce sites have certain unique behaviors that are not tracked with a basic Google Analytics implementation.

For those that have not used custom variables before you can get read [Mastering Custom Variables][1] for overview.

对于那些之前没有用过<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>的人，你可以阅读我的上篇文章“<a title="掌握谷歌分析自定义变量" href="http://g.xiaoq.in/cn/google-analytics/mastering-google-analytics-custom-variables/" target="_blank">掌握谷歌分析自定义变量</a>”来整体了解下。

Now on to the custom variables!

现在，谈自定义变量！

**<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%b7%9f%e8%b8%aa%e4%bc%98%e6%83%a0%e7%a0%81%e5%92%8c%e4%bf%83%e9%94%80%e7%a0%81/" title="查看跟踪优惠码和促销码中的全部文章" target="_blank">跟踪优惠码和促销码</a></span>**

**Tracking Coupon Codes and Promotional Codes**  
<img title="Tracking Coupon Codes with Google Analytics" src="http://cutroni.com/blog/wp-content/uploads/coupon-300x245.jpg" alt="Tracking Coupon Codes with Google Analytics" width="300" height="245" />  
我认为这是自定义变量一个十分重要的用途。如果你卖一些东西，你可能会开展很多促销活动。而你需要跟踪这些促销活动来了解它们的表现。有些促销活动可以通过广告系列跟踪来实现。我看到很多人使用utm_content参数来区分市场计划中的不同促销活动，比如邮件促销。但是，自定义变量也可以达到同样的目的。

I think this is a pretty obvious use of custom variables. If you sell something you probably run various promotions. And you need to track these promotions to see how they perform. Some promotions can be tracked using campaign tracking. I’ve seen lots of people use the utm_content parameter to identify the promotion in a marketing campaign, like an email. But a custom variable works just as well.

说到策略，随着时间推移，这些广告系列参数将会如何扩张。你想把所有的促销代码都聚合到一个自定义变量里吗？你可以添加类似下面的代码：

When coming up with a strategy think about how you might scale this as time goes on. Do you want all of your promotional codes aggregated together under one variable? You could do something like this:

`_gaq.push(['_setCustomVar',1,'PromoCode','<PROMO CODE ID>',3]);`

或者，你可能会想使用不同的自定义变量来跟踪不同的促销活动组，如季节性促销。举个例子，如果你在节假日有很多的促销活动，你可能想创建一个叫做“HolidayPromos”的自定义变量，然后赋予每个促销代码一个独特的名字，类似下面这样：

Or you could get fancy and use different custom variables to bucket groups of promotions, like seasonal promotions. For example, if you lots of promotions during the holiday season you might want to create a custom variable named HolidayPromos and then a unique name for each of the codes, something like this:

`_gaq.push(['_setCustomVar',1,'HolidayPromo','Free2DayShip',3]);<br />
_gaq.push(['_setCustomVar',1,'HolidayPromo','FreeWrapping',3]);<br />
_gaq.push(['_setCustomVar',1,'HolidayPromo','10perOff',3]);`

上述代码需要你添加到着陆页面。记住，上述代码中的位置或索引值可能根据你的实际情况会不同。取决于你如何使用自定义变量。

The above code would need to appear on your receipt page. And remember, the slot, or index, in the code above may be different for you. It all depends on your use of custom variables.

你可能想问我为什么在此使用页面级自定义变量？记住，<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%b0%b7%e6%ad%8c%e5%88%86%e6%9e%90/" title="查看谷歌分析中的全部文章" target="_blank">谷歌分析</a></span>会把一个页面级自定义变量归到一个会话中。因此，尽管自定义变量只会开始作用于着陆页面，但是数据将应用到整个访问。

You might be wondering why I decided to go with a page level custom variable here. Remember, Google Analytics will sessionize a page level custom variable. So even though the custom var will only fire on the receipt page the data will be applied to the entire visit.

**<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%b7%9f%e8%b8%aa%e4%bb%98%e6%ac%be%e6%96%b9%e5%bc%8f/" title="查看跟踪付款方式中的全部文章" target="_blank">跟踪付款方式</a></span>**

**Tracking Payment Method**

记住，我们研究访问者的行为来了解其对业务的影响。其中的一个行为就是用户如何付款。使用信用卡付款和使用PayPal付款的访问者会不同吗？是否会前者的平均花费高于后者，或者相反？除非你捕捉到付款方式然后查看如平均订单价值和转化率等维度，否则无从得知。

Remember, we study visitor behavior to understand the impact on business. One of these behaviors is how people pay for a purchase. Is there a difference between a visitor who pays with a credit card vs one who pays with PayPal? Does one spend more, on average, than the other? You’ll never know unless you capture payment type and review metrics like average order value and conversion rate.

为了捕捉付款方式，请使用页面级自定义变量。最终的GA代码将会如下面这样：

To capture payment type use a page level custom variable. The resulting GA code will look something like this:

`_gaq.push(['_setCustomVar',2, 'PaymentType','<NAME OF PAYMENT>',3]);`

别忘记把其中的`<PAYMENT TYPE>替换为客户的付款方式。`

Don’t forget to replace `<PAYMENT TYPE>` with the customer’s payment method.

**<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%b7%9f%e8%b8%aa%e8%bf%90%e8%be%93%e6%96%b9%e5%bc%8f/" title="查看跟踪运输方式中的全部文章" target="_blank">跟踪运输方式</a></span>**

**Tracking Shipping Method**

<img title="Why not tracking shipping method with Google Analytics?" src="http://cutroni.com/blog/wp-content/uploads/shipping.jpg" alt="Why not tracking shipping method with Google Analytics?" width="300" height="300" />  
与付款方式一样，了解用户对不同产品选择何种运输方式也是很有趣的一件事情。为什么？或许买特定产品的人会选择特定的运输方式。如果是这样，或许你可以使用这些信息建立一个新的促销。这里面不会有内幕吗？当然有！但是，除非你有数据并且做了一些分析，否则无从得知。

Like payment method, it’s interesting to see what shipping method people choose with various products. Why? Perhaps people who buy certain products choose certain types of shipping. If so, maybe you can build a new promotion using this information. Could there be no insights here? ABSOLUTELY! But you’ll never know unless you have some data and do a bit of analysis.

`_gaq.push(['_setCustomVar',3,'CustType','Repeat',1]);`

**<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%b7%9f%e8%b8%aa%e5%9b%9e%e5%a4%b4%e5%ae%a2/" title="查看跟踪回头客中的全部文章" target="_blank">跟踪回头客</a></span>**

**Tracking Repeat Customers**

我记得很久以前看过Eric Peterson的书Web Analytics Demystified。这是关于网站分析最早的一本书之一，同时还非常具有可操作性。Eric谈到过电子商务良好表现的关键性苗头之一便是，当然也是如此，回头客。

I remember reading Eric Peterson’s book [Web Analytics Demystified][2] a looong time ago. Besides being one of the first books on analytics it was exceedingly actionable. One of the ecommerce key performance indicators Eric talked about, and rightfully so, was the repeat-buyers.

回头客的行为与首次购买客户是不同的。这群客户因为他们对于你们产品和服务较了解，通常花更少的时间来购买。通常，让这些人购买会花较少的钱。因此，了解他们对哪些市场活动作出反应以及他们如何使用你们的网站，是一个不错的主意。

The behavior of repeat customers is different than first time customers. This segment of customers usually takes less time to purchase due to a knowledge of your products and services. Normally it costs you less money to get these people to convert. So it’s a good idea to understand what marketing they respond to and how they use your website.

为了在谷歌分析中<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%b7%9f%e8%b8%aa%e5%9b%9e%e5%a4%b4%e5%ae%a2/" title="查看跟踪回头客中的全部文章" target="_blank">跟踪回头客</a></span>，你必须使用访问级自定义变量。记住访问级自定义变量通过cookie保留到访问者的电脑。何时设置自定义变量最为关键。

To track repeat customers in Google Analytics you must use a visitor scope custom variable. Remember a visitor scoped custom variable persists on the visitor’s computer as a cookie. The trick is when you set the custom variable.

大多数人认为你可以在交易发生时设置自定义变量，如下面这样：

Most people think you can set the custom variable when the transaction happens, like this:

`_gaq.push(['_setCustomVar',4,'CustType','Repeat',1]);`

但事实是，这并不奏效。当你设置一个访问级自定义变量是，该值会应用到**当前**访问以及之后的所有访问。因此，你需要等到<span style="color: #888888;">第二次</span>购买之后设置自定义变量。这样会就好了。

But in reality this will not work. When you set a visit level custom variable the value gets applied to the **CURRENT** visit and all future visits. So you need to wait until the **SECOND** purchase before setting the above custom variable. Then it should work just fine.

我应该注意到这是应用于高级细分中的一个很棒的自定义变量。事实上，使用在高级细分中也是不错的，但是细分回头客特别有用。

I should note that this is an AWESOME custom variable to use in an advanced segment. Actually, they’re all great to use in Advanced segments, but segmenting repeat buyers is especially useful

<img title="Creating a customer segment in Google Analytics" src="http://cutroni.com/blog/wp-content/uploads/Screen-shot-2011-06-12-at-8.36.11-PM.png" alt="Creating a customer segment in Google Analytics" width="732" height="460" />

**<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%b4%ad%e4%b9%b0%e5%8e%86%e5%8f%b2/" title="查看购买历史中的全部文章" target="_blank">购买历史</a></span>**

**Purchase History**

到此事情变得有些复杂了。跟踪<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%b4%ad%e4%b9%b0%e5%8e%86%e5%8f%b2/" title="查看购买历史中的全部文章" target="_blank">购买历史</a></span>记录需要在服务器端的一些配置，意味着你或者你的计算机部门同事需要创建一些代码，基于他们在过去购买数量来分类客户。与其跟踪每次购买，我更偏爱于跟踪不同批量的购买，如下面这样：

This is where things get a little more complicated. Tracking things like purchase history requires a bit of configuration on the server side, meaning you or your nerds need to create some code to categorize customers based on the number of purchases they’ve made in the past. Rather than track every single purchase I prefer to bucket the purchases, like this:

*   1 to 3 purchases
*   4 to 6 purchases
*   7 + purchases

你需要在服务器端设置逻辑来查看客户的购买记录，然后设置相应的自定义变量。GA的JavaScript代码会像下面这样：

You need to have the logic on the server to review the custom’er purchase history and set the custom variable accordingly. The GA JavaScript will look something like this:

`_gaq.push(['_setCustomVar',5,'PurchHistory','1-3',1]);`

现在，你可能会想在之前的自定义变量中有些重复，嗯。回头客的自定义变量更通用些，会给你一个关于新客户和回头客的快速概括。购买历史记录的自定义变量用来挖掘和分析更深层的客户行为。

Now you’re probably thinking that there is some duplication with the previous custom variable, and you’re right. The repeat customer variable is a bit more generic and gives you a quick view of new and returning customers. The purchase history variable is geared towards deeper analysis of customer behavior.

那么，你已经为电子商务网站设置了5个自定义变量。这并非一个排外的清单，但是我认为这些会帮助任何电子商务为基础的公司做更好的细分和分析。

So there you have it, five custom variables for ecommerce websites. This is by no means an exhaustive list, but I think these can help any commerce based business to better segmentation and analysis.

你在你的电子商务网站使用自定义变量吗？如果在的话我希望知道你们是如何使用的！

Are you using custom variables on your ecommerce website? If so I’d love to hear how!

<span class='wp_keywordlink'><a href="http://www.yeezhe.com/" title="译者" target="_blank">译者</a></span><span class='wp_keywordlink'><a href="http://blog.xiaoq.in/" title="肖庆" target="_blank">肖庆</a></span>原创翻译自Jutin的博客，原文地址：<a title="You are here: Home / Analysis / 5 Google Analytics Custom Variables for Ecommerce5 Google Analytics Custom Variables for Ecommerce" href="http://cutroni.com/blog/2011/06/14/5-google-analytics-custom-variables-for-ecommerce/" target="_blank">http://cutroni.com/blog/2011/06/14/5-google-analytics-custom-variables-for-ecommerce/</a>

 [1]: http://cutroni.com/blog/2011/05/18/mastering-google-analytics-custom-variables/
 [2]: http://www.amazon.com/Web-Analytics-Demystified-Marketers-Understanding/dp/0974358428