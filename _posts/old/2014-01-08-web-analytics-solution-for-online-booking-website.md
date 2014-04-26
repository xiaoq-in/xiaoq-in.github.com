---
title: 数据分析解决方案之：预订类网站
author: 肖庆
layout: post
permalink: /analytics/web-analytics-solution-for-online-booking-website/
ratings_users:
  - 1
ratings_score:
  - 5
ratings_average:
  - 5
views:
  - 526
ta-thumbnail:
  - http://blog.xiaoq.in/cdn/2014/01/form-tracking-jquery.gif;http://blog.xiaoq.in/cdn/2014/01/form-tracking-micros.gif;http://blog.xiaoq.in/cdn/2014/01/form-submission-listener.gif;http://blog.xiaoq.in/cdn/2014/01/form-submit-listener.gif;http://blog.xiaoq.in/cdn/2014/01/weather-micros.gif;http://blog.xiaoq.in/cdn/2014/01/weather-done.gif;http://blog.xiaoq.in/cdn/2014/01/weather-api-tag.gif;http://blog.xiaoq.in/cdn/2014/01/weather-ua-dimension.gif;
categories:
  - 数据分析
tags:
  - GTM
  - UA
  - 事件跟踪
  - 天气
  - 数据分析解决方案
  - 机票预订
  - 自定义指标
  - 自定义维度
  - 解决方案
  - 酒店预订
---
在线预订是很多网站的运营模式，这其中主要包括旅游类网站、<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e6%9c%ba%e7%a5%a8%e9%a2%84%e8%ae%a2/" title="查看机票预订中的全部文章" target="_blank">机票预订</a></span>、<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e9%85%92%e5%ba%97%e9%a2%84%e8%ae%a2/" title="查看酒店预订中的全部文章" target="_blank">酒店预订</a></span>、医院预约等网站，当然铁道部的那个12306也算，这类网站的一个显著特性是：表单填写。表单是这类网站的最重要转化元素。本文将以新版的火车票预订网站（<https://kyfw.12306.cn/otn/>）为例讲述如何使用Google Tag Manager和<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>（<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ua/" title="查看UA中的全部文章" target="_blank">UA</a></span>）对这类网站的表单进行跟踪和代码部署配置。

要进行表单跟踪，首先我们必须了解一些基本的jquery知识，主要是其中的元素取值相关函数，这里推荐去W3C这个网站学习<a title="jQuery 教程" href="http://www.w3school.com.cn/jquery/" target="_blank">jQuery 教程</a>。

当然，如果你并不熟悉的话，也不要紧，下面的代码基本都是通用的，你可能只需要根据具体情况修改几个命名而已。如下图所示，我们先来体验下如何通过jquery取数据：<img class="alignnone  wp-image-1542" alt="form tracking jquery" src="http://blog.xiaoq.in/cdn/2014/01/form-tracking-jquery.gif" width="600" />

&nbsp;

代码片段：

