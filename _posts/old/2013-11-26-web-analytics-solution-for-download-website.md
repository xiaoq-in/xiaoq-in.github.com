---
title: 数据分析解决方案之：下载类网站
author: 肖庆
layout: post
permalink: /analytics/web-analytics-solution-for-download-website/
yourls_shorturl:
  - http://t.xiaoq.in/88
ta-thumbnail:
  - https://xiaoq.in/cdn/2013/11/element-micros1.gif;https://xiaoq.in/cdn/2013/11/event-tracking-with-id-class.gif;https://xiaoq.in/cdn/2013/11/outbound-link-click-listener1.gif;https://xiaoq.in/cdn/2013/11/link-click-listener.gif;https://xiaoq.in/cdn/2013/11/top-events.gif;https://xiaoq.in/cdn/2013/11/gtm-clientid.gif;https://xiaoq.in/cdn/2013/11/gtm-ip.gif;https://xiaoq.in/cdn/2013/11/ua-custom-dimensions2.gif;https://xiaoq.in/cdn/2013/11/gtm-custom-dimensions.gif;https://xiaoq.in/cdn/2013/11/clientid-ip.gif;
views:
  - 646
ratings_users:
  - 1
ratings_score:
  - 5
ratings_average:
  - 5
categories:
  - 数据分析
tags:
  - GA
  - Google Analytics
  - Google Tag Manager
  - GTM
  - UA
  - Universal Analytics
  - 下载站
  - 下载网站
  - 事件跟踪
  - 宏
  - 数据分析解决方案
  - 规则
---
软件<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e4%b8%8b%e8%bd%bd%e7%ab%99/" title="查看下载站中的全部文章" target="_blank">下载站</a></span>恐怕是这个网络世界除了视频和音乐之外最占资源的网站，软件站在很大意义上来说，甚至相当于一个搜索引擎，因此有人会去刷榜单。本文将就软件<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e4%b8%8b%e8%bd%bd%e7%ab%99/" title="查看下载站中的全部文章" target="_blank">下载站</a></span>的跟踪方法和数据分析部署做个简要探索，仅供资源下载的网站做个参考，从而更方便地指引网站运营。

本文将以<a title="天空下载站" href="http://www.skycn.com/" target="_blank">天空下载站</a>为示例（仅作为例子，本人与之无任何关联），主要使用<a title="Google Analytics" href="http://www.google.com/analytics/" target="_blank">Google Analytics</a>（使用其<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ua/" title="查看UA中的全部文章" target="_blank">UA</a></span>版本，<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>版本同理，不再累赘）和<a title="Google Tag Manager" href="https://www.google.com/tagmanager/" target="_blank">Google Tag Manager</a>（<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/gtm/" title="查看GTM中的全部文章" target="_blank">GTM</a></span>）这2个免费的工具。

首先，我们确定网站分析的主要目标：

1.  了解各个软件的下载情况，页面浏览情况，软件下载的转化率。
2.  了解软件下载的具体位置（这里特指站内的位置，具体指各个按钮、链接、快捷入口）。
3.  了解不同分类下的软件下载榜单（其中最好能识别一些基本的刷榜作弊行为）。
4.  了解一个用户在生命周期内下载的软件数量、具体下载的软件是哪些。
5.  站内搜索、翻页等行为。
6.  站内广告展示点击监测。
7.  来源监测、其他基础性数据指标监测。

这里，我们分步来实现具体的数据跟踪：

1.第一个使用<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>，应该是没有人会觉得不妥吧。不过，这里为了简化代码添加，并且方便后期维护，我们使用<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/gtm/" title="查看GTM中的全部文章" target="_blank">GTM</a></span>的内置<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%ae%8f/" title="查看宏中的全部文章" target="_blank">宏</a></span>来完成。Justin在他的<a title="Bye Bye JavaScript! Auto Event Tracking with Google Tag Manager" href="http://cutroni.com/blog/2013/10/07/auto-event-tracking-with-google-tag-manager/" target="_blank">这篇博客文章</a>中，对这个方式进行了具体的阐述。简单来说，GTM目前可以实现对点击事件的智能化识别。

大家切换到“<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%ae%8f/" title="查看宏中的全部文章" target="_blank">宏</a></span>”这个菜单中，可以看到（其中括号内为对应的具体参数值，这里用&#8221;XXX&#8221;表示）：element（href=&#8221;XXX&#8221;）、element url（href=“XXX”）、element class（class=&#8221;XXX&#8221;）、element id（id=“XXX”）、element target（target=&#8221;XXX&#8221;），然后还有event等，如下图：

<img class="alignnone size-full wp-image-1456" alt="element micros" src="https://xiaoq.in/cdn/2013/11/element-micros1.gif" width="300" height="240" />

比如，对于这种下载链接：<a href=&#8221;http://download.skycn.com/hao123-soft-online-bcs/soft/Q/QQ2013Beta5.exe&#8221; target=&#8221;_blank&#8221; id=&#8221;chat&#8221; class=&#8221;qq&#8221;>下载</a>，我们可以设置如下的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>标签：

<img class="alignnone size-full wp-image-1457" alt="event tracking with id class" src="https://xiaoq.in/cdn/2013/11/event-tracking-with-id-class.gif" width="680" height="660" />

