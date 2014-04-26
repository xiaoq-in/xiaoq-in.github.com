---
title: 更新GA再营销代码提高统计准确率
author: 肖庆
layout: post
permalink: /google-analytics/ga-remarketing-without-adblock/
ratings_users:
  - 2
ratings_score:
  - 10
ratings_average:
  - 5
views:
  - 1147
yourls_shorturl:
  - http://t.xiaoq.in/1
ta-thumbnail:
  - https://xiaoq.in/thumb/cache/2013/8/1271-1.png;
categories:
  - Google Analytics
tags:
  - AdBlock
  - GA
  - 事件跟踪
  - 再营销
  - 自定义变量
---
根据国外一项<a title="AdBlock Report" href="http://clarityray.com/Content/ClarityRay_AdBlockReport.pdf" target="_blank">研究报告</a>，在美国及欧洲，大约有9.26%的广告会被屏蔽，而<span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%86%8d%e8%90%a5%e9%94%80/" title="查看再营销中的全部文章" target="_blank">再营销</a></span>代码片段中的stats.g.doubleclick.net/dc.js不幸被列在这个<a title="easylist" href="https://easylist-downloads.adblockplus.org/easylist.txt" target="_blank">名单</a>之内，可以自行安装<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/adblock/" title="查看AdBlock中的全部文章" target="_blank">AdBlock</a></span>这个插件查看。如果用户安装了这个插件并启用过滤掉了那个URL，那么你也就无法收集和跟踪到这部分数据了，从而造成数据统计误差。

<img class="alignnone size-full wp-image-1272" alt="adblock" src="http://cdn.xiaoq.in/2013/08/adblock.png" width="530" height="330" />

在此，我们提供一个解决方案，原理是这样的：如果用户安装了插件致使<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>中的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%86%8d%e8%90%a5%e9%94%80/" title="查看再营销中的全部文章" target="_blank">再营销</a></span>代码无法执行，则使用传统的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>代码，否则执行<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%86%8d%e8%90%a5%e9%94%80/" title="查看再营销中的全部文章" target="_blank">再营销</a></span>的代码。同时，为了统计有用户安装相关插件的占比，我们还可以使用<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>或<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>跟踪来追踪这个数据占比（这里提供的是<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>实现，同理也可以用<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>）。

首先，我们通过这个javascript函数判断用户是否安装屏蔽了dc.js：

<table>
  <tr>
    <td>
      <script>
    </td>
  </tr>
  
  <tr>
    <td>
    </td>
    
    <td>
      var _adblock = true;
    </td>
  </tr>
  
  <tr>
    <td>
    </td>
    
    <td>
      </script>
    </td>
  </tr>
  
  <tr>
    <td>
    </td>
    
    <td>
      <script src=&#8221;<a href="http://xiaoq.in/js/advertising.js" target="_blank">http://xiaoq.in/js/advertising.js</a>&#8220;></script>
    </td>
  </tr>
</table>

其次，我们使用页面级的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>进行跟踪这个比例：

<table>
  <tr>
    <td>
      if ( !_adblock ) {
    </td>
  </tr>
  
  <tr>
    <td>
    </td>
    
    <td>
      _gaq.push(['_setCustomVar',3,'Adblocker','Not Installed',3]);
    </td>
  </tr>
  
  <tr>
    <td>
    </td>
    
    <td>
      } else {
    </td>
  </tr>
  
  <tr>
    <td>
    </td>
    
    <td>
      _gaq.push(['_setCustomVar',3,'Adblocker','Installed',3]);
    </td>
  </tr>
  
  <tr>
    <td>
    </td>
    
    <td>
      }
    </td>
  </tr>
</table>

再次，我们通过以下函数自动识别使用哪个代码片段：

<table>
  <tr>
    <td>
      (function() {
    </td>
  </tr>
  
  <tr>
    <td>
    </td>
    
    <td>
    </td>
  </tr>
  
  <tr>
    <td>
    </td>
    
    <td>
      if ( !_adblock ) { //load dc.js unless user has opted for <span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/adblock/" title="查看AdBlock中的全部文章" target="_blank">AdBlock</a></span>
    </td>
  </tr>
  
  <tr>
    <td>
    </td>
    
    <td>
      ga = document.createElement(&#8216;script&#8217;); ga.type = &#8216;text/javascript&#8217;; ga.async = true;
    </td>
  </tr>
  
  <tr>
    <td>
    </td>
    
    <td>
      ga.src = (&#8216;https:&#8217; == document.location.protocol ? &#8216;https://&#8217; : &#8216;http://&#8217;) + &#8216;stats.g.doubleclick.net/dc.js&#8217;;
    </td>
  </tr>
  
  <tr>
    <td>
    </td>
    
    <td>
      s = document.getElementsByTagName(&#8216;script&#8217;)[0]; s.parentNode.insertBefore(ga, s);
    </td>
  </tr>
  
  <tr>
    <td>
    </td>
    
    <td>
      } else { //otherwise load ga.js
    </td>
  </tr>
  
  <tr>
    <td>
    </td>
    
    <td>
      ga = document.createElement(&#8216;script&#8217;); ga.type = &#8216;text/javascript&#8217;; ga.async = true;
    </td>
  </tr>
  
  <tr>
    <td>
    </td>
    
    <td>
      ga.src = (&#8216;https:&#8217; == document.location.protocol ? &#8216;https://ssl&#8217; : &#8216;http://www&#8217;)+ &#8216;.google-analytics.com/ga.js&#8217;;
    </td>
  </tr>
  
  <tr>
    <td>
    </td>
    
    <td>
      s = document.getElementsByTagName(&#8216;script&#8217;)[0]; s.parentNode.insertBefore(ga, s);
    </td>
  </tr>
  
  <tr>
    <td>
    </td>
    
    <td>
      }
    </td>
  </tr>
  
  <tr>
    <td>
    </td>
    
    <td>
      })();
    </td>
  </tr>
</table>

这样，就搞定了。既能够更完整地收集到用户访问数据，同时还能够充分利用GA的再营销进行更细致的用户细分。

参考文章：

1.  <http://andrescholten.net/google-analytics-retargeting-for-adwords-and-adblock-software/>
2.  <http://www.analyticsresults.com/2013/03/doubleclick-remarketing-and-adblock-our.html>
3.  <http://www.statstory.com/how-many-users-block-your-ads-find-out/>
4.  <http://www.lunametrics.com/blog/2012/07/30/adwords-remarketing-google-analytics/>
5.  <http://www.blastam.com/blog/index.php/2013/04/google-analytics-remarketing-tag-concerns-solved/>

&nbsp;