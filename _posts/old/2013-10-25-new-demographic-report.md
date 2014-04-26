---
title: GA新增受众特征及兴趣报告，深度解析与应用
author: 肖庆
layout: post
permalink: /google-analytics/new-demographic-report/
yourls_shorturl:
  - http://t.xiaoq.in/80
ta-thumbnail:
  - http://blog.xiaoq.in/cdn/2013/10/geographic-customized-report.png;http://blog.xiaoq.in/cdn/2013/10/geographic-segmentation.png;
views:
  - 1223
ratings_users:
  - 1
ratings_score:
  - 5
ratings_average:
  - 5
categories:
  - Google Analytics
tags:
  - Google Tag Manager
  - 兴趣倾向
  - 兴趣类别
  - 再营销
  - 受众特征
  - 年龄
  - 性别
  - 自定义报告
  - 高级细分
---
<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>在近期新增了2个报告：<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%b9%b4%e9%be%84/" title="查看年龄中的全部文章" target="_blank">年龄</a></span>、<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e6%80%a7%e5%88%ab/" title="查看性别中的全部文章" target="_blank">性别</a></span>的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%8f%97%e4%bc%97%e7%89%b9%e5%be%81/" title="查看受众特征中的全部文章" target="_blank">受众特征</a></span>报告以及兴趣报告（含概览、倾向类别、其他类别），这给数据分析师提供了一个全新角度的分析维度，让我们更了解用户，并了解营销活动是否reach到了正确的目标受众。

这个数据基本只能通过具有一定规模的平台去获取，单个网站要获取这种信息十分困难，虽然我们可以通过对接会员系统来了解到我们的**会员**特征，但是获取到的数据也只是九牛一毛。目前来说，拥有这种数据的公司一般是：广告发布商，比如百度和淘宝都会有这种数据（为保护隐私等考虑，一般会通过聚合形式发布）。

Google Analytics的这个数据来源主要正是其庞大的内容广告网络（当然也包括其自身的用户资料、合作网站的用户资料等，如上所述，也都是以聚合形式展示）。其实，即便Google来说，它能获取到的数据也是有限的，因此你会看到：“总访问次数的48.41%（不同网站可能数字不尽相同，时间久点可能比例也会增加）”这种提示，不过只要占比不是太小，对我们数据分析影响还不是很大，毕竟我们主要看趋势罢了。

就目前来说，如果需要获取这种数据，就必须更新GA中的一行代码，即支持<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%86%8d%e8%90%a5%e9%94%80/" title="查看再营销中的全部文章" target="_blank">再营销</a></span>广告的那行，具体就是：

