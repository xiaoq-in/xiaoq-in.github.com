---
title: 谷歌分析事件跟踪及自定义变量之WordPress应用
author: 54jack
layout: post
permalink: /google-analytics/custom-variable-applications/
sina_t:
  - 'true'
views:
  - 4121
  - 4121
qq_t:
  - 'true'
duoshuo_thread_id:
  - 511907
yourls_shorturl:
  - http://t.xiaoq.in/23
ratings_users:
  - 1
ratings_score:
  - 5
ratings_average:
  - 5
ta-thumbnail:
  - NoMediaFound
categories:
  - Google Analytics
tags:
  - WordPress
  - 一号店
  - 事件跟踪
  - 引荐网址
  - 敦煌网
  - 红孩子
  - 自定义变量
---
今晚研究了两个知名的网上商城：<a title="一号店" href="http://www.yihaodian.com/" target="_blank">一号店</a>和<a title="红孩子" href="http://www.redbaby.com.cn/" target="_blank">红孩子</a>，发现他们有一个共同的特点，就是使用了<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>，只不过前者<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e4%b8%80%e5%8f%b7%e5%ba%97/" title="查看一号店中的全部文章" target="_blank">一号店</a></span>使用的付费跟踪软件（应该是<a title="AdViva" href="http://www.mediav.com/products/adviva/" target="_blank">这个</a>），把点击传递到cookie中，而<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%ba%a2%e5%ad%a9%e5%ad%90/" title="查看红孩子中的全部文章" target="_blank">红孩子</a></span>则是使用的<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>，通过定义<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>的不同值来跟踪各个位置的点击详情。之前还看到<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e6%95%a6%e7%85%8c%e7%bd%91/" title="查看敦煌网中的全部文章" target="_blank">敦煌网</a></span>也是在其首页对各个模块文章进行了<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>标记。下面是它们源文件截图：

<img class="alignnone size-full wp-image-499" title="yihaodian-track" src="http://blog.xiaoq.in/cdn/images/2011/06/yihaodian-track.png" alt="" width="800" height="400" />

<p style="text-align: center;">
  <span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e4%b8%80%e5%8f%b7%e5%ba%97/" title="查看一号店中的全部文章" target="_blank">一号店</a></span>的事件跟踪代码
</p>

<img class="alignnone size-full wp-image-500" title="redbaby-track" src="http://blog.xiaoq.in/cdn/images/2011/06/redbaby-track.png" alt="" width="980" height="220" />

<p style="text-align: center;">
  <span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%ba%a2%e5%ad%a9%e5%ad%90/" title="查看红孩子中的全部文章" target="_blank">红孩子</a></span>的事件跟踪代码
</p>

<img class="alignnone size-full wp-image-501" title="dhgate-track" src="http://blog.xiaoq.in/cdn/images/2011/06/dhgate-track.png" alt="" width="1000" height="180" />

<p style="text-align: center;">
  <span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e6%95%a6%e7%85%8c%e7%bd%91/" title="查看敦煌网中的全部文章" target="_blank">敦煌网</a></span>的事件跟踪代码
</p>

<p style="text-align: left;">
  于是，后来就想到在自己的博客实现这样的功能，其实很简单，只需要修改一下文章链接的代码即可，具体显示效果可看本站首页的最新博客文章源文件代码。
</p>

<p style="text-align: left;">
  修改后的代码如下：
</p>

<p style="text-align: left;">
  <a href=&#8221;<?php the_permalink() ?>&#8221; target=&#8221;_blank&#8221; onClick=&#8221;_gaq.push(['_trackEvent', '首页', '最新', '<?php the_permalink() ?>']);&#8221; rel=&#8221;bookmark&#8221; title=&#8221;Permanent Link to <?php the_title(); ?>&#8221;><?php the_title(); ?></a>
</p>

<p style="text-align: left;">
  然后看到了最近很火的一个网站，点点轻博客。它的广告投入我想大家是都知道的，于是为了了解用户最终通过哪种渠道获知他们的网站，想到了使用_setReferrerOverride()来确定用户来到网站的<strong>最后一个</strong><span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%bc%95%e8%8d%90%e7%bd%91%e5%9d%80/" title="查看引荐网址中的全部文章" target="_blank">引荐网址</a></span>来源。
