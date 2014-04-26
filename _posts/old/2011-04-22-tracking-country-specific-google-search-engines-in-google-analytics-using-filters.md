---
title: 在谷歌分析中使用过滤器跟踪谷歌当地搜索引擎
author: 54jack
layout: post
permalink: /google-analytics/tracking-country-specific-google-search-engines-in-google-analytics-using-filters/
sina_t:
  - 'true'
views:
  - 1296
  - 1296
qq_t:
  - 'true'
duoshuo_thread_id:
  - 511796
yourls_shorturl:
  - http://t.xiaoq.in/5j
ta-thumbnail:
  - NoMediaFound
categories:
  - Google Analytics
tags:
  - 国家搜索引擎
  - 当地搜索
  - 本地搜索
  - 谷歌分析
  - 谷歌搜索
  - 过滤器
---
国际业务的开展决定了网站访问者的差异化，我们在日常网站优化及分析过程中就可能需要针对谷歌不同国家的域名进行细分和过滤，下文由<span class='wp_keywordlink'><a href="http://www.yeezhe.com/" title="译者" target="_blank">译者</a></span><span class='wp_keywordlink'><a href="https://xiaoq.in/" title="肖庆" target="_blank">肖庆</a></span>原创翻译，原文在<a title="谷歌分析跟踪本地搜索" href="http://derickng.com/posts/89-tracking-country-specific-google-search-engines-in-google-analytics-using-filters" target="_blank">这</a>，分离<span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="谷歌分析" target="_blank">谷歌分析</a></span><span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e6%9c%ac%e5%9c%b0%e6%90%9c%e7%b4%a2/" title="查看本地搜索中的全部文章" target="_blank">本地搜索</a></span>的方法很多，以下只是其中之一，可以把这种跟踪方法拓展到YAHOO,BING等。

Tracking additional search engines (see [1][1], [2][2] and [3][3]) in <span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span> is hardly a new thing. The usual method of adding additional search engines to be tracked would be to use the [_addOrganic()][4] function of the tracking code. While that works perfectly, I would like to propose a different way of achieving the same results using filters in Google Analytics.

在<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%b0%b7%e6%ad%8c%e5%88%86%e6%9e%90/" title="查看谷歌分析中的全部文章" target="_blank">谷歌分析</a></span>中跟踪额外的搜索引擎几乎不再是新鲜事了。增加额外要跟踪搜索引擎的通常做法是使用跟踪代码的_addOrganic()功能。尽管那运行完美，但是我们还是想推荐在<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%b0%b7%e6%ad%8c%e5%88%86%e6%9e%90/" title="查看谷歌分析中的全部文章" target="_blank">谷歌分析</a></span>中使用<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%bf%87%e6%bb%a4%e5%99%a8/" title="查看过滤器中的全部文章" target="_blank">过滤器</a></span>获得相同数据的不同方法。

The advantages of using filters:

使用<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%bf%87%e6%bb%a4%e5%99%a8/" title="查看过滤器中的全部文章" target="_blank">过滤器</a></span>的优点：

*   You can (and you should) create an additional profile with the same tracking ID to track country specific search engines while leaving the original profile for an overview. Calling [_addOrganic()][4] will modify all the profiles with the same tracking ID.

你可以（而且应该）用同样的跟踪ID创建一个额外配置文件以跟踪特定<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%9b%bd%e5%ae%b6%e6%90%9c%e7%b4%a2%e5%bc%95%e6%93%8e/" title="查看国家搜索引擎中的全部文章" target="_blank">国家搜索引擎</a></span>，同时保留原始数据供查看。调用_addOrganic()会修改相同跟踪ID的所有配置文件。

*   Visitors to your website do not have to load a long list of JavaScript code containing all the additional search engines you want to track therefore reducing some (minimal) load time.

网站访问者不必被迫先加载一长串包含所有想跟踪的额外搜索引擎的JavaScript代码，从而减少了一些（细微的）加载时间

*   There should be no changes required even if Google deploys another search engine at www.google.new.tld. If you call [_addOrganic()][4] with a static list of search engine names, you will have to add and update your list of search engines to track.

即使谷歌在[www.google.new.tld][5]采纳了新的搜索引擎，你也新增不必做任何修改。如果你使用一个静态的搜索引擎列表来新增[_addOrganic()][4]，你将不得不在增加和更新要跟踪的搜索引擎列表。

This is an example of the steps required to track additional Google search engines using a single filter:

为了通过该单一过滤器跟踪额外的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%b0%b7%e6%ad%8c%e6%90%9c%e7%b4%a2/" title="查看谷歌搜索中的全部文章" target="_blank">谷歌搜索</a></span>引擎，下面是需要采取的步骤范例

*   Create an additional profile with the same tracking ID.使用同一个跟踪ID创建额外的配置文件。
*   Add a new filter with filter type as “Custom Filter” and choose “**Advanced**“.添加新的过滤器，过滤器类型为自定义过滤，选择高级。
*   Select “Campaign Source” under “Field A -> Extract A” and enter “**^google$**” as input.选择广告系列来源，在字段 A -> 提取 A后输入**^google$**
*   Select “Referral” under “Field B -> Extract B” and enter “**^http://www.(google.[^/]*)**” as input.在字段 B -> 提取 B中选择引荐链接，输入**^http://www.(google.[^/]*)**
*   Select “Campaign Source” under “Output To -> Constructor” and enter “**$B1**” as input.选择广告系列来源中选择输出至构建器并且输入**$B1**
*   Set “Field A Required” to “**Yes**“.字段A为必填
*   Set “Field B Required” to “**Yes**“.字段B为必填
*   Set “Override Output Field” to “**Yes**“.覆盖输出字段

太复杂？看图操作下就好了！

<img class="alignnone size-full wp-image-297" title="local google" src="http://cdn.54jack.com/images/2011/04/local-google.png" alt="" width="550" />

What this filter does is to check that the traffic source is one of Google’s search engines and thus extract the “**google.com.sg**” part from the referral field (usually something like “**http://www.google.com.sg/search?q=…**“) then show the search engine source as “**google.com.sg**“. Do take note that while this is an example for Google search engines, the same steps (with slightly different input) will work with other search engines.这个过滤器做的就是确认流量来源是否是Google各国搜索引擎之一，并从引荐网址中提取google.com.sg这部分（通常如 “**http://www.google.com.sg/search?q=…**“)。请注意上面尽管只是一个针对<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%b0%b7%e6%ad%8c%e6%90%9c%e7%b4%a2/" title="查看谷歌搜索中的全部文章" target="_blank">谷歌搜索</a></span>的方法，但也适用于其他搜索引擎，步骤也是一样的（需要做些细微差别的输入）

 [1]: http://www.antezeta.com/blog/google-analytics-search-engines
 [2]: http://www.seo-hongkong.com/blog/how-to-add-organic-search-engines-in-google-analytics-759.html
 [3]: http://www.advanced-web-metrics.com/blog/2008/09/14/customising-the-list-of-search-engines-in-google-analytics/
 [4]: http://code.google.com/apis/analytics/docs/gaJS/gaJSApiSearchEngines.html#_gat.GA_Tracker_._addOrganic
 [5]: http://www.google.new.tld