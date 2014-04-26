---
title: GA如何与CRM系统进行对接
author: 肖庆
layout: post
permalink: /google-analytics/ga-connect-with-crm/
ratings_users:
  - 0
ratings_score:
  - 0
ratings_average:
  - 0
views:
  - 957
yourls_shorturl:
  - http://t.xiaoq.in/p
ta-thumbnail:
  - NoMediaFound
categories:
  - Google Analytics
tags:
  - CRM
  - GAPI
  - 大数据
---
关于GA与<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/crm/" title="查看CRM中的全部文章" target="_blank">CRM</a></span>/电子商务系统（如magento）对接，本文提供一个基本思路，供数据分析系统开发参考，这样可以节省不少的报表制作时间。由于本人不懂代码，因此更多功能请相关技术人员进行改进优化，比如绘制图表、数据对比、排序筛选、访客路径、下载报告等。这里主要运用到2个东西：一个是用自定义变量记录登陆用户的ID（通过与cookie或IP结合还能进行访客的历史来源回溯），而这个ID在会员系统中也是相对应的，因此主要通过这个ID进行两个系统的整合对接。这里会存在一个情况，即用户会通过多个渠道进入网站，并且时间跨度可能也会比较大，因此也需要考虑如何处理数据的一对多问题；另外一个是<a title="GAPI" href="https://code.google.com/p/gapi-google-analytics-php-interface/" target="_blank">GAPI</a>，里面提供了基本的代码，用法一般的程序员应该都可以看懂。你需要考虑的是如何呈现这些数据，需要呈现哪些数据，然后是关联到相应的会员系统中，另外也可以考虑将数据存入数据库中。

以下贴出2段基本代码，仅供参考，分别可以了解到注册会员的完整来源信息和展示广告来源信息（由于展示广告相关维度与其他维度不能同时使用，并且有最多7个维度3个指标的限制，因此才分开提供）：

代码一：

