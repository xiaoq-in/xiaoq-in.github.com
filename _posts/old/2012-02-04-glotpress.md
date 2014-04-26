---
title: GlotPress，卓越的在线协作翻译PHP程序
author: 肖庆
layout: post
permalink: /net/glotpress/
sina_t:
  - 'true'
ratings_users:
  - 0
ratings_score:
  - 0
ratings_average:
  - 0
views:
  - 1554
duoshuo_thread_id:
  - 511964
yourls_shorturl:
  - http://t.xiaoq.in/32
ta-thumbnail:
  - NoMediaFound
categories:
  - 互联网
tags:
  - BackPress
  - GlotPress
  - PHP程序
  - 协作翻译
  - 开源程序
  - 翻译
  - 译者
---
<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/glotpress/" title="查看GlotPress中的全部文章" target="_blank">GlotPress</a></span>是一款基于PHP语言的高效在线<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%8d%8f%e4%bd%9c%e7%bf%bb%e8%af%91/" title="查看协作翻译中的全部文章" target="_blank">协作翻译</a></span>程序，基于<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/backpress/" title="查看BackPress中的全部文章" target="_blank">BackPress</a></span>开发，目前正处于开发初期阶段并未正式发布，不过我们可以通过SVN下载安装，要安装这个程序可不太容易，首先你需要有SSH的权限，其次由于它没有内置会员管理，因此还需要整合WordPress等基于<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/backpress/" title="查看BackPress中的全部文章" target="_blank">BackPress</a></span>的程序。

其中的一个重要功能是可以导出为网站或者软件所需要的文件，而且可以通过谷歌<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%bf%bb%e8%af%91/" title="查看翻译中的全部文章" target="_blank">翻译</a></span>获取<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%bf%bb%e8%af%91/" title="查看翻译中的全部文章" target="_blank">翻译</a></span>建议，可以保留各个<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%bf%bb%e8%af%91/" title="查看翻译中的全部文章" target="_blank">翻译</a></span>版本，具有原文和译文的左右对比功能，具备审核和筛选机制，等等。

<img class="alignnone" title="GlotPress" src="http://translate.xiaoq.in/img/glotpress-logo.png" alt="" width="284" height="47" />

当然，如果你曾经用过SSH和SVN的话，安装过程只需要几分钟。

以下是安装过程中需要使用的几个主要命令，完全可以通过SSH来操作，另外通过下载在线的zip文档是不完整的，因为<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/backpress/" title="查看BackPress中的全部文章" target="_blank">BackPress</a></span>这个外部模块必须只能通过SVN来获得，用户删除和添加也必须只能通过命令来实现：

svn checkout http://svn.glotpress.org/trunk/

php scripts/wipe-permissions.php

php scripts/add-admin.php

以下是几个相关教程，感兴趣的可以下载安装试下，WordPress和Yoast都是采用的这个程序搭建的平台进行<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e5%8d%8f%e4%bd%9c%e7%bf%bb%e8%af%91/" title="查看协作翻译中的全部文章" target="_blank">协作翻译</a></span>。

<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/glotpress/" title="查看GlotPress中的全部文章" target="_blank">GlotPress</a></span>安装英文教程：<a href="http://remkusdevries.com/how-to-use-glotpress-for-your-translations/" target="_blank">http://remkusdevries.com/how-to-use-glotpress-for-your-translations/</a>

TortoiseSVN 简明使用：<a style="font-size: 13px; font-weight: normal;" href="http://fairyfish.net/2007/09/08/tortoisesvn-introduce/" target="_blank">http://fairyfish.net/2007/09/08/tortoisesvn-introduce/</a>

GlotPress程序演示：<a href="http://translate.xiaoq.in/" target="_blank">http://translate.xiaoq.in/</a>，如果你注册了我的博客会员，那么可以使用该用户名和密码登陆，默认状态下你是<span class='wp_keywordlink'><a href="http://www.yeezhe.com/" title="译者" target="_blank">译者</a></span>身份。