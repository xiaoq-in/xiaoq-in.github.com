---
title: Google Analytics数据分析代码部署之Magento（一）
author: 肖庆
layout: post
permalink: /google-analytics/magento-google-analytics-implementation-1/
ratings_users:
  - 0
ratings_score:
  - 0
ratings_average:
  - 0
views:
  - 488
categories:
  - Google Analytics
  - Google Tag Manager
tags:
  - GA
  - Google Tag Manager
  - GTM
  - Magento
  - UA
  - Universal Analytics
  - 电子商务跟踪
  - 自定义维度
---
<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/magento/" title="查看Magento中的全部文章" target="_blank">Magento</a></span>是外贸B2C网站使用率最高的免费开源程序，本文讲述如何快速在<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/magento/" title="查看Magento中的全部文章" target="_blank">Magento</a></span>电子商务平台上部署<span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>跟踪代码，其中主要涉及到的有基础的流量跟踪、<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%94%b5%e5%ad%90%e5%95%86%e5%8a%a1%e8%b7%9f%e8%b8%aa/" title="查看电子商务跟踪中的全部文章" target="_blank">电子商务跟踪</a></span>、<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e7%bb%b4%e5%ba%a6/" title="查看自定义维度中的全部文章" target="_blank">自定义维度</a></span>指标跟踪、页面和商品浏览量跟踪等，由于全文比较长，大概分三个部分来写。另外，从现在开始我们的代码部署都将使用<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/google-tag-manager/" title="查看Google Tag Manager中的全部文章" target="_blank">Google Tag Manager</a></span>+<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/universal-analytics/" title="查看Universal Analytics中的全部文章" target="_blank">Universal Analytics</a></span>来完成，如果你还在用Google Analytics的旧版本的话，建议升级或新增一个<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ua/" title="查看UA中的全部文章" target="_blank">UA</a></span>版本的并行使用。

本文先说下其中的基础流量跟踪和<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%94%b5%e5%ad%90%e5%95%86%e5%8a%a1%e8%b7%9f%e8%b8%aa/" title="查看电子商务跟踪中的全部文章" target="_blank">电子商务跟踪</a></span>。

为了简化操作，并且尽可能地减少代码修改（否则后续升级维护的成本也很高，并且不利于批量生产），因此我们主要使用插件的形式安装<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/gtm/" title="查看GTM中的全部文章" target="_blank">GTM</a></span>，再在<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/gtm/" title="查看GTM中的全部文章" target="_blank">GTM</a></span>中配置相应的跟踪代码、规则和宏。

推荐使用这个<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/google-tag-manager/" title="查看Google Tag Manager中的全部文章" target="_blank">Google Tag Manager</a></span>插件，<a title="Google Tag Manager" href="http://www.magentocommerce.com/magento-connect/google-tag-manager-3.html" target="_blank">点击</a>进入官方网站查看如何安装，安装好了之后在下面这个地方设置，填写你的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/gtm/" title="查看GTM中的全部文章" target="_blank">GTM</a></span> ID，其他的建议全部勾选开启，后面我们通过<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e7%bb%b4%e5%ba%a6/" title="查看自定义维度中的全部文章" target="_blank">自定义维度</a></span>的方式来存储这些数据。

<img class="alignnone size-full wp-image-1617" alt="gtm-magento" src="https://xiaoq.in/cdn/2014/02/gtm-magento.gif" width="640" height="360" />

开启Data layer: Visitors之后，我们可以看到系统会自动生成一些参数，如：

<script>dataLayer = [{"visitorId":"3","visitorLoginState":"Logged in","visitorType":"General","visitorLifetimeValue":8448.85,"visitorExistingCustomer":"Yes"}];</script>

该行代码位于GTM的代码之前，因此也不需要我们额外配置gtm.dom那个规则。对于上述生成的这些数据，我们通过<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e7%bb%b4%e5%ba%a6/" title="查看自定义维度中的全部文章" target="_blank">自定义维度</a></span>来存储，其中visitorLoginState这个建议使用”访问“范围，其他的建议使用”用户”范围，如下图：

<img class="alignnone size-full wp-image-1618" alt="dimension-magento" src="https://xiaoq.in/cdn/2014/02/dimension-magento.gif" width="900" height="245" />

当然，如果你觉得这些数据并不够用或者并不是自己想要的话，可以对插件的代码进行修改来新增或修改需要跟踪的维度，需要记住的是<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ua/" title="查看UA中的全部文章" target="_blank">UA</a></span>的自定义维度最多支持20个，请注意这个限额。而如果你还在用<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>的自定义变量的话，那么仅有的5个自定义变量上面一下就消耗掉了，可以酌情进行删减。

修改代码的话，应该主要是看<a title="Magento_GoogleTagManager" href="https://github.com/CVM/Magento_GoogleTagManager/blob/master/app/code/community/CVM/GoogleTagManager/Block/Gtm.php" target="_blank">这个</a>文件。

上面我们还勾选了电子商务订单跟踪，勾选之后，会在订单成功页面生成订单相关的信息，我们只需要在GTM中额外添加一个代码并且使用一个规则，如下图所示：

<img class="alignnone  wp-image-1619" alt="gtm-ecommerce" src="https://xiaoq.in/cdn/2014/02/gtm-ecommerce.gif" width="600" /> <img class="alignnone size-full wp-image-1620" alt="order success" src="https://xiaoq.in/cdn/2014/02/order-success.gif" width="540" height="520" />

&nbsp;

对于基础流量代码，就比较简单了，只需要新建UA代码，同时按照上述索引号添加自定义维度的设置，规则设置为所有页面，保存。如下图所示：

<img class="alignnone size-full wp-image-1621" alt="magento-ua-1" src="https://xiaoq.in/cdn/2014/02/magento-ua-1.gif" width="1085" height="600" /> <img class="alignnone size-full wp-image-1622" alt="magento-ua-2" src="https://xiaoq.in/cdn/2014/02/magento-ua-2.gif" width="670" height="430" /> <img class="alignnone size-full wp-image-1623" alt="dimension micro" src="https://xiaoq.in/cdn/2014/02/dimension-micro.gif" width="570" height="615" /> <img class="alignnone size-full wp-image-1624" alt="uaid-micro" src="https://xiaoq.in/cdn/2014/02/uaid-micro.gif" width="400" height="420" />

&nbsp;

安装好代码之后，我们怎么来验证是否安装正确了呢？主要有4个方法：

1.  查看源文件，仔细核对代码是否正确，尤其注意大小写空格等问题。
2.  开启GTM的Debug模式，主要先打开预览模式更新之后再Debug，打开网站看底部浮层的代码加载触发提示。
3.  看实时报告。可以实时查看访问和目标转化等基础流量数据的变化。
4.  打开Chrome或者火狐的network查看collect文件的请求是否正常发送，各个参数的含义可以参照<a title="Measurement Protocol" href="https://developers.google.com/analytics/devguides/collection/protocol/v1/devguide?hl=zh-cn" target="_blank">这里</a>。

通过上述配置之后，我们就可以看到网站的流量数据、电子商务订单数据、访客相关的信息数据。这对于一般的公司来说，可能已经足够了，不过在接下来的两篇文章中，我们将再深入探索下我们还能进行一些什么深入挖掘，敬请期待~