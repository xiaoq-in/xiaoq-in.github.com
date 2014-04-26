---
title: 谷歌分析之电子商务跟踪，第一部分：它是如何运作的
author: 54jack
layout: post
permalink: /google-analytics/google-analytics-e-commerce-tracking-pt-1-how-it-works/
sina_t:
  - 'true'
views:
  - 1608
  - 1608
qq_t:
  - 'true'
ratings_users:
  - 1
ratings_score:
  - 5
ratings_average:
  - 5
duoshuo_thread_id:
  - 511794
yourls_shorturl:
  - http://t.xiaoq.in/4u
ta-thumbnail:
  - https://xiaoq.in/thumb/cache/2011/4/286-1.png;
categories:
  - Google Analytics
tags:
  - Analytics Talk
  - Justin Cutroni
  - 电子商务
  - 电子商务跟踪
  - 谷歌分析
  - 转化率
---
鉴于本人对<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%94%b5%e5%ad%90%e5%95%86%e5%8a%a1%e8%b7%9f%e8%b8%aa/" title="查看电子商务跟踪中的全部文章" target="_blank">电子商务跟踪</a></span>有些生疏，本周将翻译<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%94%b5%e5%ad%90%e5%95%86%e5%8a%a1%e8%b7%9f%e8%b8%aa/" title="查看电子商务跟踪中的全部文章" target="_blank">电子商务跟踪</a></span>这个系列的文章，并将扩展性的看些其他的，为了更好学习，特安装了一个<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%94%b5%e5%ad%90%e5%95%86%e5%8a%a1/" title="查看电子商务中的全部文章" target="_blank">电子商务</a></span>网站来测试，测试网站安装的一个网店系统，演示在<a title="网店演示" href="http://demo.yeezhe.net/shop/" target="_blank">这里</a>。

This post is the first in a series of e-commerce transaction tracking with <span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>. Why is e-commerce tracking important? Well, transaction data is a vital piece of information when analyzing online business performance.  
本文是<span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="谷歌分析" target="_blank">谷歌分析</a></span>之<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%94%b5%e5%ad%90%e5%95%86%e5%8a%a1/" title="查看电子商务中的全部文章" target="_blank">电子商务</a></span>交易跟踪系列的第一篇。<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%94%b5%e5%ad%90%e5%95%86%e5%8a%a1%e8%b7%9f%e8%b8%aa/" title="查看电子商务跟踪中的全部文章" target="_blank">电子商务跟踪</a></span>为何重要？因为，在分析电子商务表现时交易数据是一项非常重要的信息。  
Sure, it’s great to measure things like conversion rate, but revenue is much more tangible to many business owners. Having the e-commerce data in your web analytics application makes it easier to perform analysis. Do you need to set up e-commerce tracking? No, but it sure helps. <img src="http://xiaoq.in/wp-includes/images/smilies/icon_smile.gif" alt=":)" class="wp-smiley" />  
当然，分析像<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%bd%ac%e5%8c%96%e7%8e%87/" title="查看转化率中的全部文章" target="_blank">转化率</a></span>这样的东西是不错的，但是收入对公司老板来说会更实际些。网站分析应用中若有电子商务数据，分析时会更简单。你需要设置电子商务跟踪吗？不，但是它确实很有用。：）  
The Big Pictures  
大局  
E-commerce tracking is based on the same principal as standard pageview tracking. JavaScript code sends the data to a Google Analytic servers by requesting an invisible gif file. The big difference is that e-commerce data is sent rather than pageview data.  
电子商务跟踪基于与标准的页面浏览跟踪相同的原则。JavaScript代码通过请求不可见的gif图片文件发送数据到<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%b0%b7%e6%ad%8c%e5%88%86%e6%9e%90/" title="查看谷歌分析中的全部文章" target="_blank">谷歌分析</a></span>服务器。最大的不同在于是电子商务数据而非页面浏览数据被发送。  
But how does Google Analytics get the e-commerce data? That’s the tricky part. You, the site owner, must create some type of code that inserts the transaction data into the GA JavaScript. Sounds tricky, huh? Well, its not that bad.  
但是，<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%b0%b7%e6%ad%8c%e5%88%86%e6%9e%90/" title="查看谷歌分析中的全部文章" target="_blank">谷歌分析</a></span>是如何获得电子商务数据的呢？微妙之处正在于此。你，也就是网站所有者，必须创建某种代码把交易数据插入到<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%b0%b7%e6%ad%8c%e5%88%86%e6%9e%90/" title="查看谷歌分析中的全部文章" target="_blank">谷歌分析</a></span>的JavaScript代码中。听起来很微妙，是吧？其实，也没那么难以捉摸了。  
Step by Step: How it Works  
循序渐进：它是如何运作的  
Let’s break it down and walk through what actually happens.  
让我们把它细分下，看下到底发生了什么  
1. The visitor submits their transaction to your server.  
访问者提交交易数据到你网站服务器。  
2. Your server receives the transaction data and processes the transaction. This may include a number of steps at the server level, such as sending a confirmation email, checking a credit card number, etc.  
服务器接收交易数据并且处理交易。这可能包括服务器端的一些步骤，比如发送确认邮件，检查信用卡号码，等等。  
3. After processing the transaction the server prepares to send the receipt page back to the visitor. While preparing the receipt page your server must extract some the transaction data and insert it into the Google Analytics JavaScript. This is the code that you must create.  
在处理交易之后，服务器准备回调收据页面给访问者。在准备收据页面时，服务器必须提取一些交易数据并把它插入到谷歌分析的JavaScript代码中。这就是你必须创建的代码。  
4. The receipt page is sent to the visitor’s browser.  
收据页面被发送给访问者的浏览器。  
5. While the receipt page renders in the visitor’s browser the e-commerce data is sent to Google Analytics via special GA JavaScript.  
收据页面递交在访问者浏览器递交的同时，电子商务数据也通过谷歌分析代码的JavaScript代码传送给谷歌分析。  
Here’s a basic diagram of the process. Again, the biggest challenge during implementation is adding code to your web server that inserts the transaction data, in the appropriate format, into the receipt page. I’ll cover the setup in part 2 of this series. 这是一个基本的处理图表。再说下，实现起来最大的挑战在于添加代码到把交易数据插入到谷歌分析的网站服务器，以恰当的格式，放在收据页面。我将在这个系列的第二部分中谈这个问题。