**ga.src = (&#8216;https:&#8217; == document.location.protocol ? &#8216;https://ssl&#8217; : &#8216;http://www&#8217;) + &#8216;.google-analytics.com/ga.js&#8217;;**

更改为：

**ga.src = (&#8216;https:&#8217; == document.location.protocol ? &#8216;https://&#8217; : &#8216;http://&#8217;) + &#8216;stats.g.doubleclick.net/dc.js&#8217;;**

另外，如果你使用<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/google-tag-manager/" title="查看Google Tag Manager中的全部文章" target="_blank">Google Tag Manager</a></span>的话，只需勾选支持展示广告的选项，然后发布新版本即可。

当你更新代码之后，可以进行代码验证：不过使用Google Tag Mangager检测不了；代码中含有注释也检测不了；代码通过外部文件引用也是检测不了（检测机制有待改进~）。如果你确认代码添加无误的话，直接跳过检测即可。过24小时左右，你就能看到数据了。（前提是有足够的数据量，低于规定阀值时候为了保护隐私不会显示出来，个人观察日访问次数大于五千应该够了）

在更新代码之后，你还需要在GA后头开启该功能，有2个入口，一个是在<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%8f%97%e4%bc%97%e7%89%b9%e5%be%81/" title="查看受众特征中的全部文章" target="_blank">受众特征</a></span>报告顶部开启，另外一个是在“网络媒体资源设置”中“启用受众特征和兴趣报告”。

官方的另外一个步骤是更新隐私条款，如果你之前就更新了代码应该已经更新了隐私条款。在一些隐私保护严格的国家，最好也更新一下吧。

UA版本并不支持上述功能，升级需谨慎，不过后续应该也会逐步支持吧。

通过上述操作，我们已经拥有了该项功能，并且可以看到数据了。（该功能目前正在测试中，因此你的账户如果没有看到上述设置，可能需要再等等了）下面，我们说说这些数据有什么用，怎么应用这些数据，为我们的营销活动服务。

首先，拿到这些数据，我们怎么看呢？当然是多维度组合然后比较哪些组合的效果最好了。在GA标准报告中，提供了一个比较的视图，通过这个视图，我们可以很清晰地了解到哪种组合的用户效果最好。比如45-54岁的女性，它的转化率最高。再结合访问次数看，我们就能找到哪些是我们需要改进的地方了。比如看到虽然上述转化率很好，但是访问数并不多，那么这个时候我们就需要加强这个组合用户的投放了。<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e6%80%a7%e5%88%ab/" title="查看性别中的全部文章" target="_blank">性别</a></span>、<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%b9%b4%e9%be%84/" title="查看年龄中的全部文章" target="_blank">年龄</a></span>的组合在<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-adwords/" title="Google Adwords" target="_blank">Google Adwords</a></span>中是标准的定位方式。当然，这只是一个示例，我们还可以组合去看兴趣列表。在GA的标准报告，这些数据是以层级关联的方式进行呈现的，并不支持次级维度，操作起来相对不便，并且不能进行多维度组合。不过，我们可以通过<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%87%aa%e5%ae%9a%e4%b9%89%e6%8a%a5%e5%91%8a/" title="查看自定义报告中的全部文章" target="_blank">自定义报告</a></span>（<a title="受众特征深入分析" href="https://www.google.com/analytics/web/template?uid=QU0yTQUQQdCZuugtfi80YA" target="_blank">这里共享一个自定义报告模板</a>）来实现，这个是支持的。如图所示：

<img class="alignnone  wp-image-1384" alt="geographic customized report" src="http://blog.xiaoq.in/cdn/2013/10/geographic-customized-report.png" width="600" />

其次，不得不说的就是<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e9%ab%98%e7%ba%a7%e7%bb%86%e5%88%86/" title="查看高级细分中的全部文章" target="_blank">高级细分</a></span>功能也支持这些数据的细分（可自由组合），基于上述比较数据和我们对业务的理解，我们可能希望细分出不同的用户来查看具体的表现，从而了解我们的营销活动是否得当，是否需要调整营销策略，营销效果如何，问题点在哪，如何改进，等等一系列的问题。细分，可以说是数据分析的灵魂，没有细分的数据基本是无意义的。以下是GA中的受众特征细分新增内容，大家可以根据具体情况建立一个或多个数据细分项。

<img class="alignnone  wp-image-1385" alt="geographic segmentation" src="http://blog.xiaoq.in/cdn/2013/10/geographic-segmentation.png" width="600" />

以上，我们已经知道了问题在哪里，怎么去改进或加强。还是在GA的后台，我们可以做另外一个操作，即<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%86%8d%e8%90%a5%e9%94%80/" title="查看再营销中的全部文章" target="_blank">再营销</a></span>。<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%86%8d%e8%90%a5%e9%94%80/" title="查看再营销中的全部文章" target="_blank">再营销</a></span>是支持对这些受众特征进行细分的。比如上面说到的，我们的目标受众是45-54岁的女性，不过目前量不过，那么我们可以通过建立这么一个再营销列表去进行加强，采取更高的出价和更具有针对性的广告语（图片/Flash）。当然，如果我们发现某些受众根本就不是我们需要的，我们可以进行排除这类老用户，当然直接在广告系列进行排除也是OK的。

<img class="alignnone  wp-image-1389" alt="demographic remarketing" src="http://blog.xiaoq.in/cdn/2013/10/demographic-remarketing.png" width="600" />

数据分析中非常重要并且容易被忽略的一个步骤就是测试。其实，在GA的内容实验中，我们也可以通过对受众特征进行细分去分析各个测试版本的更具体表现。比如，我们测试出来是A版本的效果更好，但如果对这个版本再结合去看受众特征报告，我们可能会发现，其中45-54岁的女性效果最好，并且大多数对时尚感兴趣。那么我们下次再做测试的时候，就可以将这些因素考虑进去，比如设计更符合这些受众口味的海报或广告语。

关于其中的数据维度，性别就是：男和女，标准报告中没有未知，不过在<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e9%ab%98%e7%ba%a7%e7%bb%86%e5%88%86/" title="查看高级细分中的全部文章" target="_blank">高级细分</a></span>中是有的。年龄按区段来划分，跟AdWords中的基本一致：18-24,25-34,35-44,45-54,55-64,65+，标准报告和<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e9%ab%98%e7%ba%a7%e7%bb%86%e5%88%86/" title="查看高级细分中的全部文章" target="_blank">高级细分</a></span>中均没有未知。<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%85%b4%e8%b6%a3%e5%80%be%e5%90%91/" title="查看兴趣倾向中的全部文章" target="_blank">兴趣倾向</a></span>和<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%85%b4%e8%b6%a3%e7%b1%bb%e5%88%ab/" title="查看兴趣类别中的全部文章" target="_blank">兴趣类别</a></span>与AdWords系统中应该是相同的。<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%85%b4%e8%b6%a3%e5%80%be%e5%90%91/" title="查看兴趣倾向中的全部文章" target="_blank">兴趣倾向</a></span>和<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e5%85%b4%e8%b6%a3%e7%b1%bb%e5%88%ab/" title="查看兴趣类别中的全部文章" target="_blank">兴趣类别</a></span>有什么区别？其实，从它的报告中URL名称来看，基本就了解了：兴趣倾向侧重于品牌广告，因为它的范围更大一些，在一定程度参照了电视广告的Reach，是对受众的长期行为习惯进行类推，侧重于某种生活方式；兴趣类别则主要基于历史和当前的网页浏览行为，范围更小，分类也稍微更细致一些。当然，我们也并不能说兴趣倾向就适用于品牌广告，而直效广告使用兴趣类别效果更好，实际还是需要测试才能发现，就个人使用情况来说，在广告预算充足大量投放的情况下，某些兴趣倾向的注册引入效果甚至更好。

ABC模式，是目前GA改版之后给我们的第一印象，其实这就是一种分析思路。当然，内容实验这一块，我始终认为应该单独开来，测试实验也是数据分析的重要一个步骤。

不测量，无法改进；不改进，没有意义。

细分是分析的灵魂，对比是基本的方法。

&nbsp;

&nbsp;