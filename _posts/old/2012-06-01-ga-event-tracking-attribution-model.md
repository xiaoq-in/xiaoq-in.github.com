---
title: 使用GA自定义变量建立归因模型
author: 肖庆
layout: post
permalink: /google-analytics/ga-event-tracking-attribution-model/
sina_t:
  - 'true'
ratings_users:
  - 2
ratings_score:
  - 10
ratings_average:
  - 5
views:
  - 3603
yourls_shorturl:
  - http://g.xiaoq.in/9
ta-thumbnail:
  - http://blog.xiaoq.in/thumb/cache/2012/6/795-1.gif;
categories:
  - Google Analytics
tags:
  - Google Analytics Premium
  - 大数据
  - 归因模型
  - 自定义变量
---
今天研究<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%bd%92%e5%9b%a0%e6%a8%a1%e5%9e%8b/" title="查看归因模型中的全部文章" target="_blank">归因模型</a></span>，看了很多资料，综合对比发现，对<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%bd%92%e5%9b%a0%e6%a8%a1%e5%9e%8b/" title="查看归因模型中的全部文章" target="_blank">归因模型</a></span>的处理，有多种方法，最复杂莫过于LunaMetrics所介绍的使用Excel处理GA中导出来的数据，这个<a title="Multi-Channel Attribution Modeling – the Tool To Get You Started" href="http://www.lunametrics.com/blog/2012/05/17/multichannel-attribution-modeling-tool/" target="_blank">归因模型处理工具</a>使用了大量的高级函数，通过实际使用来看，发现这个表格还是存在一些问题，只能查看first touch（暂且译作“首次来源”）带来的转化。LunaMetrics在此之前还介绍了一个<a title="Attribution Modeling Without Google Analytics Premium" href="http://www.lunametrics.com/blog/2012/05/10/attribution-modeling-google-analytics/" target="_blank">相对简单的方法</a>，同样是使用Excel处理GA导出来的数据，但是同样非常麻烦。

<img class="alignnone size-full wp-image-796" title="attribution-model" src="http://xiaoq.in/g/pics/2012/06/attribution-model.gif" alt="" width="470" height="170" />

之后看到有一个方法，是通过<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>来实现，觉得非常不错的一个解决方案。大概思路就是使用访客级的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>记录用户的来源信息，存入到相应的字段中，然后再对应转化数据。

其实，这个方法个人曾经用过，呈现出来的数据很清晰，每个会员的来源/媒介/关键词/广告系列等信息都有了，其他的基本数据，如跳出率，停留时间，访问页数等也有了，然后转化数据和电子商务数据也都有。这样的话，你需要做的只是把这些数据加上时间维度导出来（因为用户的来源很多），加上时间维度，就基本可以区分每个用户在什么时间完成了转化，转化前后的相关数据。如果你希望获得更准确的数据，再通过会员ID与你的订单进行对接，这样，一个完美的会员来源及其对应转化的报表就出来了！

另外，如果只想跟踪首次来源带来的转化，那么你还可以通过js判断cookie中utma_的最后一组数据，如果是1的话，那么就使用自定义变量，不是的话就不使用了。如：253306240.421363226.1334163611.1334163611.1334163611**.1**

使用的函数大概如下：

<pre>//This function extracts the "_utma string" from the browser's cookies set by Google Analytics
function get_utma(l,n,s) 
{
	if (!l || l=="" || !n || n=="" || !s || s=="") return "-";
	var i,i2,i3,c="-";
	i=l.indexOf(n);
	i3=n.indexOf("=")+1;

	if (i &gt; -1) 
	{
	i2=l.indexOf(s,i); 
		if (i2 &lt; 0) 
		{ 
		i2=l.length; 
		}
	c=l.substring((i+i3),i2);
	}
return c;
}

//This function extracts the "visit count" value from the _utma cookie
function get_visit_count(str) 
{
var i = str.lastIndexOf(".");
i++;
var vc = str.substring(i);
return vc;
}</pre>

<pre>本文只是提供思路，暂时还没有完整的代码！有兴趣的童鞋可以自己去尝试下。</pre>

<pre>技术牛人：代码写法可参照：</pre>

<pre><a href="http://www.e-nor.com/e-nor-tracking-code.js">http://www.e-nor.com/e-nor-tracking-code.js</a></pre>

<pre><a href="http://weblog.scanyours.com/2010/06/23/multi-touch-conversion-tracking-with-google-analytics-part-3-implementation/">http://weblog.scanyours.com/2010/06/23/multi-touch-conversion-tracking-with-google-analytics-part-3-implementation/</a>（还可以记录转化时长）</pre>

<pre><a href="http://www.distilled.net/blog/seo/first-touch-tracking-in-google-analytics/">http://www.distilled.net/blog/seo/first-touch-tracking-in-google-analytics/</a></pre>

<pre>（可以记录引荐来源，对URL进行反编码）</pre>

<pre></pre>

<pre>当然，除了使用上面的一些思路，你还可以通过提取cookie值（和/或IP）对访客进行识别，再结合自定义变量，这样的话，访客在站内的转化数据和来源数据将可以进行对接，如果再配合使用timestamp参数，你还可以知道用户的转化耗时。这些值其实都可以通过js在cookie中获取到。</pre>

<pre>请注意：对个人信息进行跟踪是违反Google隐私政策的，因此请谨慎测试或使用！</pre>

<pre>归因模型，使用免费工具还是比较麻烦的，如果你们真的需要做到如此细致，技术也不是那么强大或者没有太多时间进行大数据的处理，选择商业版本的数据分析工具，如Google Analytics Premium，或许会让你更轻松些~</pre>

<pre></pre>