---
title: 使用Google Tag Manager设置GA的跨域跟踪
author: 肖庆
layout: post
permalink: /google-analytics/google-tag-manager-cross-domain-tracking/
ratings_users:
  - 0
ratings_score:
  - 0
ratings_average:
  - 0
views:
  - 13626
ta-thumbnail:
  - https://xiaoq.in/cdn/2014/01/cross-domains.gif;https://xiaoq.in/cdn/2014/01/uaid.gif;https://xiaoq.in/cdn/2014/01/cross-domain-rules.gif;https://xiaoq.in/cdn/2014/01/ua-tag.gif;https://xiaoq.in/cdn/2014/01/form-submit-tag.gif;https://xiaoq.in/cdn/2014/01/cross-domain-forms.gif;https://xiaoq.in/cdn/2014/01/show-domain.gif;https://xiaoq.in/cdn/2014/01/referral-exclusion-list.gif;
categories:
  - Google Analytics
tags:
  - ga 跨域
  - google analytics 跨域跟踪
  - google analytics跨域
  - Google Tag Manager
  - GTM
  - 表单跟踪
  - 跨域跟踪
  - 过滤器
---
<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%b7%a8%e5%9f%9f%e8%b7%9f%e8%b8%aa/" title="查看跨域跟踪中的全部文章" target="_blank">跨域跟踪</a></span>是数据分析中比较常见的一个问题，在如今很多公司都会有很多个网站并行运营，一方面可能是出于对SEO的考虑，另外一方面也可能是希望在搜索引擎推广中进行站群式广告推广。但是，这个问题也一直困扰着很多人，<span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>（包括升级版的Universal Analytics）中我们往往需要对**每个**需要进行跨域设置的链接或表单提交添加跟踪代码（当然更好的方式是通过jquery去寻找a标签或者form标签自动将参数附加进去），会比较麻烦，而且容易遗漏，维护起来也不太方便。

不过，如果你正在（或者准备）使用<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/google-tag-manager/" title="查看Google Tag Manager中的全部文章" target="_blank">Google Tag Manager</a></span>的话，这个设置将变得简单多了，首先来说的话是链接跨域只需要勾选一个true的选项（具体下文会提到）即可，而表单的话则通过一些宏和触发条件进行设置，而且最主要的是无需手动去修改网站内部的代码，不怕会有遗漏。

首先，我们需要设置需要<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%b7%a8%e5%9f%9f%e8%b7%9f%e8%b8%aa/" title="查看跨域跟踪中的全部文章" target="_blank">跨域跟踪</a></span>的所有域名，用逗号和空格隔开，有多少个加多少个。

<img class="alignnone size-full wp-image-1523" alt="cross domains" src="https://xiaoq.in/cdn/2014/01/cross-domains.gif" width="700" height="310" />

再次，我们将UA的ID设置为一个字符串，如果你每个网站用一个ID也可以添加多个（添加UA代码的时候需要再多设置一个触发条件触发相应的UAID代码执行），这里为了简化操作仅使用了一个ID。

<img class="alignnone size-full wp-image-1524" alt="uaid" src="https://xiaoq.in/cdn/2014/01/uaid.gif" width="600" height="310" />

第三步，设置表单提交的规则，第一个表示这个事件为事件提交，这个是<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/gtm/" title="查看GTM中的全部文章" target="_blank">GTM</a></span>的默认方式，具体需要了解可以查看帮助中心。URL即当前的网站URL，设置条件是不包括target.com；而element url则是目标URL，表示要跳转去到的URL，这里设置条件为包含target.com这个域名。整体来说这个规则就是：如果当前页面的URL中不包含target.com，且目标URL的中包含有target.com，同时这个事件是表单提交。同理，如果有多个其他域名，也可以类似方法添加。

<img class="alignnone size-full wp-image-1532" alt="cross domain rules" src="https://xiaoq.in/cdn/2014/01/cross-domain-rules.gif" width="600" height="340" />

第四步，我们添加一个UA的TAG（标签），其中跟踪ID使用我们上面设置的uaid宏，点击加号会自动提示出来选中即可；选中跟踪类型为Page View，Cookie Domain为auto，Auto Link Domains为刚才设置的cross domains宏（同理可以下拉选中），触发规则为所有页面，同时下拉勾选Allow Linker为True，其他保持默认即可。

<img class="alignnone size-full wp-image-1526" alt="ua tag" src="https://xiaoq.in/cdn/2014/01/ua-tag.gif" width="670" height="645" />

第五步，添加Form Submit的TAG，最好点选Wait For Tags，不然可能部分由于加载过快而无法跟踪到，延迟时间一般使用默认的即可，触发规则同样是所有页面。这个TAG的作用在于激活<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%a1%a8%e5%8d%95%e8%b7%9f%e8%b8%aa/" title="查看表单跟踪中的全部文章" target="_blank">表单跟踪</a></span>。

<img class="alignnone size-full wp-image-1527" alt="form submit tag" src="https://xiaoq.in/cdn/2014/01/form-submit-tag.gif" width="700" height="660" />

第六步，添加一个Decorate Form的UA跟踪TAG，其中跟踪ID使用上面设置的uaid宏，触发规则使用上面设置的表单提交规则，其他默认即可。

<img class="alignnone size-full wp-image-1528" alt="cross domain forms" src="https://xiaoq.in/cdn/2014/01/cross-domain-forms.gif" width="693" height="625" />

&nbsp;

上面，我们已经完成了在<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/gtm/" title="查看GTM中的全部文章" target="_blank">GTM</a></span>中的设置，只需要发布然后将代码加到各个跟踪网站的所有页面即可。

不过，为了更方便的查看和过滤数据，我们可以再设置一个<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%bf%87%e6%bb%a4%e5%99%a8/" title="查看过滤器中的全部文章" target="_blank">过滤器</a></span>，将主域名整合到URL中（GA默认是将域名作为主机名这样一个单独字段），<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%bf%87%e6%bb%a4%e5%99%a8/" title="查看过滤器中的全部文章" target="_blank">过滤器</a></span>如下图所示：

<img class="alignnone size-full wp-image-1533" alt="show domain" src="https://xiaoq.in/cdn/2014/01/show-domain.gif" width="950" height="530" />

&nbsp;

另外，为了防止发生自我引荐，我们需要在GA的后台设置需要忽略的引荐域名，即将你上述所有跟踪的域名添加到引荐URL的排除名单即可，系统默认是会自动添加当前设置的域名的，如下图所示：

<img class="alignnone size-full wp-image-1534" alt="referral exclusion list" src="https://xiaoq.in/cdn/2014/01/referral-exclusion-list.gif" width="890" height="293" />

好了，<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%b7%a8%e5%9f%9f%e8%b7%9f%e8%b8%aa/" title="查看跨域跟踪中的全部文章" target="_blank">跨域跟踪</a></span>就这么简单地搞定了！

你可以在<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/gtm/" title="查看GTM中的全部文章" target="_blank">GTM</a></span>中打开调试模式进行测试，成功了的话会提示说各个标记已经被触发了。

或者点击链接、提交表单的方式实际查看效果，如果你看的跳转后的URL中附加了一段类似这样的标记：&_ga=1.237288706.307133550.1388409869，说明跨域是成功了。

最后提醒下，最好可以将这个参数在robots.txt中进行排除以避免SEO的不利影响。