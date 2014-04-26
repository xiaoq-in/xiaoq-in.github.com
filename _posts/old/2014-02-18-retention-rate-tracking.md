---
title: 如何用Google Analytics监测留存率
author: 肖庆
layout: post
permalink: /analytics/retention-rate-tracking/
ratings_users:
  - 2
ratings_score:
  - 10
ratings_average:
  - 5
views:
  - 315
ta-thumbnail:
  - http://blog.xiaoq.in/cdn/2014/02/retention-rate.gif;http://blog.xiaoq.in/cdn/2014/02/retention-custom-report.gif;
categories:
  - 数据分析
tags:
  - GA
  - GTM
  - UA
  - 留存
  - 留存率
  - 自定义变量
  - 自定义维度
---
从事过游戏行业的朋友应该都会对一个指标非常熟悉，那就是：<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%95%99%e5%ad%98%e7%8e%87/" title="查看留存率中的全部文章" target="_blank">留存率</a></span>。纵观游戏行业的数据报表，都会经常看到这个名词，同时各个APP的监测工具也都会有类似的标准报告（比如腾讯移动统计、百度移动统计、友盟等等）。但是，我们在大多数的网站分析工具中，几乎看不到<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%95%99%e5%ad%98%e7%8e%87/" title="查看留存率中的全部文章" target="_blank">留存率</a></span>的踪影。

<img class="alignnone  wp-image-1577" alt="retention rate" src="http://blog.xiaoq.in/cdn/2014/02/retention-rate.gif" width="600" />

<p style="text-align: center;">
  （截图来自<a title="留存率" href="http://mta.qq.com/mta/user/ctr_retention?app_id=1" target="_blank">腾讯移动分析</a>）
</p>

其实，即便对于Web Analytics（网站分析）来说，它也应该是一个非常重要的指标，相对于访问次数或者独立访客来说，<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%95%99%e5%ad%98/" title="查看留存中的全部文章" target="_blank">留存</a></span>率对于网站的运营更具指导意义，尤其在有会员机制的网站（比如电商网站）或者用户回访率比较高的网站（比如门户网站）。

在目前的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>标准报告中，我们也能看到一些<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%95%99%e5%ad%98/" title="查看留存中的全部文章" target="_blank">留存</a></span>的相关的身影，比如新老访客占比、频率和新近度、互动度等报告。然而，它们并不是真正意义上的基于用户，基本是基于访问或者访客（访客还存在复杂的去重机制，各个工具处理方式略有差异）。访客与用户之间会存在很大的差距，在这个多屏多设备多浏览器的时代，这已是不争的事实，想象一下你的上网经历。当然，对于APP来说，这种差距会很小，因为跟踪机制是基于设备ID这种基本不会变更的信息。

在这里，我们提供一个基本的跟踪思路，可以很轻松地生成所需要的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%95%99%e5%ad%98/" title="查看留存中的全部文章" target="_blank">留存</a></span>率报告，如果公司拥有一定的技术能力，也可以做一个简易的数据报告后台（对<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>的API有一定了解），从而很方便地随时查看相关数据。

这里，我们主要运用到<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>跟踪，详细的代码片段可以<a title="ga-custom" href="https://gist.github.com/xiaoq-in/cd79f704e8ae942bcf49#file-ga-custom" target="_blank">点击这个链接</a>查看，其中预留了<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e5%8f%98%e9%87%8f/" title="查看自定义变量中的全部文章" target="_blank">自定义变量</a></span>的第二个索引，你可以用它来定义会员ID，其中第一个自定义变量为访客ID，第三个自定义变量为首次访问时间，第四个自定义变量为首次浏览页面。你也可以根据实际需要进行适当的修改：比如把第四个改成首先访问来源媒介关键词等信息，第三个的时间格式稍微调整下（后面的过滤器正则表达式也需要相应调整），时间记录规则改成服务器端调用，从而避免用户跨屏造成的数据偏差。

上面的代码可以直接加入到网站的head区域，或者通过Google Tag Manager添加自定义HTML的方式添加。另外，上面的代码是基于<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>版本的，非<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ua/" title="查看UA中的全部文章" target="_blank">UA</a></span>的，你也可以改成<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ua/" title="查看UA中的全部文章" target="_blank">UA</a></span>的版本，查看<a title="gtm-cid" href="https://gist.github.com/xiaoq-in/9049259#file-gtm-cid" target="_blank">访客ID的宏</a>。其他两个可参照来写。首次访问的基本逻辑就是，如果用户是第一次访问网站，则根据当前时间创建一个<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e7%bb%b4%e5%ba%a6/" title="查看自定义维度中的全部文章" target="_blank">自定义维度</a></span>，否则查找cookie中记录的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e7%bb%b4%e5%ba%a6/" title="查看自定义维度中的全部文章" target="_blank">自定义维度</a></span>，通过<a title="getAll" href="https://developers.google.com/analytics/devguides/collection/analyticsjs/method-reference" target="_blank">getAll函数</a>。

安装好代码之后，我们可以在自定义变量3的标准报告中查看数据，或者根据需要建立自定义报告，如下（这里隐去了上面的图表，请选择右上角的时间段查看数据变化）：

<img class="alignnone size-full wp-image-1578" alt="retention-custom-report" src="http://blog.xiaoq.in/cdn/2014/02/retention-custom-report.gif" width="1350" height="450" />

直观地看这个表，其实与我们期望的留存率报告还是有些差距。为了方便起见，我们可以建立一些常用的高级细分（使用正则表达式），比如细分出2014年2月份每周的数据，即首次访问网站的访客（用户）是在什么时间区间进入网站的，这些分别代表2014年Y2014M2.\*W1；Y2014M2.\*W2；Y2014M2.\*W3；Y2014M2.\*W4。然后再选择时间周期为2月份整个月，同时选择按周查看数据，再使用绘制选定行功能，即可从图表曲线图直观地了解到每个周期内的用户后续表现。日留存也可进行类似的操作。

如果在界面操作麻烦的话，可以下载到Excel进行处理，或者借助GA的API制作一个专门的数据报表后台，可以参照第一张图的显示效果和逻辑进行编程，也并不复杂。如果业务复杂并且庞大，搭建这么一个数据平台是非常值得的，我们可能需要整合更多的数据，比如最终的付费、线上与线下的数据整合等。

到这里你会说高级细分不是已经默认支持这种层级的细分么？是的，升级后的高级细分可以按照时间段来进行细分，同时也可以按照访客来进行细分，两个条件进行组合基本可以实现上述要求。不过，高级细分的最小时间粒度是天，并且它是基于访客的（准确来说是基于同一个设备的同一个浏览器且当前浏览器未进行过清空cookie等操作，距离最后一次访问在2年有效期内），同时如果你想查看日留存的报告，得为每一天建立一个高级细分，这是何其的麻烦，同时一次性加入太多的高级细分一方面会很慢，另外图表看起来也很混乱，并且第一列并不是我们一般留存率报告的时间维度。

总之，借助高级细分功能，我们可以在界面内进行简单快速的数据分析，但是对于制作日常报表来说，尤其是基于用户的报表来说，可能会显得捉襟见肘了。

通过使用自定义变量或者UA版本的自定义维度，主要是为我们的数据细分提供了更多发挥和想象空间，也创造了一定的灵活性和便利性。