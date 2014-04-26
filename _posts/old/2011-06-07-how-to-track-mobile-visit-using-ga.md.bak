---
title: 如何跟踪手机访问流量
author: 54jack
layout: post
permalink: /google-analytics/how-to-track-mobile-visit-using-ga/
sina_t:
  - 'true'
views:
  - 1361
  - 1361
qq_t:
  - 'true'
duoshuo_thread_id:
  - 511896
yourls_shorturl:
  - http://t.xiaoq.in/4c
ta-thumbnail:
  - NoMediaFound
categories:
  - Google Analytics
tags:
  - GA
  - PHP
  - WordPress
  - 手机访问
  - 移动设备
  - 谷歌分析
---
前些天参加了谷歌大客户的一个交流会，其中一点就说到<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e6%89%8b%e6%9c%ba%e8%ae%bf%e9%97%ae/" title="查看手机访问中的全部文章" target="_blank">手机访问</a></span>的流量和成交量在日益增加，这种趋势尤其表现在一些发达国家或地区，一般在节假日，晚上等非工作时间。那么，如何跟踪<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e6%89%8b%e6%9c%ba%e8%ae%bf%e9%97%ae/" title="查看手机访问中的全部文章" target="_blank">手机访问</a></span>的流量就是本文要探讨的一个问题了。本文以<span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>安装在<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/wordpress/" title="查看WordPress中的全部文章" target="_blank">WordPress</a></span>平台为例，其他程序应该大体类似。

下面这张图其实已经很清楚地解释了如何安装<span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="谷歌分析" target="_blank">谷歌分析</a></span>代码到手机网站了。其最终效果就是调用一张透明图片（如：<http://wap.54jack.com/ga.php?utmac=MO-22601383-1&utmn=1590299286&utmr=-&utmp=%2Findex-wap2.php&guid=ON>），其中含有你的账号ID，随机生成的utmn参数，以及网址参数和guid开关。

<img class="alignnone size-full wp-image-485" title="ga-wap" src="http://cdn.54jack.com/images/2011/06/ga-wap.gif" alt="" width="680" height="450" />

上面的代码分别为：

<p style="padding-left: 30px;">
  <?php<br />   // Copyright 2010 Google Inc. All Rights Reserved.
</p>

<p style="padding-left: 30px;">
    $<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>_ACCOUNT = &#8220;MO-22601383-1&#8243;;<br />   $<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>_PIXEL = &#8220;/ga.php&#8221;;
</p>

<p style="padding-left: 30px;">
    function googleAnalyticsGetImageUrl() {<br />     global $<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>_ACCOUNT, $GA_PIXEL;<br />     $url = &#8220;&#8221;;<br />     $url .= $GA_PIXEL . &#8220;?&#8221;;<br />     $url .= &#8220;utmac=&#8221; . $GA_ACCOUNT;<br />     $url .= &#8220;&utmn=&#8221; . rand(0, 0x7fffffff);<br />     $referer = $_SERVER["HTTP_REFERER"];<br />     $query = $_SERVER["QUERY_STRING"];<br />     $path = $_SERVER["REQUEST_URI"];<br />     if (empty($referer)) {<br />       $referer = &#8220;-&#8221;;<br />     }<br />     $url .= &#8220;&utmr=&#8221; . urlencode($referer);<br />     if (!empty($path)) {<br />       $url .= &#8220;&utmp=&#8221; . urlencode($path);<br />     }<br />     $url .= &#8220;&guid=ON&#8221;;<br />     return str_replace(&#8220;&&#8221;, &#8220;&&#8221;, $url);<br />   }<br /> ?>
</p>

以及

<p style="padding-left: 30px;">
  <?php<br />   $googleAnalyticsImageUrl = googleAnalyticsGetImageUrl();<br />   echo &#8216;<img src=&#8221;&#8216; . $googleAnalyticsImageUrl . &#8216;&#8221; />&#8217;;?>
</p>

<p style="padding-left: 30px;">
   
</p>

<p style="padding-left: 30px;">
   
</p>

本站安装的是WP-T-WAP这个<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e6%89%8b%e6%9c%ba%e8%ae%bf%e9%97%ae/" title="查看手机访问中的全部文章" target="_blank">手机访问</a></span>及发布插件，因此，你需要把上述两段代码分别放置到**wp-t-wap/wap/index-wap2.php**这个文件的相应位置。完成之后最好先停用插件，再删除wap文件夹，然后启用以生成新的文件。

插件安装完成后，在24小时左右即可在GA后台查看手机访问的相关信息了，位于访问者>技术><span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%a7%bb%e5%8a%a8%e8%ae%be%e5%a4%87/" title="查看移动设备中的全部文章" target="_blank">移动设备</a></span>。效果如下图所示：

<img class="alignnone size-full wp-image-486" title="ga-mobile" src="http://cdn.54jack.com/images/2011/06/ga-mobile.gif" alt="" width="660" height="190" />