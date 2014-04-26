---
title: GA在电子商务网站中的高级应用
author: 肖庆
layout: post
permalink: /google-analytics/ga-e-commerce-advanced-application/
sina_t:
  - 'true'
ratings_users:
  - 0
ratings_score:
  - 0
ratings_average:
  - 0
views:
  - 4787
yourls_shorturl:
  - http://g.xiaoq.in/b
ta-thumbnail:
  - http://blog.xiaoq.in/thumb/cache/2012/4/757-1.jpg;
categories:
  - Google Analytics
tags:
  - 数据分析
  - 数据整合
  - 电子商务
  - 电子商务跟踪
---
<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%94%b5%e5%ad%90%e5%95%86%e5%8a%a1/" title="查看电子商务中的全部文章" target="_blank">电子商务</a></span>网站的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e6%95%b0%e6%8d%ae%e5%88%86%e6%9e%90/" title="查看数据分析中的全部文章" target="_blank">数据分析</a></span>是一个非常严肃的问题，可以说任何一个缺乏<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e6%95%b0%e6%8d%ae%e5%88%86%e6%9e%90/" title="查看数据分析中的全部文章" target="_blank">数据分析</a></span>这个职位的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%94%b5%e5%ad%90%e5%95%86%e5%8a%a1/" title="查看电子商务中的全部文章" target="_blank">电子商务</a></span>公司，都是不完整的！数据分析的重要性已经是不言而喻的了，在此也不再累赘。

电子商务算是一个新兴的行业，当B2B的发展遇到瓶颈之后，越来越多的企业开始布局在线销售平台，称之为B2C平台。然而，大部分企业都用不上高端的数据分析工具，<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>作为一个强大的免费工具，是大多数企业的首选。工具免费并不意味着它不好用，其实Google Analytics中蕴藏着很多强大的功能，本文就尝试对这些高级功能进行一个较深入的挖掘，偏技术些。另外一篇较为基础的：<a title="基于数据分析提升转化率" href="http://xiaoq.in/google-analytics/improving-conversion-rate-based-on-analytics/" target="_blank">基于数据分析提升转化率</a>。  
[<img class="alignnone  wp-image-766" title="e-commerce-web-analytics" src="http://xiaoq.in/g/pics/2012/04/e-commerce-web-analytics3.jpg" alt="" width="500" height="796" />][1]

1. 导航菜单跟踪：onclick=&#8221;\_gaq.push(['\_trackEvent','click','parent-category','sub-category',1,false])&#8221;

筛选和排序也可以采用类似方式  
代码示例：  
onclick=&#8221;\_gaq.push(['\_trackEvent',' dimension',' color ','blue',1,false])&#8221;  
onclick=&#8221;\_gaq.push(['\_trackEvent',' sort',' price','lower',1,false])&#8221;

然后在事件中查看相应数据。  
排序和筛选使用高级细分和群组的功能也可以实现类似效果。

2. 热力图分析：  
GA：网页内分析；  
开源程序：ClickHeat  
第一个中的事件跟踪也一定程度达到热力图分析效果。

3. 404页面跟踪：\_gaq.push(['\_trackPageview', '/404.html?page=' + document.location.pathname + document.location.search + '&from=' + document.referrer]);

4. <span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%94%b5%e5%ad%90%e5%95%86%e5%8a%a1%e8%b7%9f%e8%b8%aa/" title="查看电子商务跟踪中的全部文章" target="_blank">电子商务跟踪</a></span>：

http://code.google.com/intl/zh-CN/apis/analytics/docs/tracking/gaTrackingEcommerce.html

http://www.cloga.info/archives/608.html

5. 各种跟踪代码部署相关文档：http://code.google.com/intl/zh-CN/apis/analytics/docs/tracking/eventTrackerOverview.html

6. 自定义变量跟踪：

\_gaq.push(['\_setCustomVar', 1, 'customer_id', '001', 1]);  
\_gaq.push(['\_setCustomVar', 2, 'country', '中国', 1]);  
\_gaq.push(['\_setCustomVar', 3, 'city', '广州', 1]);  
\_gaq.push(['\_setCustomVar', 4, 'name', '<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/" title="肖庆" target="_blank">肖庆</a></span>', 1]);  
\_gaq.push(['\_setCustomVar', 1, '蓝色T恤', 'sku-o1', 2]);  
7. 转化跟踪：  
方式一：AdWords代码

方式二：导入GA目标  
由于GA是根据最后点击计算转化，并且存在导入时差，因此一般建议使用上述AdWords跟踪，以了解全部辅助渠道，通过搜索渠道可以了解转化前的各种渠道来源关键词。

8. 再营销代码安装  
（直接使用转化标记或新建用户列表，或组合之，时间最长可设置为540天）：

9. 专题跟踪：  
方式一：事件跟踪  
<a href=&#8221;#&#8221; onclick=&#8221;\_gaq.push(['\_trackEvent','special','banner','christmas-2012',,true]);&#8221;>  
<img src=&#8221;#&#8221; width=&#8221;192&#8243; height=&#8221;228&#8243; onload=&#8221;\_gaq.push(['\_trackEvent','special-impressions','banner','christmas-2012',,true]);&#8221;/></a>  
分别记录图片展示次数和点击次数，相除可以得出点击率，在事件中查看。