<img src="http://www.cutroni.com/blog/wp-content/uploads/2008/01/Picture%203.png" alt="" width="480" height="473" />

What Data can be Tracked?  
什么数据可以被跟踪？  
Google Analytics collect two types of e-commerce data: transaction data and item data. Transaction data describes the overall transaction (transaction ID, total sale, tax, shipping, etc.) while item data describes the items purchased in the transaction (sku, description, category, etc.). All of this data eventually ends up in GA reports. Here’s a complete list of the data:  
谷歌分析收据两类电子商务数据：交易数据和商品数据。交易数据描述了整体的交易（交易ID，总销售额，税款，运费，等等），而商品数据则描述了在交易中购买的物品（SKU，简介，类别，等等）。所有这些数据最终反映在谷歌分析报告中，下面是完整的数据清单：  
Transaction Data  
交易数据  
• Transaction ID: your internal transaction ID [required]  
交易ID:你的内部交易ID(必需的)  
• Affiliate or store name  
联盟或者网店名称  
• Total  
总销售额  
• Tax  
税款  
• Shipping  
运费  
• City  
城市  
• State or region  
省份或地区  
• Country  
国家  
Item Data  
商品数据  
• Transaction ID: same as in transaction data [required]  
交易ID：同交易数据中的（必需的）  
• SKU  
产品SKU  
• Product name  
产品名称  
• Product category or product variation  
产品类别或者产品  
• Unit price [required]  
单价（必需的）  
• Quantity [required]  
数量（必需的）  
A few notes about the data. First, the geo-location data is no longer used by Google Analytics. The new version of GA tries to identify where the buyer is located using an IP address lookup.  
关于这些数据的一些说明。首先，地理位置数据已经不再被谷歌分析使用了。谷歌分析新版尝试通过IP地质查询确定买家的地理位置。  
Also, you should avoid using any non-alpha numeric characters in the data. Especially in the numeric fields. Do not add a currency identifier (i.e. dollar sign) in the total, tax or shipping fields. this can cause problems with the data.  
同时，你应该避免在这些数据中使用任何非字母或数字字符。特别是在数字字段中。不要在总销售额，税款或者运费字段中添加任何货币标识符（即美元符号），否则有可能使数据产生一些问题。

<span class='wp_keywordlink'><a href="http://www.yeezhe.com/" title="译者" target="_blank">译者</a></span>：<span class='wp_keywordlink'><a href="https://xiaoq.in/" title="肖庆" target="_blank">肖庆</a></span>。原文地址：<a title="Google Analytics E-Commerce Tracking Pt. 1: How It Works" href="http://cutroni.com/blog/2008/01/13/google-analytics-e-commerce-tracking-pt-1-how-it-works/" target="_blank">http://cutroni.com/blog/2008/01/13/google-analytics-e-commerce-tracking-pt-1-how-it-works/</a>

英文博客作者为 <span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/justin-cutroni/" title="查看Justin Cutroni中的全部文章" target="_blank">Justin Cutroni</a></span>，他曾写了两本谷歌分析方面十分畅销的书，分别是 O’Rielly出版的Google Analytics和Performance Marketing with Google Analytics），强烈推荐研究谷歌分析的人去看看这两本书及他的<a title="Analytics Talk" href="http://cutroni.com/blog/" target="_blank">博客</a>。