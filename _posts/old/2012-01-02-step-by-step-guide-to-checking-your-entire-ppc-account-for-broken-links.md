---
title: 循序渐进检查整个PPC账户的死链接
author: 肖庆
layout: post
permalink: /google-adwords/step-by-step-guide-to-checking-your-entire-ppc-account-for-broken-links/
sina_t:
  - 'true'
views:
  - 8449
ratings_users:
  - 0
ratings_score:
  - 0
ratings_average:
  - 0
duoshuo_thread_id:
  - 511938
yourls_shorturl:
  - http://t.xiaoq.in/6c
ta-thumbnail:
  - http://blog.xiaoq.in/thumb/cache/2012/1/571-1.gif;http://blog.xiaoq.in/thumb/cache/2012/1/571-2.gif;http://blog.xiaoq.in/thumb/cache/2012/1/571-3.jpg;http://blog.xiaoq.in/thumb/cache/2012/1/571-4.jpg;http://blog.xiaoq.in/thumb/cache/2012/1/571-5.jpg;http://blog.xiaoq.in/thumb/cache/2012/1/571-6.jpg;
categories:
  - Google AdWords
tags:
  - Adwords编辑器
  - PPC错误链接
  - Xenu
  - 死链接
  - 目标网址
  - 着陆页面
---
你知道你是否正在因为带流量到（没有找到）404页面而浪费钱吗？

随着时间的增长，URL链接地址发生了改变，网站进行了重建，<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%9d%80%e9%99%86%e9%a1%b5%e9%9d%a2/" title="查看着陆页面中的全部文章" target="_blank">着陆页面</a></span>改变了，因而要找出所有这些<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e6%ad%bb%e9%93%be%e6%8e%a5/" title="查看死链接中的全部文章" target="_blank">死链接</a></span>将会十分困难。如果你正在通过<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e6%ad%bb%e9%93%be%e6%8e%a5/" title="查看死链接中的全部文章" target="_blank">死链接</a></span>为错误页面带去流量&#8212;那么，那么正在浪费钱。

下面是一个循序渐进的指南，帮助你找出Adwords账户中所有的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e6%ad%bb%e9%93%be%e6%8e%a5/" title="查看死链接中的全部文章" target="_blank">死链接</a></span>。我将介绍如何检查Adwords的死链接；这种方法也可以应用到任何的PPC账户。

### 第一步&#8212;确保你的网站显示404错误

打开你们网站一个不存在的页面。比如，xiaoq.in/404

拷贝这个网址。然后找一个“服务器头部信息检查工具”，我喜欢<a href="http://www.seoconsultants.com/tools/headers.asp" target="_blank">SEO Consultants Tool</a>

把这个网站黏贴到这个工具的输入框，然后查看服务器的头部信息。

“HTTP状态代码”应该显示为404未找到

<img class="alignnone size-full wp-image-572" title="404-header" src="http://xiaoq.in/g/pics/2012/01/404-header.gif" alt="" width="630" height="260" />

如果你看到2000K的状态代码，或者其他非错误页面，你需要修正网站以显示404错误。这将不仅可以帮助查找错误页面，还是一个<a title="SEO最佳实践" href="http://googlewebmastercentral.blogspot.com/2008/08/farewell-to-soft-404s.html" target="_blank">SEO最佳实践</a>。

一旦你确认你的网站返回404错误，继续第二步。

### 第二步&#8212;导出账户到Excel表格

这其中的第一步便是导出你的整个账户到一个Excel文件。对于AdWords账户，这可以在<a title="AdWords编辑器" href="http://www.google.com/intl/en/adwordseditor/" target="_blank">AdWords编辑器</a>中轻松地完成。

按照以下步骤：

*   在编辑器中打开你的账户
*   定位至文件>导出电子表格(CSV)(S) 
    *   如果你想检查整个账户，选择“导出整个账户”
    *   如果你只想检查其中一个广告系列，选择“导出当前视图”

<img class="alignnone size-full wp-image-573" title="adwords-editor-export" src="http://xiaoq.in/g/pics/2012/01/adwords-editor-export.gif" alt="" width="510" height="260" />

如果你想检查微软adCenter或者Yahoo搜索营销广告系列，导出这些广告系列为CSV文件即可。

### 第三步&#8212;将所有<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%9b%ae%e6%a0%87%e7%bd%91%e5%9d%80/" title="查看目标网址中的全部文章" target="_blank">目标网址</a></span>转化为超级链接

打开你刚刚保存的文件。

“T”列应该是被标记为 ‘Destination URLs’（<span class='wp_keywordlink'><a href="http://www.yeezhe.com/" title="译者" target="_blank">译者</a></span>注：如果不是，请做相应调整）。这一列同时保留关键词和广告语级别的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%9b%ae%e6%a0%87%e7%bd%91%e5%9d%80/" title="查看目标网址中的全部文章" target="_blank">目标网址</a></span>。

更改T列的标头名为“URLs”（或者任意单字）。如果其中有空格，我们将运行的宏将会停止运行。因为T列中的其他单元格应该是http://something，改列中应该也不会有其他的空格。

接下来，我们需要把所有的T列中的网址更改为超级链接。我们将通过宏来实现。不要被使用宏给吓到了，非常简单&#8212;只需要按照下面的步骤来。

在Excel 2007中，定位至视图标签，然后点击“宏”。输入 “ConvertToHyperlink” 然后点击“创建”。

你应该会看到一个代码输入框：

