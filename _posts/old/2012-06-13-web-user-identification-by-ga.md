---
title: 通过GA实现网站用户的识别
author: 肖庆
layout: post
permalink: /google-analytics/web-user-identification-by-ga/
sina_t:
  - 'true'
ratings_users:
  - 2
ratings_score:
  - 10
ratings_average:
  - 5
views:
  - 13415
yourls_shorturl:
  - http://t.xiaoq.in/1s
ta-thumbnail:
  - http://blog.xiaoq.in/thumb/cache/2012/6/806-1.png;
categories:
  - Google Analytics
tags:
  - cookie提取
  - IP地址
  - 用户识别
  - 电子商务
  - 自定义变量
  - 访客
---
<a title="joeghwu" href="http://weibo.com/joeghwu" target="_blank">joeghwu</a>的<a title="网站用户的识别" href="http://webdataanalysis.net/personal-view/web-user-identification/" target="_blank">网站用户的识别</a>这篇文章对于网站用户的识别方法和实际意义介绍的十分的全面，不过本文将介绍如何通过<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>来实现这种数据跟踪。

基于隐私保护，Google Analytics是不会显示<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ip%e5%9c%b0%e5%9d%80/" title="查看IP地址中的全部文章" target="_blank">IP地址</a></span>的，但是我们通过简单的PHP代码就可以获取到用户的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ip%e5%9c%b0%e5%9d%80/" title="查看IP地址中的全部文章" target="_blank">IP地址</a></span>。通过IP地址对用户进行识别存在诸多问题，比如校园网，企业网，网吧的用户，他们基本上是公用一个IP地址，通过IP来进行<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%94%a8%e6%88%b7%e8%af%86%e5%88%ab/" title="查看用户识别中的全部文章" target="_blank">用户识别</a></span>就非常的不准确了。

当前主流的分析工具基本上都是通过cookie来进行数据跟踪的，Google Analytics的cookie详解请参照蓝鲸的<a title="Google Analytics cookie内容详解" href="http://bluewhale.cc/2010-01-24/google-analytics-cookie.html" target="_blank">这篇文章</a>。通过PHP获取用户的cookie值有很多种方法，比如通过<a title="Google Analytics PHP cookie parser" href="http://joaocorreia.pt/google-analytics-scripts/google-analytics-php-cookie-parser/" target="_blank">PHP</a>实现或者通过<a title="Read Google Analytics Cookie Script" href="http://www.dannytalk.com/read-google-analytics-cookie-script/" target="_blank">javascript</a>实现（另外<a title="cloga" href="http://www.cloga.info/" target="_blank">cloga</a>也写了一个js代码，详见其网站源文件）。

IP和cookie值获取到了之后，我们就可以通过两者的组合来进行用户的初步定位了。我们把这两个值存储到<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%ae%bf%e5%ae%a2/" title="查看访客中的全部文章" target="_blank">访客</a></span>级别的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>中。

核心代码如下：

function _uGC(l, n, s) {  
if (!l || l == &#8220;&#8221; || !n || n == &#8220;&#8221; || !s || s == &#8220;&#8221;) return &#8220;-&#8221;;  
var i, i2, i3, c = &#8220;-&#8221;;　　i = l.indexOf(n);　　i3 = n.indexOf(&#8220;=&#8221;) + 1;  
if (i > -1) {　　　　i2 = l.indexOf(s, i);  
if (i2 < 0) {  
i2 = l.length;  
}　　　　c = l.substring((i + i3), i2);  
}  
return c;  
}  
var utma = \_uGC(document.cookie, &#8220;\__utma=&#8221;, &#8220;;&#8221;);  
var utmb = \_uGC(document.cookie, &#8220;\__utmb=&#8221;, &#8220;;&#8221;);  
var utmc = \_uGC(document.cookie, &#8220;\__utmc=&#8221;, &#8220;;&#8221;);  
var utmx = \_uGC(document.cookie, &#8220;\__utmx=&#8221;, &#8220;;&#8221;);  
var utmz = \_uGC(document.cookie, &#8220;\__utmz=&#8221;, &#8220;;&#8221;);  
var utmv = \_uGC(document.cookie, &#8220;\__utmv=&#8221;, &#8220;;&#8221;);  
var utmk = \_uGC(document.cookie, &#8220;\__utmk=&#8221;, &#8220;;&#8221;);  
var source = _uGC(utmz, &#8220;utmcsr=&#8221;, &#8220;|&#8221;);  
var medium = _uGC(utmz, &#8220;utmcmd=&#8221;, &#8220;|&#8221;);  
var term = _uGC(utmz, &#8220;utmctr=&#8221;, &#8220;|&#8221;);  
var content = _uGC(utmz, &#8220;utmcct=&#8221;, &#8220;|&#8221;);  
var campaign = _uGC(utmz, &#8220;utmccn=&#8221;, &#8220;|&#8221;);  
var numsa = utma.split(&#8220;.&#8221;);  
var numsz = utmz.split(&#8220;.&#8221;);

\_gaq.push(['\_setCustomVar', 1, numsa[1], &#8216;<? $ip=$\_SERVER["REMOTE\_ADDR"];echo $ip;?>&#8217;, 1]);  
\_gaq.push(['\_setCustomVar', 2, numsa[1], numsz[3], 1]);

通过这段代码，你就可以获取到每个用户的cookie及其对应IP了，数据在<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>中相应的键值中查看。

当然，上述代码获取到的数据可能还是不太准确，如果你在运营一个<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%94%b5%e5%ad%90%e5%95%86%e5%8a%a1/" title="查看电子商务中的全部文章" target="_blank">电子商务</a></span>网站，需要用户进行注册登录，那么把用户ID放到<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%ae%bf%e5%ae%a2/" title="查看访客中的全部文章" target="_blank">访客</a></span>级<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>中将会大大地提高准确性。至于代理的话，个人觉得必要性还不是太大，使用代理的人毕竟不太多，而且你还可以通过GA的各种次级维度（比如城市名，浏览器类型和版本，分辨率和操作系统等，完全重合的概率应该很低的吧）对用户进行细分。

<img class="alignnone size-full wp-image-807" title="ga user identification" src="http://xiaoq.in/g/pics/2012/06/ga-user-identification.png" alt="" width="600" height="280" />

以上是通过Google Analytics的自定义变量提取相关数据对<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%94%a8%e6%88%b7%e8%af%86%e5%88%ab/" title="查看用户识别中的全部文章" target="_blank">用户识别</a></span>做的一个尝试或者说实验，请注意保护用户隐私，GA不允许使用IP和个人隐私信息！

数据分析的一个重要步骤是数据收集，当我们收集到越来越多数据的时候，你会发现很多有趣的东西，比如一个用户很多IP，一个IP很多cookie，一个会员账号通过很多cookie+ip进行购物，但是结算的cookie可能就只是一个固定的，IP却可能是动态的，很可能付款时间在晚上，订购时间在中午。

至于为什么，你应该懂的~