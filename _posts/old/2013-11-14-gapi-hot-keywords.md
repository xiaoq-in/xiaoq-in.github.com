---
title: GAPI应用示例：自建热门搜索词
author: 肖庆
layout: post
permalink: /seo/gapi-hot-keywords/
yourls_shorturl:
  - http://t.xiaoq.in/85
ta-thumbnail:
  - https://xiaoq.in/cdn/2013/11/related-keywords3.png;
views:
  - 535
ratings_users:
  - 0
ratings_score:
  - 0
ratings_average:
  - 0
categories:
  - Google Analytics
  - 搜索引擎优化
tags:
  - API
  - GA
  - GAPI
  - 热门搜索词
---
对于一个数据分析工具而已，有开放的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/api/" title="查看API中的全部文章" target="_blank">API</a></span>接口是非常重要的，用户不可能把所有数据都导入到数据分析系统中去，或者出于某种安全或隐私考虑，或者是他们主要的报告分析平台可能还是要依赖于CRM系统或者自身的订单系统，那里有着丰富而详尽的数据。在某种程度上来说，数据导出功能甚至比数据导入功能更实用。这也是我对<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>目前升级数据导入功能不太看好它的主要原因。

本文以一个简单的实例来说下<span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>的数据对接方法。当然，出于技术难度的考虑，本文也只是抛砖引玉，你可能需要掌握一些基本的PHP代码编程技术，或者找到你们的程序员进行配合来完成，这里主要说下思路。

首先，请收藏这3个网页，这是进行<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/api/" title="查看API中的全部文章" target="_blank">API</a></span>对接的必备技术文档：

<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/api/" title="查看API中的全部文章" target="_blank">API</a></span>核心代码：<https://code.google.com/p/gapi-google-analytics-php-interface/>

维度指标名称大全（10月份统计下来维度143个、指标123个）：<https://developers.google.com/analytics/devguides/reporting/core/dimsmets>

开发文档：<https://developers.google.com/analytics/devguides/reporting/core/v3/reference?hl=zh-CN>

如果对SEO有些了解的童鞋应该知道，站内搜索词很多时候是转化率非常高的，对于像百姓网或者赶集网这种网站来说，他们的很大一部分流量甚至都是通过自造的搜索词着陆页面带来的，细心的话你可能会发现它们的底部都有一个叫做热门搜索的模块（一般是灰度显示，主要做给搜索引擎看的）。这种搜索词，前期可能是通过某种方式或词库的形式去建立起来，但是随着数据量的积累，他们也会得出真正用户搜索的搜索词（如搜索引擎一般，这类网站的站内搜索量是非常大的），这是一个非常宝贵的数据资源，如下图所示：

<img class="alignnone size-full wp-image-1429" alt="related keywords" src="https://xiaoq.in/cdn/2013/11/related-keywords3.png" width="1000" height="150" />

这些词它是怎么得出来的？首先肯定是搜索量大的，然后是高度相关的，并且是关键词有对应相关内容的（没有哪怕是去伪原创也要有），这是一个完美的SEO链轮。具体的效果，你基本可以随意去搜索它的相关词，大部分关键词都是在首页的前三位置这样的。它主要是基于历史数据和热门关键词的分析，以及推荐算法的优化，再依赖于高度优化的内容频道页面，强大的合作链接阵营，用户大量而高频次的信息发布。SEO的超级流量就是这么来的。

我们，当然一般是没有这么强大的算法和技术来实现这种智能化链接了。不过，通过Google Analytics这个免费工具，以及它的免费而开放的API，我们可以迈开第一步，找出自己网站的站内搜索词（或者外部搜索引擎的自然搜索词，则替换代码中的黑体分别为**keyword**和**landingPagePath**<span style="font-family: Georgia, 'Times New Roman', 'Bitstream Charter', Times, serif; font-size: 13px; line-height: 19px;">），然后再链接到对应的目标页面，具体的技术实现方法如下：</span>

<?php  
define(&#8216;ga_email&#8217;,&#8217;g@xiaoq.in&#8217;);  
define(&#8216;ga_password&#8217;,&#8217;<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>密码&#8217;);  
define(&#8216;ga\_profile\_id&#8217;,&#8217;GA视图ID&#8217;);  
require &#8216;gapi.class.php&#8217;;  
$start = mktime(0,0,0,date(&#8220;m&#8221;),date(&#8220;d&#8221;)-180,date(&#8220;Y&#8221;));  
$end = mktime(0,0,0,date(&#8220;m&#8221;),date(&#8220;d&#8221;)-2,date(&#8220;Y&#8221;));  
$start_date = date(&#8220;Y-m-d&#8221;,$start);  
$end_date = date(&#8220;Y-m-d&#8221;,$end);  
$start_index=1;  
$max_results=70;  
$ga = new gapi(ga\_email,ga\_password);  
$ga->requestReportData(ga\_profile\_id,array(&#8216;**searchKeyword**&#8216;,&#8217;**searchDestinationPage**&#8216;),array(&#8216;pageviews&#8217;,&#8217;visits&#8217;),&#8217;-visits&#8217;,$startDate,$endDate,$filter,$start\_index,$max\_results);  
?>  
<?php  
foreach($ga->getResults() as $result):  
?>  
<li><a href=&#8221;http://<?php echo $\_SERVER['SERVER\_NAME']; ?><?php echo $result->get**searchDestinationPage**() ?>&#8221;><?php echo $result->get**searchKeyword**() ?></a></li>  
<?php  
endforeach  
?>

在这里，我们还可以根据频道或分类加上相应的过滤条件，从而在正确的目录显示正确的链接，保证相关性，增加关键词密度。

**请注意，本方法仅对那些已经尝试过自创搜索词页面增加收录，并且确实有效的网站。一般是需要比较丰富的内容才能这样去做的，不然很可能产生很多空白或错误页面，从而对SEO造成不利影响。**

这只是一个简单的例子，你可以发挥想象力，实现很多强大的功能，比如基于用户访问历史记录的内容推荐，根据用户群细分展示特定的广告横幅等。这个方法也主要针对大流量网站效果才会比较好，而且需要注意的是GA的数据是存在1天左右的延迟的，并非实时数据。

API的另外一个好处就是可以与你自己的数据系统进行对接，比如上一篇文章说的通过用户ID对接订单和来源消费数据，比单纯的通过UTM标记会靠谱更多，因为UTM很容易丢失标记和产生渠道交叉覆盖的问题。具体的对接方式，程序员看完以上三个链接的相关内容，应该都懂的。