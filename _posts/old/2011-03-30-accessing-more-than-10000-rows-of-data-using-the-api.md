---
title: 通过API获取超过一万行数据
author: 54jack
layout: post
permalink: /google-analytics/accessing-more-than-10000-rows-of-data-using-the-api/
sina_t:
  - 'true'
views:
  - 817
  - 817
qq_t:
  - 'true'
duoshuo_thread_id:
  - 511773
yourls_shorturl:
  - http://t.xiaoq.in/6h
ta-thumbnail:
  - NoMediaFound
categories:
  - Google Analytics
tags:
  - API
  - 代码
  - 谷歌分析
---
通过<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/api/" title="查看API中的全部文章" target="_blank">API</a></span>可以获取超过一万行数据，你知道吗？（<span class='wp_keywordlink'><a href="http://www.yeezhe.com/" title="译者" target="_blank">译者</a></span>注：<a title="自定义Google Analytics报告中导出数据的多少" rel="bookmark" href="http://bluewhale.cc/2010-01-13/custom-google-analytics-reports-export-data.html" target="_blank">自定义Google Analytics报告中导出数据的多少</a>）  
以下来自<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="谷歌分析" target="_blank">谷歌分析</a></span>官方博客，编程<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e4%bb%a3%e7%a0%81/" title="查看代码中的全部文章" target="_blank">代码</a></span>什么的，太专业了，不太懂，专业的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e8%b0%b7%e6%ad%8c%e5%88%86%e6%9e%90/" title="查看谷歌分析中的全部文章" target="_blank">谷歌分析</a></span>师请点击查看相关<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e4%bb%a3%e7%a0%81/" title="查看代码中的全部文章" target="_blank">代码</a></span>吧。

[<img class="alignnone size-full wp-image-227" title="Screen shot 2011-03-28 at 12_42_32 PM" src="http://blog.xiaoq.in/cdn/images/2011/03/Screen-shot-2011-03-28-at-12_42_32-PM.png" alt="" width="328" height="209" />][1]

<div>
  <div>
    <strong>Auto-Pagination through the <span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/api/" title="查看API中的全部文章" target="_blank">API</a></span></strong>
  </div>
  
  <div>
    <strong> </strong>
  </div>
  
  <p>
    通过<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/api/" title="查看API中的全部文章" target="_blank">API</a></span>自动分页<br /> Here is a quick overview on how to do auto-pagination with our API. You might also follow along by checking <a href="http://code.google.com/p/ga-api-http-samples/source/browse/trunk/src/data_export/v2/python/pagination/pagination_demo.py">the fully working sample code in Python</a> which you can use in your own applications.
  </p>
  
  <p>
    The following sample query fetches the first 10,000 keywords by conversion rate for the month of February:
  </p>
  
  <p>
    https://www.google.com/analytics/feeds/data
  </p>
  
  <p>
    ?ids=ga:12345<br /> &dimensions=ga:keywords<br /> &metrics=ga:conversionRateAll<br /> &sort=-ga:conversionRateAll<br /> &start-date=2011-02-01<br /> &end-date=2011-02-28<br /> &start-index=1<br /> &max-results=10000
  </p>
  
  <p>
    Notice how start-index is set to 1 and max-results is set to 10,000. When this query is issued to the API, the API will return up to 10,000 results. The API also returns the number rows found in <span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span> in the openSearch:totalResult XML element
  </p>
  
  <p>
    14,654
  </p>
  
  <p>
    To get the total number of pages in this request, we can use the following python code:
  </p>
  
  <p>
    num_pages = math.ceil(total_results / 10000)
  </p>
  
  <p>
    Then getting the start-index for each additional page is trivial:
  </p>
  
  <p>
    for page_number in range(num_pages)[1:]: # skips the first page.<br /> start_index_for_page = page_number * 10000 + 1
  </p>
  
  <p>
    Thats it! If you want to start doing this today, or just see how it should work, we’ve included a fully working <a href="http://code.google.com/p/ga-api-http-samples/source/browse/trunk/src/data_export/v2/python/pagination/pagination_demo.py">example</a>. If you liked this, and want to see more example, let us know what we should do next in our comments.
  </p>
  
  <div>
    <div>
      Posted by Nick Mihailovski, Google Analytics Team
    </div>
  </div>
</div>

 [1]: http://blog.xiaoq.in/cdn/images/2011/03/Screen-shot-2011-03-28-at-12_42_32-PM.png