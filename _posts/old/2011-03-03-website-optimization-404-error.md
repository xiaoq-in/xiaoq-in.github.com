---
title: 网站优化实务之自定义错误页面
author: 54jack
layout: post
permalink: /seo/website-optimization-404-error/
sina_t:
  - 'true'
views:
  - 602
  - 602
qq_t:
  - 'true'
duoshuo_thread_id:
  - 511740
yourls_shorturl:
  - http://t.xiaoq.in/4x
ta-thumbnail:
  - NoMediaFound
categories:
  - 搜索引擎优化
tags:
  - 404
  - htaccess
  - 网站优化
  - 网站优化实务
  - 网站管理员工具
  - 谷歌
  - 错误页面
---
今天<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%b0%b7%e6%ad%8c/" title="查看谷歌中的全部文章" target="_blank">谷歌</a></span>启用了新的自定义<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e9%94%99%e8%af%af%e9%a1%b5%e9%9d%a2/" title="查看错误页面中的全部文章" target="_blank">错误页面</a></span>，一个带有<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%b0%b7%e6%ad%8c/" title="查看谷歌中的全部文章" target="_blank">谷歌</a></span>首页链接的LOGO，一个温馨提示顺带做个教育普及，再一个机器人。很全面的一个自定义<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e9%94%99%e8%af%af%e9%a1%b5%e9%9d%a2/" title="查看错误页面中的全部文章" target="_blank">错误页面</a></span>，也非常符合我们的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%bd%91%e7%ab%99%e4%bc%98%e5%8c%96/" title="查看网站优化中的全部文章" target="_blank">网站优化</a></span>之道。

<img class="alignnone size-full wp-image-172" title="g404" src="http://cdn.54jack.com/images/2011/03/g404.bmp" alt="" />

我们知道，网站的链接很难保持不变，特别是在网站经历改版之后。而且即使保持链接不变，也可能会存在删除不过时信息、不适宜信息的可能。在这个时候，自定义错误页面成为<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%bd%91%e7%ab%99%e4%bc%98%e5%8c%96/" title="查看网站优化中的全部文章" target="_blank">网站优化</a></span>的一个重要方面。

网站的自定义页面，正如本文第一句话说的一样，一般需要三个元素，网站LOGO，温馨提示，再一个趣味性的图片。这是很多网站都在使用的。以下截取几张网站的自定义错误页面。当然，有些网站的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/404/" title="查看404中的全部文章" target="_blank">404</a></span>页面是自动跳转到首页或者存档页面，各有利弊，自当权衡。

<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/404/" title="查看404中的全部文章" target="_blank">404</a></span>的自定义在unix系统中可以创建.<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/htaccess/" title="查看htaccess中的全部文章" target="_blank">htaccess</a></span>文件，

代码如下：

RewriteEngine On  
RewriteBase /  
ErrorDocument 404 /404.html

豆瓣网。

<img class="alignnone size-full wp-image-169" title="douban404" src="http://cdn.54jack.com/images/2011/03/douban404.bmp" alt="" />

博客大巴

<img class="alignnone size-full wp-image-170" title="blogbus404" src="http://cdn.54jack.com/images/2011/03/blogbus404.bmp" alt="" />

译言网

<img class="alignnone size-full wp-image-171" title="yeeyan404" src="http://cdn.54jack.com/images/2011/03/yeeyan404.bmp" alt="" />

其实在谷歌的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%bd%91%e7%ab%99%e7%ae%a1%e7%90%86%e5%91%98%e5%b7%a5%e5%85%b7/" title="查看网站管理员工具中的全部文章" target="_blank">网站管理员工具</a></span>中有一个创建自定义错误页面的增强型小工具，具体位置见下图。

<img class="alignnone size-full wp-image-173" title="gw404" src="http://cdn.54jack.com/images/2011/03/gw404.bmp" alt="" />

简体中文版的代码如下：  
<script type=&#8221;text/javascript&#8221;>var GOOG\_FIXURL\_LANG = &#8216;zh_CN&#8217;;  
  var GOOG\_FIXURL\_SITE = **&#8216;http://g.xiaoq.in&#8217;**  
</script><script type=&#8221;text/javascript&#8221;  
  src=&#8221;http://linkhelp.clients.google.com/tbproxy/lh/wm/fixurl.js&#8221;></script>

<div id="zh-CN_layer">
  <pre>主要作用是自动识别带www或者不带www的，并提出建议，根据网站搜索引擎收录信息放置搜索框供用户搜索，对一些网址链接常见错误进行提示等。</pre>
  
  <pre>网站的404错误时改善用途体验及保留网站原有流量的重要措施，不容忽视。</pre>
</div>