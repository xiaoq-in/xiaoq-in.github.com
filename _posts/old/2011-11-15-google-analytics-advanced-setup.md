---
title: Google Analytics高级定制
author: 肖庆
layout: post
permalink: /google-analytics/google-analytics-advanced-setup/
views:
  - 6258
sina_t:
  - 'true'
ratings_users:
  - 0
ratings_score:
  - 0
ratings_average:
  - 0
duoshuo_thread_id:
  - 511641
yourls_shorturl:
  - http://t.xiaoq.in/44
ta-thumbnail:
  - http://blog.xiaoq.in/thumb/cache/2011/11/50-1.gif;
categories:
  - Google Analytics
tags:
  - Google Analytics
  - 谷歌分析
  - 配置文件
  - 高级定制
---
今天很惊奇地发现，我的博客关键词“<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="谷歌分析" target="_blank">谷歌分析</a></span>”居然在搜搜排名第二，在之前Google的排名最好记录也只是“<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%b0%b7%e6%ad%8c%e5%88%86%e6%9e%90/" title="查看谷歌分析中的全部文章" target="_blank">谷歌分析</a></span>博客”排名在首页。

<a href="http://www.soso.com/q?pid=s.idx&cid=s.idx&w=%B9%C8%B8%E8%B7%D6%CE%F6" target="_blank"><img class="alignnone  wp-image-51" title="Google Analytics" src="http://xiaoq.in/g/pics/2011/11/Google-Analytics.gif" alt="" width="550" /></a>

言归正传，<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>是我最喜欢的一个分析工具，最近GA也上线了很多新功能，比如访问者流，目标流，多渠道路径，实时报告。这些新功能暂且不说，如何添加基本的代码这个问题大家都知道，但是要做更精细和精准化的数据分析，还有更多工作需要做&#8230;&#8230;

1.  事件跟踪：事件跟踪主要用来跟踪网站的一些内部行为，比如表单提交，按钮操作，点击行为，等等。这个用的人也很多，但是你知道吗，事件跟踪还可以做更多的事情，比如关键词跟踪，更多的关键词跟踪。我们知道，百度、搜搜，谷歌的搜索结果URL中都有自动获取了用户的上一次搜索记录，这样通过在事件跟踪中使用PHP函数调用引荐网址的动态值，那么你可以获取用户在通过关键词进入你的网站之前还搜索了什么，有了更多的关键词，你可以做更细致的用户搜索习惯分析。一般而言，处于购买初级阶段的用户打算购买一件商品会选择同时进行多项关键词矫正，比如：我打算买诺基亚手机，可能会先搜索“诺基亚手机”，然后再搜索“千元左右诺基亚手机”，再然后可能会搜索“诺基亚N7系列”。如果你知道用户在最终点击你们的广告之前还会搜索什么词，那么购买相关的关键词加深下他们的印象，效果可能会大不相同。URL示例：<a title="肖庆的博客" href="http://www.baidu.com/s?bs=%D0%A4%C7%EC&f=8&rsv_bp=1&rsv_spt=3&wd=%D0%A4%C7%EC%B5%C4%B2%A9%BF%CD&inputT=1396" target="_blank">http://www.baidu.com/s?bs=%D0%A4%C7%EC&f=8&rsv_bp=1&rsv_spt=3&wd=%D0%A4%C7%EC%B5%C4%B2%A9%BF%CD&inputT=1396</a>
2.  自定义变量：自定义变量一般用来跟踪用户相关的东西，比如网站语言，地区分站，浏览记录，订购历史等。通过语言或区域定位，你可以为客户推销该地区更最畅销的产品，通过浏览记录和订购历史，你可以对犹豫不决的客户进行邮件营销。卓越亚马逊的这点做的非常到位，不过他们并非使用的GA，我想说的是免费的并不是不好用不能用，如果你懂编程的话，完全可以通过API与相应的邮件系统对接实现定制化的邮件营销。
3.  自定义搜索引擎：谷歌默认自带的搜索引擎可能并不包括你本地的搜索引擎，比如搜搜，那么添加相关的定制代码可以让你在搜索的随机模块中查看SEO的关键词。当然，如果你懂JS或者其他编程技术的话，还可以对Google全球不同地区的搜索引擎进行定义并区分开来，同时针对图片搜索和地图搜索再来一个更深入细致的细分。否则，默认的搜索关键词会让你不知它们到底从哪里来的，是google.com还是google.fr呢？是google.com还是images.google.com呢？*Advanced Web Metrics* with <span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/google-analytics/" title="查看Google Analytics中的全部文章" target="_blank">Google Analytics</a></span> 的作者Brian Clifton写过两个js文件，可以做到这点，只可惜它的那个免费版本只支持旧版的GA，新版的定制代码偶然在<a href="http://ga-experts.com/" target="_blank">http://ga-experts.com/</a>这个网站看到，大家可以试用下，右键查看源文件然后另存为，不过这个版权说明中写道是不能免费使用的。
4.  同步到服务器日志文件：\_gaq.push(['\_setLocalRemoteServerMode']);添加这段代码本来是用作与Urchin同步数据的，但是你同样可以把你的GA跟踪数据同步到你的网站日志系统。
5.  <a title="用Google Analytics（谷歌分析）跟踪搜索引擎蜘蛛" href="http://g.xiaoq.in/cn/google-analytics/tracking-search-bots-in-google-analytics/" target="_blank">用Google Analytics（谷歌分析）跟踪搜索引擎蜘蛛</a>：做SEO的必备。
6.  目标设置。搜索设置。电子商务跟踪。Adwords关联。这些也是不要忽视的。
7.  请注意：务必保证一个无干扰的原始数据文件，其中不包含任何的过滤器或者其他干扰原始数据的配置。

希望以上的这些<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e9%ab%98%e7%ba%a7%e5%ae%9a%e5%88%b6/" title="查看高级定制中的全部文章" target="_blank">高级定制</a></span>可以为你更精准的营销推广带来一些数据支持。