---
title: 正则表达式注意事项
author: 54jack
layout: post
permalink: /sem/tips-for-building-regular-expressions/
sina_t:
  - 'true'
views:
  - 867
  - 867
qq_t:
  - 'true'
duoshuo_thread_id:
  - 511878
yourls_shorturl:
  - http://t.xiaoq.in/5b
ta-thumbnail:
  - NoMediaFound
categories:
  - 搜索引擎营销
tags:
  - Advanced Web Metrics with Google Analytics
  - Analytics
  - Analytics 帮助
  - Brian Clifton
  - google analytics
  - 什么是正则表达式
  - 正则表达式
---
Make the regular expression as simple as possible. Complex expressions take longer to process or match than simple expressions.

<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e6%ad%a3%e5%88%99%e8%a1%a8%e8%be%be%e5%bc%8f/" title="查看正则表达式中的全部文章" target="_blank">正则表达式</a></span>应尽量简单。与简单表达式相比，复杂表达的处理或匹配需要更多时间。

• Avoid the use of .* if possible because this expression matches everything zero or more times and may slow processing of the expression. For instance, if you need to match all of the following

index.html, index.htm, index.php, index.aspx, index.py, index.cgi

use

index.(h|p|a|c)+.+

not

index.*

如果可能，请避免使用 .\*，因为此表达式与任何内容都匹配，会降低表达式的处理速度。例如，如果需要匹配 index.html, index.htm, index.php, index.aspx, index.py, index.cgi，请使用index.(h|p|a|c)+.+而不要用index.\*。

• Try to group patterns together when possible. For instance, if you wish to match a file suffix

of .pdf, .doc, and .ppt use

.(pdf|doc|ppt)

not

.pdf|.doc|.ppt

如果可能，将各种方案组合使用。例如，要匹配文件扩展名或 .pdf、.doc 和 .pdf，请使用.(pdf|doc|ppt)而不是.pdf|.doc|.ppt。

• Be sure to escape the regular expression wildcards or meta characters if you wish to match those literal characters. Common ones are periods in filenames and parentheses in text.

如果要匹配这些文字字符，请务必使用<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e6%ad%a3%e5%88%99%e8%a1%a8%e8%be%be%e5%bc%8f/" title="查看正则表达式中的全部文章" target="_blank">正则表达式</a></span>通配符或元字符的转义字符。通常做法是在文件名字使用点“.”或者在文本中使用圆括号“()”。

• Use anchors whenever possible (^ and $, which match either the beginning or end of an expression), because these speed up processing.

只要可能，请使用定位符。定位符指 ^ 和 $，分别用于匹配表达式开头或结尾。尽可能使用定位符可加快处理速度。

本文摘译自<span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="谷歌分析" target="_blank">谷歌分析</a></span>专家<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/brian-clifton/" title="查看Brian Clifton中的全部文章" target="_blank">Brian Clifton</a></span>的**Advanced Web Metrics with <span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>**，同时参考<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/analytics-2/" title="查看Analytics中的全部文章" target="_blank">Analytics</a></span>帮助中的“<a title="什么是正则表达式" href="https://www.google.com/support/googleanalytics/bin/answer.py?answer=55582&hl=zh_CN&utm_id=ad" target="_blank">什么是正则表达式</a>”中**正则表达式注意事项。**