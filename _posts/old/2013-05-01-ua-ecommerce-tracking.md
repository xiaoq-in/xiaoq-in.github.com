---
title: UA电子商务跟踪（纯技术+代码）
author: 肖庆
layout: post
permalink: /google-analytics/ua-ecommerce-tracking/
ratings_users:
  - 0
ratings_score:
  - 0
ratings_average:
  - 0
views:
  - 1952
yourls_shorturl:
  - http://t.xiaoq.in/u
ta-thumbnail:
  - NoMediaFound
categories:
  - Google Analytics
tags:
  - GA
  - UA
  - 支付宝
  - 电子商务跟踪
---
<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%94%b5%e5%ad%90%e5%95%86%e5%8a%a1%e8%b7%9f%e8%b8%aa/" title="查看电子商务跟踪中的全部文章" target="_blank">电子商务跟踪</a></span>的代码部署是个技术活，不过并没有想象中的困难，作为一个没有学过代码的人，这几天接二连三地大概花了3小时，总算是给我的博客加上了一个新功能：<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e6%94%af%e4%bb%98%e5%ae%9d/" title="查看支付宝中的全部文章" target="_blank">支付宝</a></span>捐赠按钮+<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ua/" title="查看UA中的全部文章" target="_blank">UA</a></span><span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e7%94%b5%e5%ad%90%e5%95%86%e5%8a%a1%e8%b7%9f%e8%b8%aa/" title="查看电子商务跟踪中的全部文章" target="_blank">电子商务跟踪</a></span>。这个主要是借鉴“雷锋网”的。

这是完整的index.php代码（自行修改<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/%e6%94%af%e4%bb%98%e5%ae%9d/" title="查看支付宝中的全部文章" target="_blank">支付宝</a></span>即时到帐接口的文件，另外需要配置alipay.config.php这个文件）：

<!DOCTYPE html PUBLIC &#8220;-//W3C//DTD XHTML 1.0 Transitional//EN&#8221; &#8220;http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd&#8221;>  
<html>  
<head>  
<meta http-equiv=&#8221;Content-Type&#8221; content=&#8221;text/html; charset=utf-8&#8243;>  
<title>支付宝即时到账捐赠-<span class='wp_keywordlink'><a href="http://blog.xiaoq.in/" title="肖庆" target="_blank">肖庆</a></span></title>  
<?php  
/\* \*  
* 功能：即时到账交易接口接入页  
* 版本：3.3  
* 修改日期：2012-07-23  
* 说明：  
* 以下代码只是为了方便商户测试而提供的样例代码，商户可以根据自己网站的需要，按照技术文档编写,并非一定要使用该代码。  
* 该代码仅供学习和研究支付宝接口使用，只是提供一个参考。