<?php  
define(&#8216;ga_email&#8217;,&#8217;g@xiaoq.in&#8217;);  
define(&#8216;ga_password&#8217;,&#8217;XXXXXXXXXXXX&#8217;);  
define(&#8216;ga\_profile\_id&#8217;,&#8217;XXXXXXXX&#8217;); require &#8216;gapi.class.php&#8217;;

$start = mktime(0,0,0,date(&#8220;m&#8221;),date(&#8220;d&#8221;)-30,date(&#8220;Y&#8221;));  
$end = mktime(0,0,0,date(&#8220;m&#8221;),date(&#8220;d&#8221;)-0,date(&#8220;Y&#8221;));  
$start_date = date(&#8220;Y-m-d&#8221;,$start);  
$end_date = date(&#8220;Y-m-d&#8221;,$end);  
$ga = new gapi(ga\_email,ga\_password,isset($\_SESSION['ga\_auth\_token'])?$\_SESSION['ga\_auth\_token']:null);  
$\_SESSION['ga\_auth_token'] = $ga->getAuthToken();  
?>  
<!DOCTYPE html PUBLIC &#8220;-//W3C//DTD XHTML 1.0 Transitional//EN&#8221; &#8220;http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd&#8221;>  
<html xmlns=&#8221;http://www.w3.org/1999/xhtml&#8221; dir=&#8221;ltr&#8221; lang=&#8221;zh-CN&#8221;>  
<head profile=&#8221;http://gmpg.org/xfn/11&#8243;>  
<title><span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/crm/" title="查看CRM中的全部文章" target="_blank">CRM</a></span>数据对接</title>  
<meta http-equiv=&#8221;Content-Type&#8221; content=&#8221;text/html; charset=utf-8&#8243; />  
</head>  
<body>

<strong>CRM数据对接</strong>  
<table><tr><th>客户ID,来源/媒介,广告系列,广告组,匹配方式,关键词,搜索词</th><th>访问</th><th>跳出率</th><th>停留时间</th></tr>  
<?php $ga->requestReportData(ga\_profile\_id,array(&#8216;customVarValue1&#8242;,&#8217;sourceMedium&#8217;,&#8217;campaign&#8217;,&#8217;adGroup&#8217;,&#8217;adMatchType&#8217;,&#8217;keyword&#8217;,&#8217;adMatchedQuery&#8217;),array(&#8216;visits&#8217;,&#8217;visitBounceRate&#8217;,&#8217;timeOnSite&#8217;)); ?>  
<?php foreach($ga->getResults() as $result):?>  
<tr>  
<td><?php echo $result; ?></td>  
<td><?php echo $result->getvisits(); ?></td>  
<td><?php echo $result->getvisitBounceRate(); ?></td>  
<td><?php echo $result->gettimeOnSite(); ?></td>  
</tr>  
<?php endforeach;?>  
</table>  
</body>  
</html>

代码二：

<?php  
define(&#8216;ga_email&#8217;,&#8217;g@xiaoq.in&#8217;);  
define(&#8216;ga_password&#8217;,&#8217;XXXXXXXXXXXX&#8217;);  
define(&#8216;ga\_profile\_id&#8217;,&#8217;XXXXXXXX&#8217;); require &#8216;gapi.class.php&#8217;;

$start = mktime(0,0,0,date(&#8220;m&#8221;),date(&#8220;d&#8221;)-30,date(&#8220;Y&#8221;));  
$end = mktime(0,0,0,date(&#8220;m&#8221;),date(&#8220;d&#8221;)-0,date(&#8220;Y&#8221;));  
$start_date = date(&#8220;Y-m-d&#8221;,$start);  
$end_date = date(&#8220;Y-m-d&#8221;,$end);  
$ga = new gapi(ga\_email,ga\_password,isset($\_SESSION['ga\_auth\_token'])?$\_SESSION['ga\_auth\_token']:null);  
$\_SESSION['ga\_auth_token'] = $ga->getAuthToken();  
?>  
<!DOCTYPE html PUBLIC &#8220;-//W3C//DTD XHTML 1.0 Transitional//EN&#8221; &#8220;http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd&#8221;>  
<html xmlns=&#8221;http://www.w3.org/1999/xhtml&#8221; dir=&#8221;ltr&#8221; lang=&#8221;zh-CN&#8221;>  
<head profile=&#8221;http://gmpg.org/xfn/11&#8243;>  
<title>CRM数据对接</title>  
<meta http-equiv=&#8221;Content-Type&#8221; content=&#8221;text/html; charset=utf-8&#8243; />  
</head>  
<body>

<strong>CRM数据对接</strong>  
<table><tr><th>客户ID,来源/媒介,广告系列,广告组,定位方式,域名,URL</th><th>访问</th><th>跳出率</th><th>停留时间</th></tr>  
<?php $ga->requestReportData(ga\_profile\_id,array(&#8216;customVarValue1&#8242;,&#8217;sourceMedium&#8217;,&#8217;campaign&#8217;,&#8217;adGroup&#8217;,&#8217;adTargetingType&#8217;,&#8217;adPlacementDomain&#8217;,&#8217;adPlacementUrl&#8217;),array(&#8216;visits&#8217;,&#8217;visitBounceRate&#8217;,&#8217;timeOnSite&#8217;)); ?>  
<?php foreach($ga->getResults() as $result):?>  
<tr>  
<td><?php echo $result; ?></td>  
<td><?php echo $result->getvisits(); ?></td>  
<td><?php echo $result->getvisitBounceRate(); ?></td>  
<td><?php echo $result->gettimeOnSite(); ?></td>  
</tr>  
<?php endforeach;?>  
</table>  
</body>  
</html>

备注：ga\_profile\_id这个是你的报告URL中p之后的数值。

<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%a4%a7%e6%95%b0%e6%8d%ae/" title="查看大数据中的全部文章" target="_blank">大数据</a></span>时代，信息化时代，请不要浪费时间做重复的体力劳动，能系统解决的一定要用系统来解决，时间就是生命，效率也是竞争力！

当然，还有另外一种方法，那就是通过utm标记来进行访客来源记录，然后在用户完成相关转化目标时将这个cookie值存入到相应的会员系统对应的记录中去。这个方法请参照《<a title="通过GA实现网站用户的识别" href="http://xiaoq.in/google-analytics/web-user-identification-by-ga/" target="_blank">通过GA实现网站用户的识别</a>》，唯一麻烦的就是你得标记URL（即便是AdWords的），否则看获取不到正确的数据（SEO、直接等来源的还是能看到），并且看到的只是最后的那一条来源记录，而不是整个的访问来源记录，要知道多渠道长周期的转化是越来越多了。