---
title: GA高级技巧：通过输入分析优化表单长度
author: 肖庆
layout: post
permalink: /google-analytics/optimize-form-length-with-input-analysis/
sina_t:
  - 'true'
ratings_users:
  - 0
ratings_score:
  - 0
ratings_average:
  - 0
views:
  - 1360
yourls_shorturl:
  - http://t.xiaoq.in/51
ta-thumbnail:
  - https://xiaoq.in/thumb/cache/2012/4/723-1.jpg;https://xiaoq.in/thumb/cache/2012/4/723-2.jpg;https://xiaoq.in/thumb/cache/2012/4/723-3.jpg;https://xiaoq.in/thumb/cache/2012/4/723-4.jpg;https://xiaoq.in/thumb/cache/2012/4/723-5.jpg;https://xiaoq.in/thumb/cache/2012/4/723-6.jpg;
categories:
  - Google Analytics
tags:
  - GA技巧
  - 网站优化
  - 虚拟页面跟踪
  - 表单跟踪
---
<table width="490" border="0">
  <tr>
    <td align="left" valign="middle" width="60%">
      很多人，包括我自己，都不喜欢填表单。表单通常很长，并且包含太多必填项，等等。然而，从商业的角度来看，表单是收集信息的绝佳工具。</p> <p>
        作为网站分析师的我们，要做的便是让双方都高兴并且通过输入分析优化表单长度。</td> <td align="center" width="40%">
          <img src="http://www.e-nor.com/blog/images/frustration.jpg" alt="" border="0" />
        </td></tr> </tbody> </table> 
        
        <p>
          在本文中，我将分享 E-Nor（<span class='wp_keywordlink'><a href="https://xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span>认证合作伙伴之一）在决定人们最不可能填写哪些字段时使用的技巧。我将告诉你如何将这些数据呈现给决策者和<span class='wp_keywordlink_affiliate'><a href="https://xiaoq.in/tag/%e7%bd%91%e7%ab%99%e4%bc%98%e5%8c%96/" title="查看网站优化中的全部文章" target="_blank">网站优化</a></span>人员以便他们作出必要的更改。
        </p>
        
        <p>
          <img src="http://www.e-nor.com/blog/images/form.jpg" alt="" border="0" />
        </p>
        
        <p>
          首先，我们需要添加一些JavaScript到表单的html代码中。在提交按钮代码下方的onclick事件中添加：
        </p>
        
        <p>
          <img src="http://www.e-nor.com/blog/images/code1.jpg" alt="" border="0" /><br /> 一旦提交这个表单，验证函数将会被执行，从而验证字段是否为空 。
        </p>
        
        <p>
          <a id="idtagger21" href="http://www.e-nor.com/blog/code/code03.htm" target="_blank"><img src="http://www.e-nor.com/blog/images/code.jpg" alt="" border="0" /></a><br /> 验证函数通常被用来验证必要的字段是否包含有效信息。在此，我们将同样使用它来传递两个变量到isEntered函数：
        </p>
        
        <ul>
          <li>
            第一个变量是用户在每个字段中输入的文本。比如，如果用户在name字段中输入“John Smith”，那么<em>document.getElementById(‘name’) </em>= “John Smith”，而如果该字段为空的话，则<em>document.getElementById(‘name’) </em>= “ ”。
          </li>
          <li>
            第二个变量是该字段的名字（比如“name”），这是发送信息到GA的必要变量。
          </li>
        </ul>
        
        <p>
          .<em>isEntered</em>函数将会检查从验证函数中传递的el变量。
        </p>
        
        <ul>
          <li>
            如果该变量值为空，它将发送一个pageview到GA，表明该字段为空（比如，/forms/contact_us.htm/<strong>empty</strong>/phone）
          </li>
        </ul>
        
        <table width="225" border="0">
          <tr>
            <td align="left" valign="middle" width="100">
              <h3>
                在GA中读取数据
              </h3>
            </td>
            
            <td align="left" valign="middle" width="110">
              <img src="http://www.e-nor.com/blog/images/google_logo.jpg" alt="" border="0" />
            </td>
          </tr>
        </table>
        
        <p>
          由于在我们的主配置文件中或许有成千上万的页面浏览，因此我建议为该表单创建一个特定的配置文件：
        </p>
        
        <p>
          1. 创建一个过滤器并命名为<em><em>URL Filter – Contact Us Form</em></em><br /> <a id="idtagger23" href="http://www.e-nor.com/blog/images/filter.jpg" target="_blank"><img src="http://www.e-nor.com/blog/images/filter_s.jpg" alt="" border="0" /></a>
        </p>
        
        <p>
          2. 添加上述过滤器到一个新的配置文件，配置文件命名为<em>Contact Us Form</em>或其他任意名称<em>。</em>
        </p>
        
        <p>
          3. 去往新的配置文件 -> 内容 -> 热门内容
        </p>
        
        <p>
          <a id="idtagger24" href="http://www.e-nor.com/blog/images/ga.jpg" target="_blank"><img src="http://www.e-nor.com/blog/images/ga_s.jpg" alt="" border="0" /></a>
        </p>
        
        <p>
          上述数字清晰显示哪些表单客户通常会填写或者留空。这种层次的输入分析必定会对优化表单长度有所帮助
        </p>
        
        <p>
          <img src="http://www.e-nor.com/blog/images/form_after.jpg" alt="" border="0" />
        </p>
        
        <p>
          <strong>注释:</strong>
        </p>
        
        <ul>
          <li>
            <em>Name</em> 和 <em>Email</em>字段都是必填项；因此他们不应该会出现在我们的报告中，因为如果不填写这两个字段的话人们将无法提交表单。
          </li>
          <li>
            评论字段的页面浏览数值非常高，高达154，这表明客户并没有兴趣填写表单中的这个字段。
          </li>
          <li>
            其他要做的事情由你决定，取决于商业性质和表单目标，解决方案也各不相同。
          </li>
          <li>
            从表单中移除某些字段，从而使它们更短更扼要，这是有道理的。
          </li>
          <li>
            另外一个选择是使用如<a id="idtagger25" href="http://www.google.com/websiteoptimizer" target="_blank">Google Website Optimizer</a>这样的工具来测试更短的版本。结果可能是更短的表单将会获得更短提交数，但是无任何影响也是有可能的。
          </li>
        </ul>
        
        <p>
          更新（异步跟踪代码）：
        </p>
        
        <pre>function validate()
{
isEntered(document.getElementById('name'),'name');
isEntered(document.getElementById('email'),'email');
isEntered(document.getElementById('phone'),'phone');
isEntered(document.getElementById('company'),'company');
isEntered(document.getElementById('comments'),'comments');

frm.action='/thankyou.aspx?src=contact_us.htm';
} 

function isEntered(el, field_name)
{
     if((el.value=="") || (el.value==null))
     {
	 _gaq.push(['_trackPageview', '/contact_us.htm/empty/'+field_name]);
     }

     else
     {
     return false;
     }
}</pre>
        
        <p>
          <span class='wp_keywordlink'><a href="http://www.yeezhe.com/" title="译者" target="_blank">译者</a></span><span class='wp_keywordlink'><a href="https://xiaoq.in/" title="肖庆" target="_blank">肖庆</a></span>原创翻译自：<a href="http://www.e-nor.com/blog/index.php/web-analytics/code-update-optimize-form-length-with-input-analysis/" target="_blank">http://www.e-nor.com/blog/index.php/web-analytics/code-update-optimize-form-length-with-input-analysis/</a>
        </p>