---
title: 外贸企业网站改版注意事项
author: 54jack
layout: post
permalink: /seo/redesign-tips-for-foreign-trade-site/
sina_t:
  - 'true'
views:
  - 564
  - 564
qq_t:
  - 'true'
duoshuo_thread_id:
  - 511638
yourls_shorturl:
  - http://t.xiaoq.in/6y
ta-thumbnail:
  - NoMediaFound
categories:
  - 搜索引擎优化
tags:
  - htaccess
  - 域名解析
  - 域名跳转
  - 外贸网站
  - 网站改版
  - 自定义错误
  - 谷歌管理员工具
---
互联网的精神是，产品永远处于BETA阶段。这里所说的BETA或者说测试阶段，并非指产品存在致命缺陷或者漏洞，并以此借口网站数据丢失，页面打不开，千奇百怪的错误。我们说网站处于BETA阶段是指产品需要不断完善和改进，BUG是肯定存在的，我们需要在网站的发展过程中不断修复。这些BUG可能在网站初期不易察觉，但是随着网站的发展会慢慢被用户或者自己发现。网站的小BUG可以通过细微修复来解决。

下面，我们说说网站的改版。网站为什么要改版？改版有什么目标？如何改版？这是改版之前首先需要考虑的问题。

一般来说，外贸企业<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%bd%91%e7%ab%99%e6%94%b9%e7%89%88/" title="查看网站改版中的全部文章" target="_blank">网站改版</a></span>可能是因为现在的网站无法满足用户及企业本身的需求，原来网站系统有问题并且通过小修小补不易解决，公司发展策略转变或升级，希望通过改版实现更好的用户体验，搜索引擎表现，提升品牌知名度。

无论什么原因，改版是必然趋势，当然改版不应过于频繁，不涉及系统构建或者整体布局的改造不能称作改版。过于频繁的改版会让访问者感觉公司过于轻率，不稳重，没有长远发展策略。

那么，改版过程中，需要注意些什么呢？外贸企业该如何改版呢？如何做到不丢失原有流量呢？因为，一个网站进行改版，很有可能URL结构会做些调整，空间会切换，系统会换掉，过时的下载文件会丢弃。以下几点可能需要注意：

1.  如果需要切换空间，这就涉及到了<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%9f%9f%e5%90%8d%e8%a7%a3%e6%9e%90/" title="查看域名解析中的全部文章" target="_blank">域名解析</a></span>的更改，我们知道<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%9f%9f%e5%90%8d%e8%a7%a3%e6%9e%90/" title="查看域名解析中的全部文章" target="_blank">域名解析</a></span>全球生效时间并不是实时的。一般需要24到72个小时才能全球生效。因为，修改<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%9f%9f%e5%90%8d%e8%a7%a3%e6%9e%90/" title="查看域名解析中的全部文章" target="_blank">域名解析</a></span>最好选择用户访问量少的时间，这个数据可以查看以往的访问记录。如果需要切换空间，我们最好先不要关闭原有空间，因为不同地区还有搜索引擎都有一种缓存机制。
2.  切换系统，URL结构调整，文件丢弃，这些问题都可以使用301永久重定向或者<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e9%94%99%e8%af%af/" title="查看自定义错误中的全部文章" target="_blank">自定义错误</a></span>页面来解决。如果只是更换了目录，用301重定向；如果彻底删除或改变了，使用自定义的403、/44错误页。
3.  进入<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%b0%b7%e6%ad%8c%e7%ae%a1%e7%90%86%e5%91%98%e5%b7%a5%e5%85%b7/" title="查看谷歌管理员工具中的全部文章" target="_blank">谷歌管理员工具</a></span>，设首选置域名，重新提交网站地图，然后是等待谷歌重新抓取页面了。<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%bd%91%e7%ab%99%e6%94%b9%e7%89%88/" title="查看网站改版中的全部文章" target="_blank">网站改版</a></span>之后，也许会有战略调整，因此站内链接（sitelink）可能也需要修改下。

以下给出一些常用代码：

不带www的跳转到www的域名：

rewritecond %{http_host} ^54jack.com [nc]  
rewriterule ^(.*)$ http://g.xiaoq.in/$1 [r=301,nc]

<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e9%94%99%e8%af%af/" title="查看自定义错误中的全部文章" target="_blank">自定义错误</a></span>页面：

ErrorDocument 403 http://g.xiaoq.in/  
ErrorDocument 404 http://g.xiaoq.in/  
当然，不一定要跳转到首页，可以自定义一个个性化的页面，提醒用户访问错误。

快速域名本地解析：  
开始，运行，输入C:WINDOWSsystem32driversetcHOSTS  
回车  
用记事本打开该文件并添加下行，然后保存。  
74.82.54.217 www.54jack.com