---
title: 广告公司如何管理及配置Google Analytics
author: 肖庆
layout: post
permalink: /google-analytics/advertising-agency-google-analytics-implementation/
ratings_users:
  - 2
ratings_score:
  - 10
ratings_average:
  - 5
views:
  - 7204
yourls_shorturl:
  - http://t.xiaoq.in/12
ta-thumbnail:
  - http://blog.xiaoq.in/thumb/cache/2013/1/1043-1.png;
categories:
  - Google Analytics
tags:
  - Google Analytics
  - MCC
  - 媒体资源
  - 广告代理公司
  - 账户
  - 配置文件
---
<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%b9%bf%e5%91%8a%e4%bb%a3%e7%90%86%e5%85%ac%e5%8f%b8/" title="查看广告代理公司中的全部文章" target="_blank">广告代理公司</a></span>往往会有很复杂的需求，比如客户量非常大，每个客户有不同的分支结构或子品牌，每个分支机构或子品牌又可能会有不同的网站，而每个网站又可能有单独的子域名或子目录需要分开进行监测分析。以下就介绍2种推荐的做法，<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%b9%bf%e5%91%8a%e4%bb%a3%e7%90%86%e5%85%ac%e5%8f%b8/" title="查看广告代理公司中的全部文章" target="_blank">广告代理公司</a></span>可以根据相应的业务需求进行配置，从而进行规范化地标准运作。

我们知道，<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>主要分为三个<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%b4%a6%e6%88%b7/" title="查看账户中的全部文章" target="_blank">账户</a></span>层级：账号（每个<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%b4%a6%e6%88%b7/" title="查看账户中的全部文章" target="_blank">账户</a></span>最多可以建立50个，但可以通过权限授权实现无限制绑定）&#8212;<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e9%85%8d%e7%bd%ae%e6%96%87%e4%bb%b6/" title="查看配置文件中的全部文章" target="_blank">配置文件</a></span>（一般用作监测不同的子域名或子目录）&#8212;<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%aa%92%e4%bd%93%e8%b5%84%e6%ba%90/" title="查看媒体资源中的全部文章" target="_blank">媒体资源</a></span>（一般用以查看不同访客类型或者满足相应的业务需求）。

<img class="alignnone  wp-image-1044" alt="accountsProfiles" src="http://blog.xiaoq.in/cdn/2013/01/accountsProfiles.png" width="600" />

<p style="text-align: center;">
  <a title="Accounts and Profiles" href="https://developers.google.com/analytics/resources/concepts/gaConceptsAccounts" target="_blank">Accounts and Profiles</a>
</p>

这种账户层次，跟<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-adwords/" title="Google Adwords" target="_blank">Google Adwords</a></span>的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/mcc/" title="查看MCC中的全部文章" target="_blank">MCC</a></span>（经理账户）是十分相似的，清晰的账户规划之后，<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%b9%bf%e5%91%8a%e4%bb%a3%e7%90%86%e5%85%ac%e5%8f%b8/" title="查看广告代理公司中的全部文章" target="_blank">广告代理公司</a></span>就可以很清晰地进行客户管理。AdWords中的各种授权管理及子账户关联，相信操作过一定数量账户的<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/sem/" title="SEM搜索引擎营销" target="_blank">SEM</a></span>是非常娴熟了，然而，往往很多公司（包括我见过的很多大公司），在<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/google-analytics/" title="查看Google Analytics中的全部文章" target="_blank">Google Analytics</a></span>的账户设置方面，往往显得不太专业。

上面说到，有2种账户部署方式 ，决定方式的不同主要取决于账户的流量媒介及标记手法。这里先说我们SEM经常会用到的一种：Roll up（上卷）。这种账户的话，一般是全球性的跨国公司或有着多个部门的大集体公司，它们使用不同的AdWords账户进行广告推广并有着独立的SEM和数据分析部门，总部希望看到全局性数据，下属分公司各自为政。

GA范例代码如下：

<script type=&#8217;text/javascript&#8217;>  
var \_gaq = \_gaq || [];  
\_gaq.push(['\_setAccount', 'UA-28069997-1']);  
\_gaq.push(['\_trackPageview']);  
**\_gaq.push(['t2\_setAccount', 'UA-28069998-1']);**  
** \_gaq.push(['t2\_trackPageview']);**  
(function() {  
var ga = document.createElement(&#8216;script&#8217;); ga.type = &#8216;text/javascript&#8217;; ga.async = true;  
ga.src = (&#8216;https:&#8217; == document.location.protocol ? &#8216;https://ssl&#8217; : &#8216;http://www&#8217;) + &#8216;.google-analytics.com/ga.js&#8217;;  
var s = document.getElementsByTagName(&#8216;script&#8217;)[0]; s.parentNode.insertBefore(ga, s);  
})();  
</script>

代码部署也很简单，在各个网站中，保留t2上面的那个默认账户代码，然后将t2的ID替换为相应网站所建立的账户的ID的即可。  
使用这种方式主要有以下几个好处：  
权限管理方便，下属机构方便管理，同时总部的数据也不会被污染。  
方便Google AdWords及<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/google-analytics/" title="查看Google Analytics中的全部文章" target="_blank">Google Analytics</a></span>进行账号管理。关联Google AdWords及<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/google-analytics/" title="查看Google Analytics中的全部文章" target="_blank">Google Analytics</a></span>一般有2个步骤：开启auto tag，到GA的设置中设置好数据来源（data source）。经过这两步之后，你的AdWords点击展示数据就可以直接呈现在GA后台了。当然如果有心的话，还能进行反向关联，把GA的数据导入到AdWords中，然后也能在AdWords的报告中看到GA中网站层面的表现情况。

当然，这种方式也会带来一些不便，即在做事件跟踪和电子商务跟踪配置时，需要添加2次代码。网上看到一个老外些的JS代码，似乎可以自动化实现，懂技术的童鞋可以看下：http://seo-website-designer.com/WsaGa/WsaGa.js

通常来说，我们会使用另外一种方式，就是给每个客户（子品牌）建立单独的GA账户，对应每个AdWords账户，再在各个账户中为其下的各个网站（或主域名）建立不同的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e9%85%8d%e7%bd%ae%e6%96%87%e4%bb%b6/" title="查看配置文件中的全部文章" target="_blank">配置文件</a></span>，保留一个无任何过滤器的配置文件，然后针对不同的业务需要使用过滤器建立其他配置文件（如按部门、语言、区域进行划分），再在各个配置文件中使用不同过滤器建立不同<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%aa%92%e4%bd%93%e8%b5%84%e6%ba%90/" title="查看媒体资源中的全部文章" target="_blank">媒体资源</a></span>（如SEO流量报告，PPC流量报告，品牌词广告报告，等等）。

当然，可能不同业务由不同人员进行管理，你可以给予不同人员相应的权限，让他们看到所需的配置文件或者对其数据进行个性化配置（前提是该人专业并且已经内部协调一致）。

当然，对于复杂业务的配置和代码安装调试过程中，可能会遇到各种问题，比如跨域跟踪，自我引荐，cookie路径设置，自定义变量的覆盖，电子商务跟踪的货币统一，时区统一等问题，需要根据具体问题进行分析解决。