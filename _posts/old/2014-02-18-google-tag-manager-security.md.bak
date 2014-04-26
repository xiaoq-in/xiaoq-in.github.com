---
title: Google Tag Manager安全吗？
author: 肖庆
layout: post
permalink: /google-tag-manager/google-tag-manager-security/
ratings_users:
  - 1
ratings_score:
  - 5
ratings_average:
  - 5
views:
  - 245
ta-thumbnail:
  - https://xiaoq.in/cdn/2014/02/user-management.gif;
categories:
  - Google Tag Manager
tags:
  - GTM
  - 代码黑名单
  - 发布和版本
  - 安全
  - 用户权限
  - 隐私
  - 预览和调试
---
初次接触Google Tag Manager（<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/gtm/" title="查看GTM中的全部文章" target="_blank">GTM</a></span>）的人可能会对这个工具的强大而感叹，感叹之余，也不免担忧<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%ae%89%e5%85%a8/" title="查看安全中的全部文章" target="_blank">安全</a></span>问题：这个工具这么强大，我网站上面的任何信息都可以获取并存储在GA或者其他工具里面（这个猜测是确实成立的，请相信js/jquery的强大，以后我们再慢慢说），那多不<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%ae%89%e5%85%a8/" title="查看安全中的全部文章" target="_blank">安全</a></span>啊？！我的网站里面可是有很多的商业机密信息，比如客户信息，订单信息等。

其实，这种担忧未免有些过了。下面我们看看<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/gtm/" title="查看GTM中的全部文章" target="_blank">GTM</a></span>是如何为你的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%ae%89%e5%85%a8/" title="查看安全中的全部文章" target="_blank">安全</a></span>护航的。

<a title="用户和权限" href="https://support.google.com/tagmanager/answer/2695756?hl=zh-Hans&topic=2574304&ctx=topic" target="_blank">用户和权限</a>：在GTM中，有两个层级的权限管理，分别是账户层级和容器层级，默认都是最低的权限。其中账户级别分为两种权限：仅限查看（只读权限）；查看、修改和管理（管理员权限）。而容器层级则有以下四种权限：

*   **无访问权限**：用户将无法看到帐户中列出的容器。
*   **仅限查看**：用户可以看到列出的容器，而且可以浏览容器中的代码、规则和宏。
*   **查看和修改**：用户可在容器中添加和修改代码、规则和宏。
*   **查看、修改、删除和发布**：用户可以在容器中添加、修改和删除代码、规则和宏，还可以在实际网站上发布更改。

<img class="alignnone size-full wp-image-1584" alt="user-management" src="https://xiaoq.in/cdn/2014/02/user-management.gif" width="460" height="480" />

在实际工作中，我们可以给不同的人赋予不同的权限，其中“查看、修改和管理”用户的“查看、修改、删除和发布”权限是最高级别的，一般是给予代码部署人员，他对代码的部署最终负责，如果分析人员自己有能力可自己操作，如果不能自己独立完成，可以给相关人员（比如IT、代码部署工程师、技术人员）添加这个权限或者不放心的话可以设置上个等级的“查看和修改”，等他们添加好了再自己最终测试和发布。一旦部署完毕，立即回收相关权限，除非出现问题或者需要重新设置和部署再重新给他们权限，从而最大程度地保证代码和账户安全。

<a title="发布和版本" href="https://support.google.com/tagmanager/answer/2699097?hl=zh-Hans&topic=2574304&ctx=topic" target="_blank">发布和版本</a>：版本控制中的历史操作记录是你检查账户是否被人乱搞的强有力证据，有了这个我想应该没人敢乱搞的。每次修改、删除、新建等操作都会有操作记录，即便删除了某个容器也可以通过点击“显示删除项”来查看其中的设置。并且，删除在30天内是可以再恢复的：点击“显示删除项”进入删除的容器，右上角有个“取消删除”的按钮，点击即可。在删除后我们可以在头部看到这个提示：“已对容器版本 X 作删除标记。系统可能会在 30 天后将其永久删除。”

另外，任何代码或者规则、宏的保存之前，都会进行出错检查，如果代码存在错误，会提示你修改。这个机制可以避免你的代码出错从而影响网站的正常运行。

<a title="预览和调试" href="https://support.google.com/tagmanager/answer/2695660?hl=zh-Hans&ref_topic=3441532" target="_blank">预览和调试</a>：通过这个功能，我们可以在代码容器正式发布前进行<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e9%a2%84%e8%a7%88%e5%92%8c%e8%b0%83%e8%af%95/" title="查看预览和调试中的全部文章" target="_blank">预览和调试</a></span>，从而进一步避免数据出错。关于代码调试的具体方法后续我们再讲。当然，简单的调试的话看底部的提示框基本就可以了。如果配置了很多复杂逻辑的代码，我们则需要借助一些开发者工具（Chrome和火狐等浏览器内置支持）以及对相关参数的深入了解，细心和条理清晰在这种情形下也尤为重要，标点、空格、括号等低级出错往往会让你苦笑不已。

<a style="line-height: 1.5em;" title="代码黑名单" href="https://developers.google.com/tag-manager/devguide?home#security" target="_blank">代码黑名单</a><span style="line-height: 1.5em;">：通过在网站中加入类似下面的代码，可以通过白名单和（或）黑名单规则，确保某些代码能否被触发和执行。需求注意的一点是：黑名单规则覆盖白名单规则，同时如果两个规则之间存在依赖关系的class，上述覆盖规则同样适用。详细的介绍可以点击链接进入开发者中心查看。</span>

<pre>dataLayer = [{
  ...
  'gtm.whitelist': ['&lt;ID&gt;', '&lt;ID&gt;', ...]
  'gtm.blacklist': ['&lt;ID&gt;', '&lt;ID&gt;', '&lt;ID&gt;', ...]
}];</pre>

谷歌服务器的快速、稳定和安全性，应该无人质疑吧？嗯，对于代码管理工具（或者任何添加到网站的第三方代码）而言，这些是非常重要的，虽然并不起眼。

关于<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e9%9a%90%e7%a7%81/" title="查看隐私中的全部文章" target="_blank">隐私</a></span>问题，我们看下官方的介绍：<a>Google 跟踪代码管理器会收集数据吗？Google 将如何使用这些数据？</a>

Google 跟踪代码管理器是专为营销人员通过单个界面管理网站代码而提供的解决方案。代码管理器工具本身（用于部署代码）是一个不使用 Cookie 的域，不会收集任何个人身份信息。此工具会指示其他代码触发，而这些代码可能会收集数据。Google 跟踪代码管理器不会访问这些数据。如果用户在域或 Cookie 级别选择了停用，则他们使用 Google 跟踪代码管理器部署的所有跟踪代码都不会收集这些域或 Cookie 的数据。

我们可能会请求您允许我们与其他 Google 产品共享部分产品数据（例如您的帐户信息）以启用某些功能，比如让您更容易地添加新的 AdWords 转化跟踪代码。此外，我们的工程师还会定期审核有关产品使用情况的信息，以不断完善产品。但是，在未经您同意的情况下，我们绝不会与其他 Google 产品共享任何这些数据。

有关详细信息，请参阅我们的产品<a href="https://www.google.com/tagmanager/use-policy.html" target="_blank">使用政策</a>。

最后，我们看到他们有一个规划中的功能：代码触发报告，这个在很多商业代码管理工具中是有的，非常期待这个，可以更好地了解代码的执行情况。话说，京东都在用GTM了（如果你看到哪家大公司在用，欢迎留言），大型电商都在用，还有啥不放心的呢~