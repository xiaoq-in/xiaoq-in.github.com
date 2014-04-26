---
title: 新功能推介之Google Analytics的内容分组
author: 肖庆
layout: post
permalink: /google-analytics/content-grouping/
yourls_shorturl:
  - http://t.xiaoq.in/8a
ta-thumbnail:
  - https://xiaoq.in/cdn/2013/12/content-grouping.gif;
views:
  - 359
ratings_users:
  - 1
ratings_score:
  - 5
ratings_average:
  - 5
categories:
  - Google Analytics
tags:
  - 使用抽取规则分组
  - 使用规则定义分组
  - 内容分组
  - 按跟踪代码分组
  - 自定义报告
---
<span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%86%85%e5%ae%b9%e5%88%86%e7%bb%84/" title="查看内容分组中的全部文章" target="_blank">内容分组</a></span>出来已经有一段时间了（其实去年已经内测了，大概本月中旬公测并在GA的官方博客发布更新），这个<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%86%85%e5%ae%b9%e5%88%86%e7%bb%84/" title="查看内容分组中的全部文章" target="_blank">内容分组</a></span>到底有什么用，能给网站分析带来什么好处和便利呢，本文将做一个概况性总结。

首先，内容分组其实本身来说并没有什么太大的功能升级，在一定程度上可以说完全没有必要，因为自定义维度就可以实现类似的效果，并且自定义维度目前来说是可以作为次级维度来查看的。不过，自定义维度有数量限制（最多20个），而且用它来进行内容分组有点大材小用的味道。

在此前，我们一般使用虚拟页面跟踪对网址进行改写的方式生成规则的URL，从而在网页内容报告中形成层次清晰的数据结构，比如按照页面类型、域名、目录进行一个结构化处理，有点类似于SEO中的树形结构。当然，也有人使用事件跟踪，在这个应用场景下，这两种方式并不会有太多的差异，所不同的是事件跟踪方式不会影响原有的数据结构，当你希望对单个URL进行细分查看时，使用事件跟踪可以更方便地进行问题定位，因为虚拟页面跟踪往往会对一些重复的页面进行整合，常见的就是将带有不同查询字符串的页面进行整合。如果你需要进行这个层次的细分，并且数据量不是很大的话（额外的事件跟踪会消耗hits），最好使用事件跟踪。

以上说的，都是通过其他方式实现内容分组的效果，都是需要添加代码的，这些方式与新推出的内容分组中<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e6%8c%89%e8%b7%9f%e8%b8%aa%e4%bb%a3%e7%a0%81%e5%88%86%e7%bb%84/" title="查看按跟踪代码分组中的全部文章" target="_blank">按跟踪代码分组</a></span>，在实现方式上来说，其实并无太大差异，只是查看数据的地方不一样而已。内容分组的报告，目前来说，还只能在<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e6%8a%a5%e5%91%8a/" title="查看自定义报告中的全部文章" target="_blank">自定义报告</a></span>中查看，其他地方应该是暂时没有入口的。

当然，这并不是说内容分组就没有存在的必要性，它有三种分组方式，上面说到的跟踪代码分组，还有下面截图中看到的其他两种方式，分别是使用抽取规则和按规则定义进行分组。这其他的2个方式从本质上来说，也是属于一个大类的，不同的是按照规则定义是对抽取规则的一个升级，除了可以用正则表达式，也照顾到一些不懂的同学使用那些常见的筛选条件，另外也可以按照或/且的关系组合条件并且可以按照顺序进行组合。

GA的内容分组位于视图里面，在目标的标签下面，如图所示：

<img class="alignnone  wp-image-1492" alt="content grouping" src="https://xiaoq.in/cdn/2013/12/content-grouping.gif" width="600" />

在这里，正则表达式又出来了（正则表达式是使用GA高级功能必备的一个技能），当然也有其他的一些基本筛选条件，我们可以对网页的网址或网页标题（APP是屏幕名称）使用这些筛选条件，

内容分组也是有数量限制的，最多支持五个，因此我们在用的时候一定要做个长远规划，一旦将分组方式定下来就不要再改来改去了，中途的随意改动很容易会造成数据脱节或者混乱。如果实在不够用，可以做个变通，将多个规则进行组合，也方便后续二次细分。比如我这里使用的划分结构：首页；分类.某个分类；标签.某个标签；文章.某篇文章。这里仅提供一个思路，具体使用还是根据业务情况和具体需求进行规划。在GA的帮助中心也有很多的应用范例，有兴趣的可以去看下。

当我们对这些数据梳理完成之后，便可以创建<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e6%8a%a5%e5%91%8a/" title="查看自定义报告中的全部文章" target="_blank">自定义报告</a></span>来查看和分析这些数据了。只需要选择相应的内容分组维度，然后添加相应的指标便可以了，最好可以再用下过滤条件，因为在实际使用中，我们几乎是不可能对所有页面都照顾到的，很可能会有少量的(not set)，这些数据在一定程度上在这个报告中的分析意义并不大，我们需要排除它或者但是查看它的数据来了解哪些页面遗漏了，并进一步考察是否需要对这部分也标记一下或者影响不大的话直接忽略。

以上，便是Google Analytics最近推出的内容分组的一个简要介绍，如果你的网站内容非常丰富，存在上千个或以上的页面，并且目前的URL结构并不是那么清晰，那么建议你使用下这个功能，会给你的日常数据分析带来很大便利的。

&nbsp;

&nbsp;