\***\***\***\***\***\***\****\*\\*\*注意\*\*\***\***\***\***\***\***\*****  
* 如果您在接口集成过程中遇到问题，可以按照下面的途径来解决  
* 1、商户服务中心（https://b.alipay.com/support/helperApply.htm?action=consultationApply），提交申请集成协助，我们会有专业的技术工程师主动联系您协助解决  
* 2、商户帮助中心（http://help.alipay.com/support/232511-16307/0-16307.htm?sh=Y&info_type=9）  
* 3、支付宝论坛（http://club.alipay.com/read-htm-tid-8681712.html）  
* 如果不想使用扩展功能请把扩展功能参数赋空值。  
*/  
require(&#8216;../../wp-blog-header.php&#8217;);  
require_once(&#8220;alipay.config.php&#8221;);  
require\_once(&#8220;lib/alipay\_submit.class.php&#8221;);  
$post_id = $p;  
$queried\_post = get\_post($post_id);  
/\***\***\***\***\***\***\*****\*\\*\*请求参数\*\*\***\***\***\***\***\***\***\***/

//支付类型  
$payment_type = &#8220;1&#8243;;  
//必填，不能修改  
//服务器异步通知页面路径  
$notify\_url = &#8220;http://xiaoq.in/api/alipay/notify\_url.php&#8221;;  
//需http://格式的完整路径，不能加?id=123这类自定义参数

//页面跳转同步通知页面路径  
$return\_url = &#8220;http://xiaoq.in/api/alipay/return\_url.php&#8221;;  
//需http://格式的完整路径，不能加?id=123这类自定义参数，不能写成http://localhost/

//卖家支付宝帐户  
$seller_email = &#8220;g@xiaoq.in&#8221;;  
//必填

//商户订单号  
$out\_trade\_no = $p.date(&#8216;YmdHis&#8217;).rand(1000,2000);  
//商户网站订单系统中唯一订单号，必填  
//文章ID  
$p = $_GET["p"];  
$post\_permalink= post\_permalink($p);  
//订单名称  
$subject = $queried\_post->post\_title;  
//必填  
//付款金额  
$total\_fee = $\_GET["tf"];  
//必填

//订单描述  
$body = 评价《.$queried\_post->post\_title.》;  
//商品展示地址  
$show\_url = $post\_permalink;  
//需以http://开头的完整路径，例如：http://www.xxx.com/myorder.html

//防钓鱼时间戳  
$anti\_phishing\_key = &#8220;&#8221;;  
//若要使用请调用类文件submit中的query_timestamp函数

//客户端的IP地址  
$exter\_invoke\_ip = &#8220;&#8221;;  
//非局域网的外网IP地址，如：221.0.0.1  
/\***\***\***\***\***\***\***\***\***\***\***\***\***\***\***\***\***\***\***\***/  
//构造要请求的参数数组，无需改动  
$parameter = array(  
&#8220;service&#8221; => &#8220;create\_direct\_pay\_by\_user&#8221;,  
&#8220;partner&#8221; => trim($alipay_config['partner']),  
&#8220;payment\_type&#8221; => $payment\_type,  
&#8220;notify\_url&#8221; => $notify\_url,  
&#8220;return\_url&#8221; => $return\_url,  
&#8220;seller\_email&#8221; => $seller\_email,  
&#8220;out\_trade\_no&#8221; => $out\_trade\_no,  
&#8220;subject&#8221; => $subject,  
&#8220;total\_fee&#8221; => $total\_fee,  
&#8220;body&#8221; => $body,  
&#8220;show\_url&#8221; => $show\_url,  
&#8220;anti\_phishing\_key&#8221; => $anti\_phishing\_key,  
&#8220;exter\_invoke\_ip&#8221; => $exter\_invoke\_ip,  
&#8220;\_input\_charset&#8221; => trim(strtolower($alipay\_config['input\_charset']))  
);  
//建立请求  
$alipaySubmit = new AlipaySubmit($alipay_config);  
$html_text = $alipaySubmit->buildRequestForm($parameter,&#8221;get&#8221;, &#8220;确认&#8221;);  
require(&#8216;ga.php&#8217;);  
echo &#8220;</head><body>&#8221;.$html_text;  
?>  
</body>  
</html>

这是完整的<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ga/" title="查看GA中的全部文章" target="_blank">GA</a></span>+<span class='wp_keywordlink_affiliate'><a href="http://blog.xiaoq.in/tag/ua/" title="查看UA中的全部文章" target="_blank">UA</a></span>代码：

<?php  
echo &#8220;<!&#8211; <span class='wp_keywordlink'><a href="http://blog.xiaoq.in/google-analytics/" title="Google Analytics" target="_blank">Google Analytics</a></span> &#8211;>  
<script>  
var \_gaq = \_gaq || [];  
\_gaq.push(['\_setAccount', 'UA-28069997-1']);  
\_gaq.push(['\_trackPageview']);  
\_gaq.push(['\_addTrans',  
'$out\_trade\_no', // transaction ID - required  
'xiaoq.in', // affiliation or store name  
'$total_fee', // total - required  
'0', // tax  
'0', // shipping  
'', // city  
'', // state or province  
'' // country  
]);  
// add item might be called for every item in the shopping cart  
// where your ecommerce engine loops through each item in the cart and  
// prints out _addItem for each  
\_gaq.push(['\_addItem',  
'$out\_trade\_no', // transaction ID - required  
'$p', // SKU/code - required  
'$subject', // product name  
'blog', // category or variation  
'$total_fee', // unit price - required  
'1' // quantity - required  
]);  
\_gaq.push(['\_trackTrans']); //submits transaction to the Analytics servers  
(function() {  
var ga = document.createElement(&#8216;script&#8217;); ga.type = &#8216;text/javascript&#8217;; ga.async = true;  
ga.src = (&#8216;https:&#8217; == document.location.protocol ? &#8216;https://ssl&#8217; : &#8216;http://www&#8217;) + &#8216;.google-analytics.com/ga.js&#8217;;  
var s = document.getElementsByTagName(&#8216;script&#8217;)[0]; s.parentNode.insertBefore(ga, s);  
})();  
(function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){  
(i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),  
m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)  
})(window,document,&#8217;script&#8217;,&#8217;//www.google-analytics.com/analytics.js&#8217;,&#8217;ga&#8217;);  
ga(&#8216;create&#8217;, &#8216;UA-28069997-5&#8242;, &#8216;api.xiaoq.in&#8217;);  
ga(&#8216;send&#8217;, &#8216;pageview&#8217;);  
ga(&#8216;require&#8217;, &#8216;ecommerce&#8217;, &#8216;ecommerce.js&#8217;);  
ga(&#8216;ecommerce:addTransaction&#8217;, {  
&#8216;id&#8217;: &#8216;$out\_trade\_no&#8217;, // Transaction ID. Required.  
&#8216;affiliation&#8217;: &#8216;xiaoq.in&#8217;, // Affiliation or store name.  
&#8216;revenue&#8217;: &#8216;$total_fee&#8217;, // Grand Total.  
&#8216;shipping&#8217;: &#8217;0&#8242;, // Shipping.  
&#8216;tax&#8217;: &#8217;0&#8242; // Tax.  
});  
ga(&#8216;ecommerce:addItem&#8217;, {  
&#8216;id&#8217;: &#8216;$out\_trade\_no&#8217;, // Transaction ID. Required.  
&#8216;name&#8217;: &#8216;$subject&#8217;, // Product name. Required.  
&#8216;sku&#8217;: &#8216;$p&#8217;, // SKU/code.  
&#8216;category&#8217;: &#8216;blog&#8217;, // Category or variation.  
&#8216;price&#8217;: &#8216;$total_fee&#8217;, // Unit price.  
&#8216;quantity&#8217;: &#8217;1&#8242;, // Quantity.  
&#8216;currencyCode&#8217;: &#8216;CNY&#8217; // local currency code.  
});  
ga(&#8216;ecommerce:send&#8217;);  
</script>  
<!&#8211; End Google Analytics &#8211;>&#8221;  
?>

主要是需要了解一些WordPress的函数和基本的PHP代码逻辑，看得懂的可以直接借鉴，看不懂的也别问我了，咱不懂技术~

另外，按照UA电子商务跟踪的官方文档，以下是按照官方格式填的，这个的灵活性更大些，一次预定义，之后就可以很方便的引用了，也可参考下：

<?php  
// Transaction Data  
$trans = array(&#8216;id&#8217;=>$out\_trade\_no, &#8216;affiliation&#8217;=>&#8217;xiaoq.in&#8217;,  
&#8216;revenue&#8217;=>$total_fee, &#8216;shipping&#8217;=>&#8217;0&#8242;, &#8216;tax&#8217;=>&#8217;0&#8242;);

// List of Items Purchased.  
$items = array(  
array(&#8216;sku&#8217;=>$p, &#8216;name&#8217;=>$subject, &#8216;category&#8217;=>&#8217;blog&#8217;, &#8216;price&#8217;=>$total_fee, &#8216;quantity&#8217;=>&#8217;1&#8242;),  
);  
// Function to return the JavaScript representation of a TransactionData object.  
function getTransactionJs(&$trans) {  
return <<<HTML  
ga(&#8216;ecommerce:addTransaction&#8217;, {  
&#8216;id&#8217;: &#8216;{$trans['id']}&#8217;,  
&#8216;affiliation&#8217;: &#8216;{$trans['affiliation']}&#8217;,  
&#8216;revenue&#8217;: &#8216;{$trans['revenue']}&#8217;,  
&#8216;shipping&#8217;: &#8216;{$trans['shipping']}&#8217;,  
&#8216;tax&#8217;: &#8216;{$trans['tax']}&#8217;  
});  
HTML;  
}

// Function to return the JavaScript representation of an ItemData object.  
function getItemJs(&$transId, &$item) {  
return <<<HTML  
ga(&#8216;ecommerce:addItem&#8217;, {  
&#8216;id&#8217;: &#8216;$transId&#8217;,  
&#8216;name&#8217;: &#8216;{$item['name']}&#8217;,  
&#8216;sku&#8217;: &#8216;{$item['sku']}&#8217;,  
&#8216;category&#8217;: &#8216;{$item['category']}&#8217;,  
&#8216;price&#8217;: &#8216;{$item['price']}&#8217;,  
&#8216;quantity&#8217;: &#8216;{$item['quantity']}&#8217;  
});  
HTML;  
}  
?>  
<!&#8211; Google Analytics &#8211;>  
<script>  
(function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){  
(i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),  
m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)  
})(window,document,&#8217;script&#8217;,&#8217;//www.google-analytics.com/analytics.js&#8217;,&#8217;ga&#8217;);  
ga(&#8216;create&#8217;, &#8216;UA-28069997-5&#8242;, &#8216;api.xiaoq.in&#8217;);  
ga(&#8216;send&#8217;, &#8216;pageview&#8217;);&#8221;  
ga(&#8216;require&#8217;, &#8216;ecommerce&#8217;, &#8216;ecommerce.js&#8217;);  
<?php  
echo getTransactionJs($trans);  
foreach ($items as &$item) {  
echo getItemJs($trans['id'], $item);  
}  
?>  
ga(&#8216;ecommerce:send&#8217;);  
</script>  
<!&#8211; End Google Analytics &#8211;>

如果你是一个电子出版机构并且使用WordPress作为CMS系统，还想接受一些捐赠，或者希望实现付费阅读；同时你希望对这些数据进行跟踪和分析，了解用户的口味，那么以上这些代码或许对你有用。当然，你也可以把以上的代码作为电子商务跟踪代码的模版，让技术依葫芦画瓢填充其中的变量。