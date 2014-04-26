---
title: GA自定义变量的16个有趣用法
author: 肖庆
layout: post
permalink: /google-analytics/16-interesting-ways-to-use-google-analytics-custom-variables/
sina_t:
  - 'true'
views:
  - 6936
ratings_users:
  - 1
ratings_score:
  - 5
ratings_average:
  - 5
duoshuo_thread_id:
  - 511942
yourls_shorturl:
  - http://t.xiaoq.in/3w
ta-thumbnail:
  - http://blog.xiaoq.in/thumb/cache/2012/1/583-1.jpg;http://blog.xiaoq.in/thumb/cache/2012/1/583-2.jpg;http://blog.xiaoq.in/thumb/cache/2012/1/583-3.jpg;
categories:
  - Google Analytics
tags:
  - GA
  - 自定义变量
---
<center>
  <a title="Copyright © TechPad.co.uk" href="http://techpad.co.uk/custom/images/large/4ddba1d946f41.jpg"><img src="http://techpad.co.uk/custom/images/medium/4ddba1d946f41.jpg" alt="16 interesting ways to use Google Analytics custom variables" width="426" height="228" /></a>
</center>Copyright © TechPad.co.uk

早期迹象表明<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>(<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>)用户可能将能够存储多达50个<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>。下面是填充这些数值的一些主意！

设置<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>相对于<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>中的其他事情来说稍微更复杂些，因为你需要懂一点服务器端的编程和SQL查询。

然而，这是非常有用并且值得的。<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>会给GA的配置文件中增加大量额外的数据，因为设置这些是值得的。

如果把高级细分和自定义变量配合使用，你会发现GA的作用增强上百倍。

如果你想尝试这个，查看我们的这个“<a href="http://techpad.co.uk/content.php?sid=106" target="_blank">通过PHP创建自定义变量</a>”的指南。

<a href="http://techpad.co.uk/content.php?sid=165" target="_blank">50个自定义变量位置</a>确实非常多，我想类似我这样的粉丝甚至很难填充满它们。然而，下面是着手去做的一些主意。

（注：后有博客更新：50个自定义变量只针对于商业版用户，免费GA用户仍然只能使用5个自定义变量）

**1. 跟踪用户是否登录**

当用户登录时，你的服务器端语言将创建一个变量会话来声明这点，以允许你识别用户是否已经登录。

如果你找到一个有效的变量会话，表明用户已经登录，创建一个自定义变量，该变量将会在结束时过期。

\_gaq.push(['\_setCustomVar',1,'Status','Logged-in',1]);

如果你找到一个有效的变量会话，表明用户未登录，创建一个自定义变量来标记他们为退出用户。

\_gaq.push(['\_setCustomVar',1,'Status','Logged-out',1]);

<img src="http://techpad.co.uk/custom/images/medium/4debdfd01f0e1.jpg" alt="" width="426" height="291" />

**2. 跟踪会员与非会员**

When a user successfully logs in, you know that they&#8217;re a member, so you create a custom variable which is persistent.当用户成功登录，你知道他们是会员，因此你创建一个持续性自定义变量。

\_gaq.push(['\_setCustomVar',2,'User','Member',2]);

下次他们返回时，即使他们没有登录，还是能够识别他们为会员。

对于其他人，你创建一个自定义变量表明他们是非会员。

\_gaq.push(['\_setCustomVar',2,'User','Non-Member',2]);

**3. 跟踪作者的表现**

想了解你网站的哪个作者吸引了最多的访客，与最多的用户互动并产生了最大的回报？

你可用通过创建一个包含作者名字的页面级自定义变量来实现。

\_gaq.push(['\_setCustomVar',3,'Author','Matt Clarke',3]);

**4. 跟踪网站各个部分的表现**

页面级自定义变量，正如第三条表明的是这个功能的最后一次声明，用它来归类网站各个部分表现的额外数据是非常方便的，而这单独通过标准的界面是很难跟踪的。

比如，如果你只想跟踪和细分你网站博客部分的访问（或者你网店鞋类产品部分客户的），创建一个类似这个的自定义变量。

\_gaq.push(['\_setCustomVar',4,'Section','Blog',3]);

类似的，如果你想存储正在浏览的子分类信息，只需创建一个这样的自定义变量。

\_gaq.push(['\_setCustomVar',5,'Subsection','Web analytics',3]);

<img src="http://techpad.co.uk/custom/images/medium/4debdf844cf3b.jpg" alt="" width="426" height="386" />

**5. 跟踪评论者**

参与会话的用户与保持沉默的用户有何区别，你能从中学到什么以带动评论？

一旦他们发表一个评论，创建一个下面这样的自定义变量，然后你就可以跟踪他们他们整站的活动以及未来的访问。

\_gaq.push(['\_setCustomVar',6,'Commented','Yes',1]);

你将同时需要为那些未评论的人创建一个自定义变量，其中的值需要设置为NO，这允许你比较着两个组。

\_gaq.push(['\_setCustomVar',6,'Commented','No',1]);

**6. 跟踪客户忠诚度**

If you run an e-commerce site and want to analyse the behaviour of customers depending on the number of purchases they&#8217;ve made try this one. 如果你在运营一个电子商务网站并且想基于购买次数分析客户的行为，那么尝试这个。