<img src="http://certifiedknowledge.org/wp-content/uploads/2009/01/1162009-84510am.jpg" alt="1162009_84510 AM" width="529" height="236" border="0" />

拷贝下面的代码到“Sub ConvertToHyperlink ()’ 和“End Sub”之间

`Dim rng As Range</p>
<p>Set rng = Range("T1:T" & Cells _</p>
<p>(Rows.Count, 1).End(xlUp).Row)</p>
<p>'Set rng = ActiveSheet.UsedRange</p>
<p>For Each cell In rng</p>
<p>cell.Select</p>
<p>If cell.Value <> "" Then</p>
<p>If Left(cell.Value, 7) = "http://" Then</p>
<p>URL = cell.Value</p>
<p>Else</p>
<p>URL = "http://" + cell.Value</p>
<p>End If</p>
<p>ActiveSheet.Hyperlinks.Add Anchor:=cell, _</p>
<p>Address:=URL, TextToDisplay:=cell.Value</p>
<p>End If</p>
<p>here:</p>
<p>Next`

`<img src="http://certifiedknowledge.org/wp-content/uploads/2009/01/1162009-84735am.jpg" alt="1162009_84735 AM" width="529" height="468" border="0" />`

特别感谢<a title="超级链接转换宏代码" href="http://answers.yahoo.com/question/index?qid=20080801135151AAOKGiu" target="_blank">Yahoo问答</a>的帮助，提供了这段代码，非常感谢。

现在，运行代码。你可以通过两种方式来实现。

1.  点击Excel中的录制图标。
2.  返回到Excel文档 
    *   点击宏按钮
    *   选择宏
    *   点击选项
    *   设置一个该宏的快捷键
    *   关闭选项框
    *   按下快捷键（ctrl+你选择的字母）

当你按键之后，在后台，T列中的所有东西都会被转化为超级链接。完成的时候，你可能会看到超时错误提示（原因是宏到达了一个它无法更改的单元格）。如果该单元格现在是超级链接，忽视这个错误。如果这些单元格没有改变为超级链接，很有可能是你没有把T列设置为一个单字。改变表头的标签，让它里面不包含任何空格，然后重试。

最后一件事情是复制/黏贴。由于WordPress和浏览器可能会产生字符转换。你可以在<a href="http://certifiedknowledge.org/images/ConvertToHyperlink.txt" target="_blank">这里</a>查看这个文本文件。

If you are running this macro for Yahoo or adCenter, there’s an easy way to change any column to hyperlinks. In the code, the third row contain ‘T1:T’ – just change those values to the row you want to change to hyperlinks. For instance, if you wanted to convert column A to hyperlinks, the code would look like:

`Set rng = Range("A1:A" & Cells _`

### 第四步&#8212;保存文档为HTML网页格式

Save the document as ‘webpage’ which is a .html or .htm file for Excel.

In Excel 07, go to ‘Save As’ > Other formats > and Choose webpage.

You will most likely see an error that says some features will be incompatible with the new format. Go ahead and click ‘Yes’ and save the document as an HTML file.

Now we have a file that contains all of our PPC destination URLs. It’s time to check for errors.

### 第五步&#8212;检查文件中的错误链接

The very first thing to do is make sure you have [Xenu Link Sleuth][1] on your computer. <span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/xenu/" title="查看Xenu中的全部文章" target="_blank">Xenu</a></span> is a free spidering program. If you don’t have it, download it and install it now – it’ll only take a couple minutes.

Next, open <span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/xenu/" title="查看Xenu中的全部文章" target="_blank">Xenu</a></span>.

Go to File > Check URL

In the next box, click on ‘local file’ and select the HTML file you just saved from Excel.

<img src="http://certifiedknowledge.org/wp-content/uploads/2009/01/1162009-90110am.jpg" alt="1162009_90110 AM" width="529" height="428" border="0" />

Make sure ‘’Check external links’ is checked. Now just click the ‘OK’ button and go. Depending on how large your PPC account is, Xenu may take a few minutes to a few hours (I once had it run for 19 hours getting around 850k destination URLs. The bonus? It didn’t time out.

Once Xenu finishes, you will now have a report of every URL in your PPC account and if it’s broken or OK. You will see one broken link, which is the name of Column T. You can either save the file, view the full report, or export to a tab delineated file (which can be opened in Excel).

You can click on the below picture to see a larger view. Look for ‘Not Found’ in the Status column. Every red line is a link where you’re sending traffic to broken pages – lost money.

<a href="http://certifiedknowledge.org/wp-content/uploads/2009/01/1162009-92823am.jpg" rel="shadowbox[post-4300];player=img;"><img src="http://certifiedknowledge.org/wp-content/uploads/2009/01/1162009-92823am-thumb.jpg" alt="1162009_92823 AM" width="529" height="249" border="0" /></a>

### 第六步&#8212;别再浪费钱了

If you have a website where multiple people or divisions make changes to your site – make sure you coordinate the activity. It’s very common to see traffic driven to broken pages. Don’t waste your money.

Even in companies with great communication, I’ve still seen old projects get released, prior sections of a website rolled back, etc.  All it takes is one person to make a quick change for you to start driving traffic to money-wasting pages.

Once you run this report once, you’ll see how easy it is to actually complete. While it looks complex, on a site with less than a thousand destination URLs, this entire process usually takes less than 5-10 minutes. That’s a small price of time to pay to stop wasting money.

 [1]: http://home.snafu.de/tilman/xenulink.html