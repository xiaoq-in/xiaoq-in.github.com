---
layout: post
title: Universal Analytics 实验指南（一）
permalink: /universal-analytics/content-experiments-1/
category : Universal Analytics
tags : [Universal Analytics, 内容实验, AB测试, 多手柄老虎机实验, MAB, Content Experiments]
---
{% include JB/setup %}



《A/B测试服务公司Optimizely获$5700万融资》，相信大家都对最近的这条消息感到很振奋。但是，作为屌丝的我们，可能支付不起昂贵的使用费，英文界面可能也让你有点晕，其实大多数情况下，也没太大必要。

如果你正在使用GA（本文及之后都特指UA版本，请升级吧），那么我们一起来玩玩GA的实验吧（最近的翻译去掉了“内容”这个词）。实验非常重要，页面改进全靠它了。

这里我们不使用A/B测试这个词语，因为GA的默认选项并非基于A/B算法，而是使用一种叫做“[多手柄老虎机实验](https://support.google.com/analytics/answer/2844870?hl=zh-Hans)”（英文全称为Multi-armed bandit，以下简称MAB）算法，这种算法可以缩短实验周期，并且不会因为实验变体的落差对整体的转化率产生太大的影响，当然也会有一些不足，感兴趣的童鞋可以看看[这篇文章](http://visualwebsiteoptimizer.com/split-testing-blog/multi-armed-bandit-algorithm/)。简单来说，MAB算法的核心就是基于“择优展示”。


如果你希望使用A/B算法，则可以在设置实验的第一步中点击“高级选项”，其中有一个“在各变体之间均匀地分配流量”，将其开启即可。这样的话，将会执行严格意义的A/B测试。提示语中对此是这样解释的：启用此选项可为实验生命周期的每个变体分配相等的流量。在此选项停用时，内容实验会按默认基于变体效果动态调整流量。

A/B测试主要有三种方式，页面跳转是实施层面来说最简单的（也是默认的玩法），但是也会一定程度上影响用户体验，我想没有人喜欢页面跳来跳去的吧。另外2种分别是：

1.基于浏览器客户端的js API

2.基于服务器端的API

对了，你可能不知道，GA的API是支持实验的，包括收集、管理和报告。

以下，以[我的首页](http://xiaoq.in/)为例，来介绍下个人最喜欢的，也是个人强烈推荐的js非页面跳转方式，代码范例如下：

{% gist 8ef2fdc33e9a76db367c gist.md %}

如果对js有所了解，并且读了GA的API文档，应该不难理解：

1.加载 Content Experiments JavaScript API client，其中api.js?experiment=`F6zsXkdMQTKlHGVBxeCPEA`的红色字体部分需替换为自己的“实验 ID”。

2.调用chooseVariation方法。

3.评估chooseVariation的返回值，然后通过js替换超级链接的文字。我这里是超级链接的文本，因此是.innerText，如果是图片，可能需要改成.src之类的（建议学习下[HTML DOM 教程](http://www.w3school.com.cn/htmldom/index.asp)）

4.加载analytics.js，并将请求发送至GA服务器。请注意，需要将实验的代码放在pageview或event、ecommerce等代码前面，如果实在不行的话，就再额外写一个非互动的事件吧。

设置时候注意以下几点：

1.设置或者选择一个符合测试目的的目标。

2.由于我们这里并没有使用多个页面，因此在设置实验的时候，变体的那几个URL随便填写几个，提示的错误也直接忽略。

3.在“配置实验”中，建议勾选“针对其他内容报告整合实验”。选择此选项后，在内容报告中，原始网页和变体网页的所有流量都将合并列入到原始网页的网址之下。这样可提高内容报告的易读性，而您仍然可以在实验报告中看到指向各个网页的流量。如果变体网页使用了相对网址，则不能使用此选项。

如果你的collect文件请求中包含`&xid=F6zsXkdMQTKlHGVBxeCPEA&xvar=2`这种字符串，那么，恭喜你，成功了。

试试吧，并没有那么想象的那么复杂。