</p>

<p style="text-align: left;">
  我们知道GA默认是统计最后一次的广告来源的（除非是直接输入网址或者收藏夹进入），我们也可以通过在广告系列中加入参数<a title="utm_nooverride的使用" href="http://www.cloga.info/archives/551.html" target="_blank">utm_nooverride=1</a>来实现之后的广告系列无法覆盖之前的cookie这种功能。
</p>

<p style="text-align: left;">
  因为<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%bc%95%e8%8d%90%e7%bd%91%e5%9d%80/" title="查看引荐网址中的全部文章" target="_blank">引荐网址</a></span>并不能覆盖之前的cookie，如果最后一次是通过直接输入网址或者收藏夹进入网站，那么如果该访问者之前通过其他渠道来到网站，GA后台是把之前的广告系列判断为带来注册和转换的广告来源。因此跟踪引荐来源网址在CPC中就很有必要了。
</p>

### <a title="_setReferrerOverride()" href="http://code.google.com/intl/zh-CN/apis/analytics/docs/gaJS/gaJSApiCampaignTracking.html" target="_blank">_setReferrerOverride()</a>

<p style="text-align: left;">
  <code>_setReferrerOverride(newReferrerUrl)</code>设置用于确定广告系列跟踪值的引荐来源网址。使用此方法可让 iFrame 中的窗口小部件正确跟踪引荐来源。默认情况下，广告系列跟踪使用 <code>document.referrer</code> 属性来确定引荐来源网址，该网址将被传入 GIF 请求的 <code>utmr</code> 参数中。不过，您可以使用自己的值覆盖此参数。例如，如果您将新的引荐来源网址设置为 <code>http://www.google.com/search?hl=en&q=hats</code>，则广告系列 Cookie 将会使用 <code>source=google</code>、<code>medium=organic</code> 和 <code>keyword=hats</code>存储一个新广告系列。
</p>

#### 参数

<p style="text-align: left;">
  <code>&lt;em>String&lt;/em>   newReferrerOverride </code>相应文档引荐来源网址的新网址。
</p>

* * *

<p style="text-align: left;">
   
</p>

 在PHP程序中可以使用如下代码：

\_gaq.push(['\_setReferrerOverride','<?php $ref = getenv("HTTP_REFERER"); echo $ref;?>']);

通过页面级的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>来跟踪<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/wordpress/" title="查看WordPress中的全部文章" target="_blank">WordPress</a></span>中**文章页面**的几个重要参数：分类，评论数量，浏览次数，月份，标签，可以很方便地了解自己文章受欢迎的话题，关注度，灵感爆发期等等。

同样，如果你把GA应用在商业领域，可以自定义最关注的5个变量（如产品类别，浏览次数，城市，语言等），然后跟踪并分析它们吧。

下面是<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/wordpress/" title="查看WordPress中的全部文章" target="_blank">WordPress</a></span>中上述<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>跟踪的源代码，供参考：

<?php if (is_single() ) { ?>  
         <?php if (have\_posts()) : while (have\_posts()) : the\_post(); ?>\_gaq.push(['_setCustomVar', 1, 'category', '<?php  
$category = get\_the\_category();  
echo $category[0]->cat_name;  
?>&#8217;, 1]);  
 \_gaq.push(['\_setCustomVar', 2, 'comment', '<?php comments_number('0','1','%'); ?>条评论', 1]);  
 \_gaq.push(['\_setCustomVar', 3, 'view', '<?php if(function\_exists('the\_views')) { the_views(); } ?>', 1]);  
 \_gaq.push(['\_setCustomVar', 4, 'date', '<?php the_time('Ym'); ?>', 1]);  
 \_gaq.push(['\_setCustomVar', 5, 'tag', '<?php  
$posttags = get\_the\_tags();  
if ($posttags) {  
  foreach($posttags as $tag) {  
    echo $tag->name . ',';  
  }  
}  
?>', 1]);  
 <?php endwhile; else: ?>  
 <?php endif; ?>  
<?php } else {?>  
<?php } ?>