$(&#8216;form&#8217;).find(&#8216;input[id=fromStationText]&#8216;).val();  
$(&#8216;form&#8217;).find(&#8216;input[id=toStationText]&#8216;).val();  
$(&#8216;form&#8217;).find(&#8216;input[id=train_date]&#8216;).val();  
$(&#8216;form&#8217;).find(&#8216;input[id=back\_train\_date]&#8216;).val();

其中，你只需要点击各个需要跟踪的区域，右键-审查元素，即可找到相应的元素ID，如果没有id，用class或者name也行，只要保持是惟一性即可。

当然，我们这里是需要把这些字段通过<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/gtm/" title="查看GTM中的全部文章" target="_blank">GTM</a></span>的宏来存储并且最终赋值到<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>里面的。<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>器的命名方法可以这样：

事件类别：提交表单

事件操作：出发点-目的地

事件标签：出发日-返程日

事件价值：预订张数（这里不能买多张没法示例，如果有成人票+儿童票，可以中间用0隔开，比如成人票和儿童票各1张，最终目标价值为101，到时再分列开来即可，这样做的目的是因为GA的事件目标价值仅支持integer/整数）

下面，看下<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/gtm/" title="查看GTM中的全部文章" target="_blank">GTM</a></span>中是如何操作的吧：

1、如下图所示建立一个宏，其他的表单跟踪内容类似方法，可通过复制然后修改其中的两个名字来快捷建立其他的。

<img class="alignnone size-full wp-image-1543" alt="form tracking micros" src="http://blog.xiaoq.in/cdn/2014/01/form-tracking-micros.gif" width="600" height="460" />

2、建立表单跟踪的事件触发规则，一般情况下是设置为所有页面，当然也可以排除些确实没有表单填写的页面。

3、建立一个表单跟踪的监听规则，event=gtm.formSubmit，如下图所示：

<img class="alignnone size-full wp-image-1544" alt="form submission listener" src="http://blog.xiaoq.in/cdn/2014/01/form-submission-listener.gif" width="700" height="400" />

4、添加一个<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>的监听标签，设置延时，时间一般使用默认的即可，如下图所示：

<img class="alignnone size-full wp-image-1545" alt="form submit listener" src="http://blog.xiaoq.in/cdn/2014/01/form-submit-listener.gif" width="730" height="660" />

5、再添加一个<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ua/" title="查看UA中的全部文章" target="_blank">UA</a></span>的事件跟踪（以新建TAG的形式添加），按照本文开头的命名方式填入参数的对应值，需要注意的是你需要替换其中的动态参数为上面设置的对应的宏，触发规则选择上面设置的Form Submission Listener这个规则。

通过以上的五个步骤，你就可以发布然后到热门事件中查看数据了，测试方法主要有3个：一个是看实时事件跟踪报告，另外一个是开启debug模式，再一个是在network中查看http://www.google-analytics.com/collect的Query String Parameters，去网站实际搜索下就可以看到结果了。

前几天在微博上发了一个用<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e7%bb%b4%e5%ba%a6/" title="查看自定义维度中的全部文章" target="_blank">自定义维度</a></span>跟踪<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%a4%a9%e6%b0%94/" title="查看天气中的全部文章" target="_blank">天气</a></span>情况的微博，大家好像比较感兴趣，这里再说下如何设置。其实，<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%a4%a9%e6%b0%94/" title="查看天气中的全部文章" target="_blank">天气</a></span>对于预订类网站影响还蛮大的，特别是外卖类网站或者旅游类网站。其实也简单，在GTM中新增一个宏、一个规则、修改一个标签，如下图所示：

<img class="alignnone size-full wp-image-1546" alt="weather micros" src="http://blog.xiaoq.in/cdn/2014/01/weather-micros.gif" width="725" height="530" /> <img class="alignnone size-full wp-image-1547" alt="weather done" src="http://blog.xiaoq.in/cdn/2014/01/weather-done.gif" width="730" height="415" /> <img class="alignnone size-full wp-image-1548" alt="weather api tag" src="http://blog.xiaoq.in/cdn/2014/01/weather-api-tag.gif" width="730" height="655" /> <img class="alignnone size-full wp-image-1549" alt="weather ua dimension" src="http://blog.xiaoq.in/cdn/2014/01/weather-ua-dimension.gif" width="600" height="165" />

记得去UA中添加Weather这个<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e7%bb%b4%e5%ba%a6/" title="查看自定义维度中的全部文章" target="_blank">自定义维度</a></span>，注意要对应索引号。

其中Weather API tag的代码如下（已经考虑到https的支持，如网站本身有jquery则可以去掉jquery库的引用）：

<script src=&#8221;//ajax.googleapis.com/ajax/libs/jquery/1.8.2/jquery.min.js&#8221;></script>  
<script type=&#8221;text/javascript&#8221; src=&#8221;//j.maxmind.com/app/geoip.js&#8221;></script>  
<script type=&#8221;text/javascript&#8221;>  
var lat = geoip_latitude();  
var lon = geoip_longitude();  
var weather = &#8220;&#8221;;  
var weatherAPI = &#8220;http://api.openweathermap.org/data/2.5/weather?lat=&#8221; + lat + &#8220;&lon=&#8221; + lon;

$.ajax({  
type : &#8220;POST&#8221;,  
dataType : &#8220;jsonp&#8221;,  
url : weatherAPI + &#8220;&units=metric&callback=?&#8221;,  
async : true,  
success : function(data){  
weather = data.weather[0].main;  
dataLayer.push({&#8220;weather&#8221;:weather});  
dataLayer.push({&#8220;event&#8221;:&#8221;weatherDone&#8221;});  
},  
error: function(errorData){  
console.log(&#8220;Error while getting weather data :: &#8221; + errorData.status);  
dataLayer.push({&#8220;event&#8221;:&#8221;weatherDone&#8221;});  
}  
});  
</script>

clientId几乎成为我使用UA和GTM的标配了~

function(){  
var clientId = ga.getAll()[0].get(&#8216;clientId&#8217;);  
return clientId;  
}

通过以上这些设置，那些表单跟踪就轻松搞定了。GA的站内搜索在这种网站大多数情况下其实是不太好用的，因为它们都基于某些考虑，让URL变得不那么规则和浅显易懂，很难去直接提取参数，而且站内搜索报告很难与其他维度指标进行交叉组合的。当然，如有你的自定义维度和指标有空的话，上面的事件跟踪改成自定义维度和指标也是未尝不可的。

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;