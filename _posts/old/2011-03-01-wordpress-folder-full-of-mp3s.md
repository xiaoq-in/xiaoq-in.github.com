---
title: WordPress高级技巧，如何自动播放文件夹音乐
author: 54jack
layout: post
permalink: /net/wordpress-folder-full-of-mp3s/
sina_t:
  - 'true'
views:
  - 1087
  - 1087
qq_t:
  - 'true'
duoshuo_thread_id:
  - 511738
yourls_shorturl:
  - http://t.xiaoq.in/2y
ta-thumbnail:
  - NoMediaFound
categories:
  - 互联网
tags:
  - Life Is Still A Struggle
  - MP3
  - WordPress
  - 花开的声音
---
其实来说，我最早是写音乐博客的，自从2008年那会从一家倒闭的音像店淘回来几十张英文CD之后，就开始真正的爱上了音乐了，几乎是每天晚上都要写上一篇。坚持了大概两年。PR那会也上升到了4，登上了易付宝的公益链接。  
当初使用的是一款叫做podpress的插件，但是后来发现，IE浏览器无法正常使用，那个插件一起用就会使博客强制关闭。并且会在底部产生难看的广告链接，很难清除。  
其实，<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/mp3/" title="查看MP3中的全部文章" target="_blank">MP3</a></span>播放的插件有很多，但是我的偏好是尽量少用，用最精简的。今天发现了一款比较好的<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/mp3/" title="查看MP3中的全部文章" target="_blank">MP3</a></span>播放插件，可以直接读取文件夹中的所有<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/mp3/" title="查看MP3中的全部文章" target="_blank">MP3</a></span>文件，然后在边栏生成链接。点击播放。  
后来，经过我的一番改进，可以直接用flash player播放了，效果见我的博客右栏。  
编辑插件文件，把 
*   
中间的链接改成：  
<embed src="http://g.xiaoq.in/images/mp3.swf?soundFile=http://g.xiaoq.in/' . $data['folder'] . '/' . $file . '&bg=0xeeeeee&leftbg=0x357dce&lefticon=0xFFFFFF&rightbg=0xf06a51&rightbghover=0xaf2910&righticon=0xFFFFFF&righticonhover=0xffffff&text=0x666666&slider=0x666666&track=0xFFFFFF&border=0x666666&loader=0x9FFFB8&loop=no&autostart=no" type="application/x-shockwave-flash" wmode="transparent" height="40" width="200" />

  
<无法正常显示，请查看源文件>  
MP3播放强烈不建议放在自身服务器，百度、迅雷等工具可不是吃干饭的，什么都能抓取到，一般的防盗链方法也没多大用处，一旦被它们抓取到，就等着流量耗尽，被服务商关停吧。

下面，我就测试下几种防盗链的手法，而且反正博客目前流量不大，不用也是浪费，权当试验了，等哪天快耗尽了再把MP3删除好了。  
以下是防盗链的方法之一，使用.htaccess（需服务器支持，功能非常强大）：  
RewriteEngine On  
RewriteCond %{HTTP_REFERER} !^$ [NC]  
RewriteCond %{HTTP_REFERER} !54jack.com [NC]  
RewriteCond %{HTTP_REFERER} !www.54jack.com [NC]  
RewriteRule .*.(mp3|jpg|gif|png|ico)$ http://g.xiaoq.in/[L,NC]

其中有首歌就是那位嘻哈歌手通过邮件发送给我的，怎么样？**<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/life-is-still-a-struggle/" title="查看Life Is Still A Struggle中的全部文章" target="_blank">Life Is Still A Struggle</a></span>**  
另一首歌是，**<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e8%8a%b1%e5%bc%80%e7%9a%84%e5%a3%b0%e9%9f%b3/" title="查看花开的声音中的全部文章" target="_blank">花开的声音</a></span>**，这也是我们公司的期刊名，不错。