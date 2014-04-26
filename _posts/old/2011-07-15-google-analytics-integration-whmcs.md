---
title: GA电子商务跟踪：WHMCS
author: 54jack
layout: post
permalink: /google-analytics/google-analytics-integration-whmcs/
sina_t:
  - 'true'
views:
  - 1102
  - 1102
qq_t:
  - 'true'
duoshuo_thread_id:
  - 511911
yourls_shorturl:
  - http://t.xiaoq.in/48
ta-thumbnail:
  - NoMediaFound
categories:
  - Google Analytics
tags:
  - integration
  - whmcs
  - WordPress
  - 异步跟踪
  - 电子商务跟踪
---
前几天花了一百多刀买了个WHMCS，配合着<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/wordpress/" title="查看WordPress中的全部文章" target="_blank">WordPress</a></span>搭建了一个主机销售平台：<a title="译者主机" href="http://idc.yeezhe.net/" target="_blank">译者主机</a>。<span class='wp_keywordlink'><a href="http://www.yeezhe.com/" title="译者" target="_blank">译者</a></span>主机目前主要销售高速美国空间，目标潜在客户为外贸企业及独立博客。译者主机是专业的外贸主机，博客主机提供商。销售渠道主要通过SEO及口碑，不求赚钱，主要为了实践SEO和网站分析。

<img class="alignnone size-full wp-image-513" title="idc-yeezhe-net" src="http://cdn.54jack.com/images/2011/07/idc-yeezhe-net.gif" alt="" width="550" />

谷歌的标题获取方式很特别，目前我的多个网站都有这种效果了，主要看外链的影响吧。

其实整合GA到WHMCS中很简单，官方已经有<a title="GA与WHMCS整合" href="http://docs.whmcs.com/Google_Analytics_Integration" target="_blank">说明文档</a>，只要按照把两段代码（替换其中的ID为自己的）复制到相应的模板文件中即可。

下面这段代码放置到模板文件footer.tpl的</body>标签之前：

<pre style="padding-left: 30px;">&lt;script type="text/javascript"&gt;
var gaJsHost = (("https:" == document.location.protocol) ? "<a href="https://ssl/">https://ssl</a>." : "<a href="http://www/">http://www</a>.");
document.write(unescape("%3Cscript src='" + gaJsHost + "google-analytics.com/ga.js' type='text/javascript'%3E%3C/script%3E"));
{literal} try {
var pageTracker = _gat._getTracker("UA-22793934-1");
pageTracker._trackPageview();
} catch(err) {} {/literal}
&lt;/script&gt;</pre>

下面这段代码放到templates/orderforms/激活的订单模板文件夹中的complete.tpl文件中：

{php}  
$orderid = $this->get\_template\_vars(&#8216;orderid&#8217;);  
$userid = $_SESSION["uid"];

// get client data  
$result = select_query(&#8220;tblclients&#8221;,&#8221;city, state, country&#8221;,array(&#8220;id&#8221;=>$userid));  
$data = mysql\_fetch\_array($result);  
$city = $data["city"];  
$state = $data["state"];  
$country = $data["country"];  
$this->assign(&#8216;city&#8217;,$city);  
$this->assign(&#8216;state&#8217;,$state);  
$this->assign(&#8216;country&#8217;,$country);

// get package name  
$result = select_query(&#8220;tblhosting&#8221;,&#8221;packageid&#8221;,array(&#8220;orderid&#8221;=>$orderid));  
$data = mysql\_fetch\_array($result);  
$packageid = $data["packageid"];  
$result = select_query(&#8220;tblproducts&#8221;,&#8221;name, type&#8221;,array(&#8220;id&#8221;=>$packageid));  
$data = mysql\_fetch\_array($result);  
$name = $data["name"];  
$type = $data["type"];  
$this->assign(&#8216;name&#8217;,$name);  
$this->assign(&#8216;type&#8217;,$type);  
$this->assign(&#8216;packageid&#8217;,$packageid);  
{/php}

<script type=&#8221;text/javascript&#8221;>  
var gaJsHost = ((&#8220;https:&#8221; == document.location.protocol) ? &#8220;[https://ssl][1].&#8221; : &#8220;[http://www][2].&#8221;);  
document.write(unescape(&#8220;%3Cscript src=&#8217;&#8221; + gaJsHost + &#8220;google-analytics.com/ga.js&#8217; type=&#8217;text/javascript&#8217;%3E%3C/script%3E&#8221;));  
var pageTracker = \_gat.\_getTracker(&#8220;UA-22793934-1&#8243;);  
pageTracker._trackPageview();  
pageTracker._addTrans( &#8220;{$orderid}&#8221;, &#8220;&#8221;, &#8220;{$amount}&#8221;, &#8220;0&#8243;, &#8220;0&#8243;, &#8220;{$city}&#8221;, &#8220;{$state}&#8221;, &#8220;{$country}&#8221;  );  
pageTracker._addItem( &#8220;{$orderid}&#8221;, &#8220;{$packageid}&#8221;, &#8220;{$name}&#8221;, &#8220;{$type}&#8221;, &#8220;{$amount}&#8221;,&#8221;1&#8243; );  
pageTracker._trackTrans();  
</script>

这是老的代码片段了，新的异步代码片段怎么写呢？

 [1]: https://ssl/
 [2]: http://www/