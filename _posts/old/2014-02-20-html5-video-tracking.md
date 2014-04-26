---
title: Google Analytics之HTML 5 视频跟踪
author: 肖庆
layout: post
permalink: /google-analytics/html5-video-tracking/
ratings_users:
  - 1
ratings_score:
  - 5
ratings_average:
  - 5
views:
  - 239
ta-thumbnail:
  - http://blog.xiaoq.in/cdn/2014/02/html5-video-tracking.gif;http://blog.xiaoq.in/cdn/2014/02/gtm-html5-video-tracking.gif;http://blog.xiaoq.in/cdn/2014/02/event-tracking-html5-video.gif;
categories:
  - Google Analytics
tags:
  - GA
  - GTM
  - HTML 5
  - UA
  - 事件跟踪
  - 视频跟踪
---
本文讲述如何通过<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>来监测<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/html-5/" title="查看HTML 5中的全部文章" target="_blank">HTML 5</a></span>视频，并提供<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ua/" title="查看UA中的全部文章" target="_blank">UA</a></span>、<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>、<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/gtm/" title="查看GTM中的全部文章" target="_blank">GTM</a></span>的三种现成代码，如果不想听我啰嗦，或者对技术不感兴趣，请直接点击<a title="html5-video-tracking" href="https://gist.github.com/xiaoq-in/9093428#file-html5-video-tracking" target="_blank">这里</a>，查看跟踪代码。这里是<a title="html5 video tracking" href="http://xiaoq.in/demo/video.html" target="_blank">demo</a>，可以点击查看效果演示。

<a title="HTML5的视频格式之争" href="http://www.ruanyifeng.com/blog/2010/05/html5_codec_fight.html" target="_blank">HTML 5支持直接播放视频</a>，无需安装插件，是目前非常流行的一项技术，特别是在视频网站和移动网站中被广泛使用。随着网络技术的不断发展、浏览器的版本功能升级，<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/html-5/" title="查看HTML 5中的全部文章" target="_blank">HTML 5</a></span>的市场占有率在一路攀升，<a title="Roughly 80% of the market now supports HTML5 video" href="http://www.jwplayer.com/html5/#html5_marketshare" target="_blank">报告</a>显示，目前已经大概有80%的浏览器支持HTML 5，而<a title="《HTML5 视频的现状》报告指出：目前市场上74%的浏览器都支持HTML5视频" href="http://www.36kr.com/p/101646.html" target="_blank">在2012年1月份才只有66%</a>。

我们看到越来越多的网站都会使用视频来宣传产品、品牌或者服务，视频的鼓动力还是非常大的！如果没有尝试过，是时候了。

下面来解释下这个代码的原理和使用方法： 基本手段就是使用<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>。加上代码之后，我们可以通过以下方法来查看是否正确运行了。或者查看实时报告中的事件报告。

<img class="alignnone  wp-image-1591" style="line-height: 1.5em;" alt="html5 video tracking" src="http://blog.xiaoq.in/cdn/2014/02/html5-video-tracking.gif" width="600" />

我们可以看到其中，事件类别统一为：video；事件操作为播放、暂停、播放进度（0%、25%、50%、75%、100%）、播放完成。这里一个完整的正常播放会产生八次请求，即播放完成后也会产生一次暂停操作；事件标签则是当前视频的URL；事件价值和是否为非互动都没有设置，即使用的默认值（无价值、非互动）。

如果对HTML 5技术有了解或者希望做一些调整优化的话，可以参考这个文档：<a title="HTML 5 视频/音频参考手册" href="http://www.w3school.com.cn/html5/html5_ref_audio_video_dom.asp" target="_blank">HTML 5 视频/音频参考手册</a>。 这个代码默认使用的Universal Analytics（<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ua/" title="查看UA中的全部文章" target="_blank">UA</a></span>）的版本，如果你想使用Google Analytics（<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>）的版本，将<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>的代码调整下注释位置即可，比如：

<div id="file-html5-video-tracking-LC24">
  //_gaq.push(['_trackEvent', 'video', 'Play', e['target']['currentSrc'] ]);
</div>

<div id="file-html5-video-tracking-LC25">
  ga(&#8216;send&#8217;,&#8217;event&#8217;, &#8216;video&#8217;, &#8216;Play&#8217;, e['target']['currentSrc']);
</div>

<div>
  改成
</div>

<div>
  <div id="file-html5-video-tracking-LC24">
    _gaq.push(['_trackEvent', 'video', 'Play', e['target']['currentSrc'] ]);
  </div>
  
  <div id="file-html5-video-tracking-LC25">
    //ga(&#8216;send&#8217;,&#8217;event&#8217;, &#8216;video&#8217;, &#8216;Play&#8217;, e['target']['currentSrc']);
  </div>
  
  <div>
  </div>
  
  <div>
    如果你使用Google Tag Manager（<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/gtm/" title="查看GTM中的全部文章" target="_blank">GTM</a></span>）来管理代码，则可以通过添加“自定义HTML代码”的方式新建代码代码，保存，然后生成新的版本，发布。代码添加的操作界面如下：
  </div>
  
  <div>
  </div>
  
  <div>
    <img class="alignnone  wp-image-1592" alt="gtm-html5-video-tracking" src="http://blog.xiaoq.in/cdn/2014/02/gtm-html5-video-tracking.gif" width="600" />
  </div>
  
  <div>
  </div>
  
  <div>
  </div>
  
  <div>
    当然，你也可以使用定义宏的方式来进行添加，这里为了简单起见，就不麻烦了，感兴趣的童鞋可以尝试下。
  </div>
  
  <div>
  </div>
  
  <div>
    最终的报告显示在热门事件中，我们可以新建次级维度来组合查看哪些视频更受欢迎（或者使用自定义报告）。
  </div>
  
  <div>
  </div>
  
  <div>
    如果关注视频的关注度（点击率），则主要看唯一身份事件数，因为如上面所述，一个视频播放会产生多个事件。而如果希望了解某个视频的受欢迎程度（互动率也体现了一个用户对视频的兴趣度），则可以查看事件总数，特别是我们可以过滤出那些播放进度大于75%的事件操作，这往往是用户非常感兴趣的视频。
  </div>
  
  <div>
  </div>
  
  <div>
    另外，我们可以结合其他的相关维度来做我们感兴趣的数据分析，比如用户是从什么来源过来的，看完视频之后最终有没有完成订单或咨询等宏观转化。一般来说，播放进度低于25%的视频，用户对此可能并不感兴趣，这也是很多视频广告的基本考量标准。可以考虑下改进或更换视频了，或者思考下是否流量导入的人群是否为目标受众，等等。
  </div>
  
  <div>
  </div>
  
  <div>
    <img class="alignnone  wp-image-1593" alt="event-tracking-html5-video" src="http://blog.xiaoq.in/cdn/2014/02/event-tracking-html5-video.gif" width="600" />
  </div>
  
  <div>
  </div>
  
  <div>
    怎么样，这个报告是否很像你在AdWords后台中看到的YouTube视频广告报告，如果你曾经投放过AdWords的YouTube视频广告的话？如何监测网站中嵌入的YouTube视频呢？请听下回分解！
  </div>
  
  <div>
  </div>
</div>