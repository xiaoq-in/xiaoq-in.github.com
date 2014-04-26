---
title: 用Google Analytics（谷歌分析）跟踪搜索引擎蜘蛛
author: 54jack
layout: post
permalink: /google-analytics/tracking-search-bots-in-google-analytics/
sina_t:
  - 'true'
views:
  - 1263
  - 1263
qq_t:
  - 'true'
duoshuo_thread_id:
  - 511913
yourls_shorturl:
  - http://t.xiaoq.in/5a
ta-thumbnail:
  - https://xiaoq.in/thumb/cache/2011/8/523-1.jpg;https://xiaoq.in/thumb/cache/2011/8/523-2.jpg;https://xiaoq.in/thumb/cache/2011/8/523-3.jpg;
categories:
  - Google Analytics
tags:
  - SEO
  - 客户端
  - 服务器端
  - 用户代理
  - 蜘蛛爬行
  - 谷歌分析
---
<div>
  <p>
    通常情况下，<span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="谷歌分析" target="_blank">谷歌分析</a></span>的跟踪代码是基于JavaScript的解决方案，它依赖于浏览器来生成并存储cookie。这种依赖性也正是为什么<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%b0%b7%e6%ad%8c%e5%88%86%e6%9e%90/" title="查看谷歌分析中的全部文章" target="_blank">谷歌分析</a></span>报告中不会显示大多数蜘蛛访问你网站的数据。
  </p>
  
  <p>
    但是，如果你真想跟踪搜索蜘蛛的活动呢？这或许是为了做技术性的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/seo-2/" title="查看SEO中的全部文章" target="_blank">SEO</a></span>分析。我们已经制作了一个叫做“搜索蜘蛛专用GA代码”的PHP代码库，它使用<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e6%9c%8d%e5%8a%a1%e5%99%a8%e7%ab%af/" title="查看服务器端中的全部文章" target="_blank">服务器端</a></span>的进程来捕捉来自众多蜘蛛的页面浏览。
  </p>
  
  <p>
    尽管<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%b0%b7%e6%ad%8c%e5%88%86%e6%9e%90/" title="查看谷歌分析中的全部文章" target="_blank">谷歌分析</a></span>已经有专门的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e6%9c%8d%e5%8a%a1%e5%99%a8%e7%ab%af/" title="查看服务器端中的全部文章" target="_blank">服务器端</a></span>移动跟踪代码脚本，然而该脚本的设计宗旨仍然只是用来跟踪来自浏览器端的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%94%a8%e6%88%b7%e4%bb%a3%e7%90%86/" title="查看用户代理中的全部文章" target="_blank">用户代理</a></span>活动。我已经对脚本进行了解构并做了一些修改，使得所有对于_utm.gif文件请求的构建和发送均完全由服务器端处理，从而允许任何<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%94%a8%e6%88%b7%e4%bb%a3%e7%90%86/" title="查看用户代理中的全部文章" target="_blank">用户代理</a></span>均能被跟踪。
  </p>
  
  <p>
    当然，我们只是希望用这个脚本跟踪蜘蛛（而非人），因此这个代码库还包括一个<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%94%a8%e6%88%b7%e4%bb%a3%e7%90%86/" title="查看用户代理中的全部文章" target="_blank">用户代理</a></span>被认定为蜘蛛的白名单。这将确保你有一个“仅含蜘蛛访问”的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%b0%b7%e6%ad%8c%e5%88%86%e6%9e%90/" title="查看谷歌分析中的全部文章" target="_blank">谷歌分析</a></span>配置文件。
  </p>
  
  <h2>
    如何设置“搜索蜘蛛专用GA代码”
  </h2>
  
  <ol>
    <li>
      在谷歌分析中创建一个“仅含蜘蛛访问”的配置文件。
    </li>
    <li>
      下载“<a href="http://goo.gl/ydtiR" target="_blank">搜索蜘蛛专用GA代码</a>”代码库
    </li>
    <li>
      解压，然后把文件放到你网站的“/gaforsearchbots/”文件夹（示例：<a href="http://g.xiaoq.in/gaforsearchbots/">www.54jack.com/gaforsearchbots/</a>）。
    </li>
    <li>
      拷贝sample.php文件中的跟踪代码，把它们放置到你PHP源文件中（示例：模板文件中的“header”包含文件）
    </li>
    <li>
      按下面步骤编辑跟踪代码： <ol>
        <li>
          设置$GA_SB_ACCOUNT变量为你的GA属性ID，用MO替换掉UA。
        </li>
        <li>
          设置$GA_SB_PATH为‘/gaforsearchbots/’ 文件夹的路径。
        </li>
      </ol>
    </li>
  </ol>
  
  <p>
    需要注意的一件事情是在这个代码库中是“来源”设置为用户代理，而非传统的广告系列来源。我发现使用这种方法可以更简单地下钻到不同蜘蛛。我会更关注页面浏览而非访问，以更好地分析蜘蛛如何爬行你的网站。
  </p>
  
  <p>
    另外一间需要明白的重要事情是，该代码仅在<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%9c%98%e8%9b%9b%e7%88%ac%e8%a1%8c/" title="查看蜘蛛爬行中的全部文章" target="_blank">蜘蛛爬行</a></span>了一个确实会使用此代码执行PHP脚本的URL时才会运行。如果一个<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%9c%98%e8%9b%9b%e7%88%ac%e8%a1%8c/" title="查看蜘蛛爬行中的全部文章" target="_blank">蜘蛛爬行</a></span>了一个无法返回已渲染页面的URL（比如，500内部错误），那么搜索蜘蛛专用GA代码将不会执行。因此，这并不会捕捉到所有的蜘蛛活动，特别是含有很多错误页面的网站。明白蜘蛛在错误URL中的活动是非常重要的，我们也正在努力开发第二个版本来解决这个问题。
  </p>
  
  <h2>
    我能在我的报告中看到什么？
  </h2>
  
  <p>
    尽管你可以在谷歌分析中探索所有的标准报告，我仍然推荐下面这个自定义报告。配置为下钻：来源->页面。你可以任意修改这个报告以满足你的特点需求。
  </p>
  
  <p>
    <a href="http://goo.gl/7U8Ul" target="_blank">http://goo.gl/7U8Ul</a>
  </p>
  
  <p>
    在这个报告中看到的第一件事情就是一系列的不同<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%9c%98%e8%9b%9b%e7%88%ac%e8%a1%8c/" title="查看蜘蛛爬行中的全部文章" target="_blank">蜘蛛爬行</a></span>了我们的网站。
  </p>
  
  <p>
    <a href="http://xiaoq.in/?attachment_id=1808" rel="attachment wp-att-1808"><img src="http://www.cardinalpath.com/cpwp/wp-content/uploads/searchbots-overview.jpg" alt="google analytics for search bots custom report" width="394" height="333" /></a>
  </p>
  
  <p>
    你可以看到一些爬行网站的不同搜索引擎。位于名单首位的是“未知蜘蛛”，它包含了所有未定义的蜘蛛。我相信我只知道很少的一些特定蜘蛛，产生了这些点击。因此我应该做的便是识别这些未定义蜘蛛的用户代理，然后把它们补充到botconfig.php文件中。
  </p>
  
  <p>
    让我们看下Googlebot在为期6周时间段的爬行行为：
  </p>
  
  <p>
    <a href="http://xiaoq.in/?attachment_id=1811" rel="attachment wp-att-1811"><img src="http://www.cardinalpath.com/cpwp/wp-content/uploads/searchbots-google-541x365.jpg" alt="googlebot crawl in google analytics" width="541" height="365" /></a>
  </p>
  
  <p>
    在这个报告中，我们可以看到一些东西。首先，我们可以看到每日蜘蛛活动，在这个较短的时间段内似乎有上升的趋势。我们还可以看到Googlebot（谷歌蜘蛛）经常爬行的热门页面，这可能折射出它认为哪些页面是重要的。
  </p>
  
  <p>
    为了让你通过时间归类页面爬行，这个代码库还配置为发送以日期时间为标记的页面级自定义变量。下面是昨天哪些时间页面被爬行的一个细分：
  </p>
  
  <p>
    <a href="http://xiaoq.in/?attachment_id=1812" rel="attachment wp-att-1812"><img src="http://www.cardinalpath.com/cpwp/wp-content/uploads/searchbots-timecrawl-550x313.jpg" alt="google analytics for search bots pages sorted by time" width="550" height="313" /></a>
  </p>
  
  <p>
    我看到的数据非常酷，但是我确信还有一些更有趣的事情有待发现。请下载文件并亲自尝试一下。分享其他有见地的报告，或者让我们知道对于这个代码有哪些可做改进的。
  </p>
  
  <p>
    <span class='wp_keywordlink'><a href="http://www.yeezhe.com/" title="译者" target="_blank">译者</a></span><span class='wp_keywordlink'><a href="https://xiaoq.in/" title="肖庆" target="_blank">肖庆</a></span>原创翻译自：<a href="http://www.cardinalpath.com/blog/tracking-search-bots-in-google-analytics" target="_blank">http://www.cardinalpath.com/blog/tracking-search-bots-in-google-analytics</a> 翻译不易，转载请注明出处，谢谢。
  </p>
</div>