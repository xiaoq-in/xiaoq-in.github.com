---
title: GTM：如何获取clientId并存入自定义维度
author: 肖庆
layout: post
permalink: /google-tag-manager/access-universal-clientid-through-gtm/
ratings_users:
  - 0
ratings_score:
  - 0
ratings_average:
  - 0
views:
  - 183
categories:
  - Google Tag Manager
tags:
  - clientId
  - GTM
  - 宏
---
如何获取<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/clientid/" title="查看clientId中的全部文章" target="_blank">clientId</a></span>并存入自定义维度，这个问题之前困扰了我很久，主要看了这几个地方：<a href="http://stackoverflow.com/questions/19976976/accessing-clientid-set-by-google-analytics-through-google-tag-manager" target="_blank">1</a>、<a href="https://productforums.google.com/forum/#!topic/tag-manager/TqWEfMl3XK8" target="_blank">2</a>、<a href="http://stackoverflow.com/questions/21806716/google-tag-manager-analytics-js-clientid-as-custom-dimension-set-as-an-event" target="_blank">3</a>，都未能成功。以下这种方法通过配合事件跟踪成功过，如我的这个<a title="淘宝关键词排名查询" href="http://www.sotop.org/" target="_blank">淘宝关键词排名查询</a>网站中运用的就是这个方法（直接使用貌似不凑效）：

    function(){
      var client = ga.getAll()[0].get('clientId');
      return client;
    }
    

今天刚好有空再研究了下Google Tag Manager，看到<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%ae%8f/" title="查看宏中的全部文章" target="_blank">宏</a></span>已经支持了第一方cookie，这下简单很多了。因为客户ID是存储在名为\_ga的第一方cookie中的，形如：\_ga=GA1.2.1232495606.1396280517（你可以在console中输入：document.cookie查看），其中GA1应该是Universal Analytics的版本号，而2则是域名的层级，比如二级子域名的话则为3，1232495606.1396280517这个一般统称为<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/clientid/" title="查看clientId中的全部文章" target="_blank">clientId</a></span>，也即上面方法的出来的client。不过，再行拆分的话，其中1232495606这个是唯一身份标识，而1396280517这个则是首次访问的时间戳。（<a href="http://stackoverflow.com/questions/16102436/what-are-values-in-ga-cookie" target="_blank">详细介绍</a>）

了解了这个cookie的意思之后，我们便可以对这个数据进行拆分和存储了。我们存储这个信息的主要作用在于唯一身份识别与辨识，同时配合首次访问时间我们可以了解访客的忠诚度和推广效果。不过，由于UA存储的cookie值十分有限，只有上面说到的2个，不像ga.js那样，存储了3个时间戳、访问次数、来源媒介广告系列等信息。我们暂且就先用这2个好了，大多数情况下也够用了，至于其他的维度，我们可以也通过其他的方法来实现。

如果你懂英文、理解能力不错并且对<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/gtm/" title="查看GTM中的全部文章" target="_blank">GTM</a></span>非常熟悉的话，直接看这个gist文件就好了：<a href="https://gist.github.com/xiaoq-in/46aa800b3bec45596a3c#file-ua-clientid-tracking" target="_blank"><strong>ua clientid tracking</strong></a>。

下面通俗地解释下这几个步骤：

1.  创建一个“第一方Cookie”的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%ae%8f/" title="查看宏中的全部文章" target="_blank">宏</a></span>，宏名称为：ga cookie。
2.  创建一个”自定义JavaScript“的宏，宏名称为“cid”，在代码框中填入如下代码一：
3.  创建另外一个”自定义JavaScript“的宏，宏名称为”intit_time“，在代码框中填入如下代码二（这里主要是提取cookie中的第四段值，然后将时间戳转化为一般的时间格式）：
4.  在你通用的UA代码中新增2个自定义维度，索引号分别为1和2，然后分别对应上述{{cid}}和{{intit_time}}
5.  在Universal Analytics的后台分别新建2个自定义维度，索引号分别为1和2，分别命名为：客户ID、首次访问时间。

代码一：

    function() {
      try {
        return {{ga cookie}}.split(".")[2];
      } catch(e) {
        console.log("No Universal Analytics cookie found");
        return "n/a";
      }
    }

代码二：

    function() {
      try {
        var init_time = new Date({{ga cookie}}.split(".")[3] * 1000)
        var init_time = init_time.getFullYear()+"-"+(init_time.getMonth()+1)+"-"+init_time.getDate()+" "+init_time.getHours()+":"+init_time.getMinutes()+":"+init_time.getSeconds();
        return init_time;
      } catch(e) {
        console.log("No init_timestamp cookie found");
        return "n/a";
      }
    }

另外，需要注意的是：如果用户只访问过一次网站并且本次为你设置代码后的第一次，那么将在自定义维度的对应字段中显示为n/a，你可以根据情况设置为会话级别或者访客级别的自定义维度。最终我们可以生成类似如下的报告：

<img class="alignnone size-full wp-image-1652" alt="init_time source_medium" src="https://xiaoq.in/cdn/2014/04/init_time-source_medium.gif" width="510" height="460" />