方式二：网址构建器（建议在网址结尾处再加上?utm_nooverride=1，否则来源媒介等数据会覆盖从其他渠道进来的数据）注意区分大小写及保持一致性。EDM最好也使用此种方式标记，否则EDM流量都是进入引荐网址为相应邮箱的，从而无法区分订单到达来自EDM，系统邮件还是客服发送的邮件。

http://support.google.com/googleanalytics/bin/answer.py?hl=zh-Hans&#038;answer=55578

方式三：DFP工具。（推荐，兰亭等大型网站都在用，但是需要Adsense账号）  
使用方法：http://fairyfish.net/2009/10/23/google-ad-manager/

10. 关键词排名跟踪：  
参照UK站已加代码如下  
function rankingsPush() {  
var url = String(document.referrer);  
if (url.indexOf(&#8220;google.&#8221;) != -1) {  
var urlVars = {};  
var parts = url.replace(/[?&]+([^=&]+)=([^&]*)/gi, function (m, key, value) {  
urlVars[key] = value;  
});  
\_gaq.push(['\_setCustomVar', '2', 'Rankings', urlVars["cd"], 2]);  
}  
}  
….

rankingsPush();  
\_gaq.push(['\_trackPageview']);  
…..

另一种方式是通过GA的过滤器，较复杂，具体方式为：http://www.chrisabernethy.com/tracking-keyword-ranking-position-with-google-analytics/

11. 各种链接点击跟踪：  
onClick=&#8221;\_gaq.push(['\_trackEvent', 'outbound', 'verified', 'paypal']);&#8221;  
其他需要跟踪的点击依次类推，将outbound，verified，paypal分别替换相应的名称即可，数据再事件中查看，注意保持大小写一致。  
可以跟踪的点击有：信任标识，SNS链接，分享链接等其他需要跟踪的链接。

12. 注册表单提交跟踪：

onclick=&#8221;\_gaq.push(['\_trackEvent','form','register','submit',10,false]);  
其他需要跟踪的表单提交依次类推，将form，register，submit分别替换相应的名称即可，数据再事件中查看，注意保持大小写一致。  
可以跟踪的表单提交有：注册，登陆，订阅，查询订单，在线联系，等其他需要跟踪的表单行为。

13. 添加到购物车/心愿单跟踪：  
\_gaq.push(['\_trackEvent', 'add to cart','蓝色T恤', 'sku-01','99.99',true]);  
\_gaq.push(['\_trackEvent', 'add to wishlist','蓝色T恤', 'sku-01','99.99',true]);  
上述代码分别表示：事件类别、产品类别、产品型号、产品价格、非互动。

购物流程跟踪（针对单页支付，分页支付可以直接使用URL设置目标）：  
onclick=&#8221;\_gaq.push(['\_trackPageview', '/order/cart'])&#8221;;  
onclick=&#8221;\_gaq.push(['\_trackPageview', '/order/shipping'])&#8221;;  
onclick=&#8221;\_gaq.push(['\_trackPageview', '/order/payment'])&#8221;;  
onclick=&#8221;\_gaq.push(['\_trackPageview', '/order/confirmation'])&#8221;;  
onclick=&#8221;\_gaq.push(['\_trackPageview', '/order/pay'])&#8221;;  
/cart/后的值需明确表意，然后在GA中设置目标，分别依次设置为目标渠道，最终一步为目标网址，以下仅为示例，具体根据上述定义值。

14. 在线聊天工具跟踪  
Zopim默认已经整合GA，在事件中查看：

15. 站内搜索跟踪：  
在GA工具的配置文件设置中设置，如：

注：由于某些站对搜索结果的URL已经做了伪静态处理，默认无法跟踪到站内搜索，需要对网址进行虚拟页面改造。  
改造的方法，搜索结果页中：  
\_gaq.push(['\_trackPageview ']);  
定义为  
\_gaq.push(['\_trackPageview', '/search/?category=当前类别&q=当前搜索关键词']);

然后查询参数设置为：q  
类别参数设置为：category  
最终在网站搜索中查看关键词和搜索类别。

16. 搜索结果为空：  
如果搜索结果为空则附加以下代码到GA中：  
\_gaq.push(['\_setCustomVar', 1, 'no result','搜索关键词' , 3]);

放置于这行之前：  
\_gaq.push(['\_trackPageview']);

17. 蜘蛛爬行跟踪：  
GA实现方法：http://www.robinli007.com/archives/271

或使用开源工具Crawl Track，当然服务日志分析也是一种。

18. 路径分析：  
GA实现：各种流（如事件流、访客流、目标流等）  
安装Piwik开源工具，可以查看每个客户的浏览轨迹。

19. 网站优化工具的使用参照官方文档：http://support.google.com/websiteoptimizer/?hl=zh-Hans

20.数据对接：

方法一：通过导入数据到CRM或者网站后台：<a title="Integrating Google Analytics With a CRM" href="http://cutroni.com/blog/2007/10/29/integrating-google-analytics-with-a-crm/" target="_blank">http://cutroni.com/blog/2007/10/29/integrating-google-analytics-with-a-crm/</a>；<a title="Google Analytics PHP cookie parser" href="http://joaocorreia.pt/blog/2009/09/google-analytics-php-cookie-parser/#english" target="_blank">http://joaocorreia.pt/blog/2009/09/google-analytics-php-cookie-parser/#english</a>

方法二 ：通过自定义变量贯通订单数据和来源数据。

 [1]: http://xiaoq.in/g/pics/2012/04/e-commerce-web-analytics3.jpg