当这个客户达到支付页面，运行一段快速的SQL数据库查询以了解他们之前订购过多少订单。如果只是他们的首次下单，那么创建这个自定义变量。

\_gaq.push(['\_setCustomVar',7,'Customer','New customer',2]);

如果这是第二次下单，设置这个。

\_gaq.push(['\_setCustomVar',7,'Customer','Returning customer',2]);

如果他们下过两次订单或者更多，创建这个。

\_gaq.push(['\_setCustomVar',7,'Customer','Loyal customer',2]);

**7.  跟踪单独的客户**

这是一个 某些人觉得有些冒险的事情，但是它取决于你是否把客户ID，比如383328，当做可识别的个人信息（PII）。

Google坚持你不能存储可识别的个人信息（PII）到GA中，但是大多数人会说像3980933这样的客户ID，除非站长本身，其他人是无法识别为个人的，因此这并不会违反隐私条款或者带来安全隐患。

如果你想做这个，你只需要在客户登陆时把客户ID提取出来并添加到像这样的自定义变量中。

\_gaq.push(['\_setCustomVar',7,'CustomerID','5345435',2]);

**8. Track Twitter users**

Want to see how much Twitter users are worth and how they differ from other customers or users? When a user clicks a Tweet or Follow button, or is referred to your site from Twitter, create a custom variable to identify them as a Twitterer on their future visits.

\_gaq.push(['\_setCustomVar',8,'Twitter user','Yes',2]);

**9. 跟踪Twitter用户**

You could do the same thing with Facebook users, with a bit of slightly trickier JavaScript. If you can determine whether they&#8217;ve clicked your Like or Recommend button, or they&#8217;ve been referred to you via Facebook.com then add them to a custom variable.

\_gaq.push(['\_setCustomVar',9,'Facebook user','Yes',2]);

**10. 跟踪邮件订阅者**

You could track email newsletter subscribers in a couple of ways.

You could bucket them after they sign up for your newsletter by writing the custom variable after they submit the form, or if you use[utm_campaign tracking][1] you could capture this from the URL, parse it and bucket them that way.

\_gaq.push(['\_setCustomVar',10,'Newsletter subscriber','Yes',2]);

**11. 跟踪RSS订阅者**

Do your RSS subscribers respond differently? You can track them in much the same way as your email subscribers if you tag up your RSS feeds with Google Analytics&#8217; campaign tracking variables.

\_gaq.push(['\_setCustomVar',11,'RSS subscriber','Yes',2]);

**12. 跟踪促销活动表现**

Running an offer on your home page and want to see whether users buy the product as a result? You could track the performance of this with event tracking if you use _trackEvent on the onclick.

However, the offer promotion won&#8217;t be recorded as the reason for the conversion if they buy the product on a subsequent visit. However, if you set a custom variable on the onclick it definitely could.

\_gaq.push(['\_setCustomVar',12,'Summer sale promo','Yes',2]);

**13. 跟踪你帮助过的客户是否最终下单**

Most sites offer online customer service in which customers can contact them via a form on their site.

Some businesses see this as an expensive service to provide, as it can appear that helping these customers doesn&#8217;t always lead to a sale.

By setting a custom variable when they submit the form you can mark them as a customer you&#8217;ve provided customer service to via your email system, and you&#8217;ll be able to group them with the others and measure the response.

\_gaq.push(['\_setCustomVar',13,'Customer service','Emailed',2]);

**14. 跟踪投诉者是否回来  
**

Similarly, if you have a customer service form which includes a drop-down menu with various options and they mark their query as a complaint, you can add them to another custom variable.

\_gaq.push(['\_setCustomVar',14,'Complaint','Emailed',2]);

If you combine that with a [_trackEvent][2] (for ease of tracking) you&#8217;ll be able to monitor not only how many complaints you&#8217;re getting, but also whether customers who complain ever shop with you again.

**15.跟踪客户性别**

如果你让用户告诉你他们是男性还是女性（未婚或已婚），你可以使用这个信息并把性别信息包含到设置的自定义变量中。

\_gaq.push(['\_setCustomVar',15,'Gender','Male',2]);

\_gaq.push(['\_setCustomVar',15,'Gender','Female',2]);

然后，你就可以下钻了解是否男性与女性会对你的网站做出不同的反应，这可能对你的营销团队或甚至你的设计师有用处。

**16. 跟踪客户年龄**

类似地，如果你询问用户，要求他们告诉你年龄（或者大概年龄），你还可以把这个值放入到自定义变量中。

\_gaq.push(['\_setCustomVar',16,'Age','16-25',2]);

是否某个年龄的女性喜欢你的某个产品，或者博客话题？把那个数据和其他自定义变量组合，你可以或者一些真正的买家数据透视。

**<span class='wp_keywordlink'><a href="http://www.yeezhe.com/" title="译者" target="_blank">译者</a></span><span class='wp_keywordlink'><a href="http://blog.xiaoq.in/" title="肖庆" target="_blank">肖庆</a></span>，原创翻译自：<a title="GA自定义变量的16个有趣用法" href="http://techpad.co.uk/content.php?sid=166" target="_blank">http://techpad.co.uk/content.php?sid=166</a>**

 [1]: http://techpad.co.uk/content.php?sid=100
 [2]: http://techpad.co.uk/content.php?sid=102