我们看到下面，还设置了两个代码触发<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%a7%84%e5%88%99/" title="查看规则中的全部文章" target="_blank">规则</a></span>：第一个是为了避免因为加载顺序而造成代码未加载用户就已经完成某个动作，造成跟踪数据丢失，尤其是如果你的事件在GTM代码之后，就一定得加上这个。

另外一个是外部链接的触发<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%a7%84%e5%88%99/" title="查看规则中的全部文章" target="_blank">规则</a></span>。其中{{event}}=gtm.linkClick，另外一个规则可以根据你的文件格式设置，比如软件的文件格式均为exe，则设置为：{{element url}} 包含exe，如下图所示：当然，我们也可以分开建立2个规则，一个是第一行的，另外文件格式的根据具体需要单独再设置，然后在Tag中添加对应的规则组合。

<img class="alignnone size-full wp-image-1470" alt="outbound link click listener" src="https://xiaoq.in/cdn/2013/11/outbound-link-click-listener2.gif" width="560" height="250" />

添加<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e4%ba%8b%e4%bb%b6%e8%b7%9f%e8%b8%aa/" title="查看事件跟踪中的全部文章" target="_blank">事件跟踪</a></span>，我们还需要设置如下这个基本的标签，这个标签告诉GTM启动点击链接跟踪，同时为了避免由于点击打开过快而造成跟踪丢失，这里加上一个两千毫秒（2秒）的延迟，等待所有代码都执行完之后再打开链接（下载链接的打开前加2秒对于用户是几乎无影响的），标签具体设置如下图：

<img class="alignnone size-full wp-image-1459" alt="link click listener" src="https://xiaoq.in/cdn/2013/11/link-click-listener.gif" width="620" height="560" />

以上设置好了之后，我们就可以在热门事件中查看到相应软件及类别的下载数据（包括去重的独立事件数，即以访问会话为计数范围的不重复的下载数），如下图：

<img class="alignnone size-full wp-image-1460" alt="top events" src="https://xiaoq.in/cdn/2013/11/top-events.gif" width="670" height="190" />

下面，我们来跟踪独立用户。我们知道universal analytics中有一个叫做clientId的参数，这个也是主要区别于<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>的东西。虽然我们可以通过查看访客对应的数据来了解总体的下载情况。但是，对于个体用户的分析，默认他是不支持的，这里我们就需要用到其中的自定义维度了。由于大多数用户下载软件其实并不会进行登录操作的，因此我们只能记录它的clientId，通过这个值来判定是否归属于某个具体的用户（当然这离具体的数据还是有些差距，再新增一个IP值的维度可以一定程度减少这种误差）。

具体需要进行以下设置：

&nbsp;

<img class="alignnone size-full wp-image-1465" alt="gtm clientid" src="https://xiaoq.in/cdn/2013/11/gtm-clientid.gif" width="695" height="465" />

通过宏定义clientId

<img class="alignnone size-full wp-image-1466" alt="gtm ip" src="https://xiaoq.in/cdn/2013/11/gtm-ip.gif" width="640" height="485" />

通过datalayer定义IP

<img alt="ua custom dimensions" src="https://xiaoq.in/cdn/2013/11/ua-custom-dimensions2.gif" width="645" height="150" />

在<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ua/" title="查看UA中的全部文章" target="_blank">UA</a></span>中设置上述2个维度

<img alt="gtm custom dimensions" src="https://xiaoq.in/cdn/2013/11/gtm-custom-dimensions.gif" width="680" height="440" />

在<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ua/" title="查看UA中的全部文章" target="_blank">UA</a></span>代码中新增自定义维度，1和2分别对应UA中的索引号，后面的维度对应上述定义的值，用{{}}括起来。

最终，在<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>的报告中，我们就可以看到这样的数据了。

<img class="alignnone size-full wp-image-1467" alt="clientid ip" src="https://xiaoq.in/cdn/2013/11/clientid-ip.gif" width="515" height="485" />

到这里，看起来或许会非常复杂，但是当你使用了之后，会发现其实会非常方便和简单，比如你不用再去给每个文件下载链接加上事件跟踪代码，然后相对于单独加事件跟踪代码，你也可以省去定义类别和名称，直接调用id或class即可，或者再简单点通过jquery函数动态读取面包屑的内容。这种代码部署方式，对于后期维护和保证数据完整性非常好的。

当代码部署完之后，你需要做的只是去设置几个自定义报表，然后所有想要的数据都信手拈来。

至于上面还说到的站内搜索跟踪、站内广告跟踪等，这些留给读者自己了，相对简单很多。

另外，看完上面的事件跟踪设置规则及方法，不知道你是否想到，其实对于下载链接这种之前根本无法添加AdWords转化跟踪代码的事件（一般是需要再做一个跳转页面），我们也可以将这种规则应用到相应的转化跟踪代码。

当你理解并完成了这些设置之后，你一定会喜欢上<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/google-tag-manager/" title="查看Google Tag Manager中的全部文章" target="_blank">Google Tag Manager</a></span>的，至少对于我来说，我已经慢慢习惯了它的这种简洁方便、逻辑思维、以及高度扩展和自定义。

&nbsp;