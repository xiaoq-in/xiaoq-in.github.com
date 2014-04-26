---
title: DCO广告优化进阶
author: 肖庆
layout: post
permalink: /google-adwords/dco-advanced-skills/
ratings_users:
  - 0
ratings_score:
  - 0
ratings_average:
  - 0
views:
  - 3032
yourls_shorturl:
  - http://t.xiaoq.in/w
ta-thumbnail:
  - http://blog.xiaoq.in/thumb/cache/2013/4/1135-1.png;
categories:
  - Google AdWords
tags:
  - DCO
---
前段时间比较忙，博客更新比较少，现在开始慢慢梳理这段时间尝试总结出来的一些广告优化技巧。刚好前几天有朋友问到<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/dco/" title="查看DCO中的全部文章" target="_blank">DCO</a></span>广告怎么去优化，那么在此再说下，希望能对各位玩<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-adwords/" title="Google Adwords" target="_blank">Google Adwords</a></span>的朋友有些帮助。

<img class="alignnone size-full wp-image-1136" alt="Napoleon-dynamite" src="http://blog.xiaoq.in/cdn/2013/04/Napoleon-dynamite.png" width="551" height="390" />

关于<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/dco/" title="查看DCO中的全部文章" target="_blank">DCO</a></span>，其实之前也写过一篇<a title="展示广告系列优化工具(DCO) 最佳实践" href="http://xiaoq.in/google-adwords/display-campaign-optimizer-dco/" target="_blank">展示广告系列优化工具(DCO) 最佳实践</a>，建议还未尝试的朋友先看下。<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/dco/" title="查看DCO中的全部文章" target="_blank">DCO</a></span>广告成功的一个关键是需要设置比较靠谱的转化目标，因为我们后续的一切优化都是基于转化数据的，如果设置不当或者数据量太小或者数据量太大。一般建议电商企业以支付跳转页面作为转化目标，如果刚起步一天的订单量很少的话也可以设置为添加到购物车。而品牌客户来说，一般是会以GA的一些目标会比较具有参考价值，如事件目标，每次访问页面，停留时间等。要做DCO首先要满足的一个条件是需要在过去30天有至少15次转化，因此以上目标的设置请根据实际业务情况进行设置。

一般大多数人的操作方式应该是，在设置中更改2个基本设置，就算开启了DCO，然后就自动让其优化。更进阶的一个方式是在原有30天内转化次数超过15次的广告系列中新建单独的2个广告，分别是文字广告和图片广告，然后逐步去暂停原有的广告组。第二种方式的一个优点是，我们可以抛弃各种复杂的广告组设置，实现真正意义的DCO，同时也能够逐步优化创意，而不至于因为广告组过多而产生各种迷乱。DCO的本质在于广告的优化由Google AdWords广告系统自动实现，一般是根据该广告系列的历史数据表现，它会去拓展更相关的用户群或展示位置，或者去以更高的出价去竞争转化最好的展示位置，在恰当的时间地点和情境之下（当然具体我们是无法得知的，这只是基本的工作原理，具体表现好坏还得看Google的机器学习能力和优化算法了）。

本文主要介绍第三种方式：通过复制新的广告系列来降低风险，同时提升转化量及提升转化率。基本操作流程如下：

1、找出账户内转化次数最多的广告系列（并确保已经达到开启DCO基本条件，暂且称作A系列），复制原A广告系列并新建一个广告系列（B系列）。

2、将A系列中的广告组设置较低出价（比如比原先的计划设置低10%的出价），新建2个广告组，一个文字一个图片（当然你也可以将图片按尺寸再分组），不设置任何定位和排除过滤等。开启改系列的DCO设置。

3、同时开启A和B两个系列。观察数据表现，你应该会发现A系列中的出价低广告组的展现机会将会逐步降低，并逐步转移到B系列中去，理想状态应该是在一段时间后达到A系列之前的表现（含质和量），当达到这个状态时候，你就可以很自信地去暂停A系列中之前的那些广告组了。同时你会发现，A系列中的DCO广告也会达到一个比较好的表现。

接下来的话，DCO广告系列中，你主要的操作将是出价调整了。当然，如果在掌握足够的数据量之后，你也可以去尝试一些排除或做其他设定了，不过个人并不建议你将个别表现好的网站或者看起来并不相关但转化好的网站单独拿去做展示位置定位。因为用户完成转化并不一定仅由展示位置决定的，可能与当时用户的地理位置、时段、历史浏览记录和访问习惯有关。比如，你看到一个用户的转化来自于一个域名停放页面，你会去设置单独的网站定位么？或者你看到一个用户从某新闻网站某个频道的首页（超大流量）过来完成了订单，你就能说这个网站一定好么，即便是好的，你能做那么广泛的广告定位么？基本上，很难。当然，如果你想最终检验下，也是可以做些尝试的。

另外，关于DCO的几个温馨提示：

1.  建议DCO用于考核单一转化步骤的帐户。
2.  DCO适用于PC和wap端，不适合于推广app.
3.  请给DCO和CO最初设置略高于历史平均CPA的出价，否则会降低流量.
4.  即使开启了DCO和CO的系列，仍然需要定期进行网站优化.

最后，分享一个Google Display广告的一个内部优化工具，叫做KCT优化工具（通过Excel宏来优化），猛击<a title="https://sites.google.com/site/kwoptimizationtool/download" href="https://sites.google.com/site/kwoptimizationtool/download" target="_blank">这里</a>下载（需FQ，你懂的），好用不好用，试了就知道，以上仅供参考。

参考文章：http://www.ppchero.com/i-dare-you-to-try-out-the-dco/