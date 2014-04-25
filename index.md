---
layout: page
title: 首页
tagline: 数字营销探索与学习
---
{% include JB/setup %}

[文章订阅](/rss.xml)

关于数据分析、搜索营销、数字营销等相关话题，欢迎与我交流: [关注微博](http://weibo.com/1282922154)

## 作者简介

中文名 `肖庆`，英文名`Jason`:
    
    数字营销从业者，主攻数据分析和搜索营销
    
    资质认证 :
      Google Analytics个人认证
      Google AdWords个人认证
      Bing Advertising个人认证

*持续学习的心态比认证本身更重要
    
## 最新文章

    微信公众平台同步更新，欢迎订阅，订阅号：xiaoq-in

近期关注主题：Google Tag Manager、Universal Analytics

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
