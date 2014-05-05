---
layout: post
title: Piwik系列教程之：环境搭建
permalink: /piwik/environment/
category : Piwik
tags : [Piwik, AWS, EC2, RDS, Ubuntu, Debian]
---
{% include JB/setup %}


Piwik是一款免费开源的网站数据分析工具，其知名度和受欢迎程度不亚于博客界的WordPress。下面，我们就来介绍下这款工具，本文先从环境搭建开始。

搭建环境以AWS的EC2为例，Amazon提供一年的免费试用（其中有很多注意事项，一不小心就会被扣费，咱已经交了好几美金的学费，终于算是理清了）。AWS的申请流程网上一大堆，这里不再累赘。

Ubuntu在前不久出了新版本14.04 LTS，刚好它也是AWS的free tier所支持的，由于个人习惯于debian/ubuntu系统，因此以之为例。

如果你对数据库并不太熟悉，并且希望快速上手，建议使用RDS服务，除非你是专业的DBA，RDS在大多数情况下是够用的，国外的一些benchmark得出的结论也是，如果数据量不是非常大并对MySQL进行了专业的优化，两者在效率方面差异也并不会大。使用RDS可以节省很多运维方面的工作，比如主从同步，数据备份与恢复等，并且可以减少数据库操作对EC2的压力。使用RDS的话，一定记得使用与EC2一样的available zone，并且使用内网IP进行数据库连接，不然会被扣费，虽然很便宜，才0.01美金/GB。

另外，你还可以使用cloudfront对js文件进行CDN加速，使用s3来保存数据库备份文件，并将历史备份数据存放在Glacier中，cloudfront较贵（不在免费试用范围），S3比较便宜，Glacier用来保存不常使用的大文件，非常便宜。

如果你网站有使用SSL证书的话，最便宜的SSL证书也仅需4.99美金/年，nginx中设置也比较简单，网上教程一大把。

Piwik在前不久发布了[Debian的官方源](http://debian.piwik.org/)，因此，我们可以使用它来快速安装，安装方法非常简单，几个命令就搞定了：

```
sudo -i

sudo nano etc/apt/sources.list.d/piwik.list
```
加入以下两行：

```
deb http://debian.piwik.org/ piwik main

deb-src http://debian.piwik.org/ piwik main
```
```
sudo apt-get update

sudo apt-get install piwik
```

安装完成后，会生成2个文件夹：

/ect/piwik //存放Piwik核心程序

/usr/share/piwik //存放配置文件

推荐使用Nginx，个人不太喜欢使用一键安装包，手动安装其实也挺简单的，并且可定制性强，不用担心存在漏洞或者没用的东西占用内存。

在服务器设置的入门教程中，[DigitalOcean](https://www.digitalocean.com/?refcode=6b173b2d7e5e
)（AWS之外，个人推荐的另外一个云服务，不贵并且容易使用，话说AWS的价格算法相对复杂点）有一个不错的资料库，其中的[这篇文章](https://www.digitalocean.com/community/articles/how-to-install-linux-nginx-mysql-php-lemp-stack-on-ubuntu-14-04)就教我们如何在Ubuntu 14.04中安装Nginx+PHP环境。
 
需要额外注意以下几点：

1.nginx中主机的conf文件中root设置为：

```
root /usr/share/piwik
```

2.文件夹的权限设置，使用下面两个命令：


```
chown -R www-data:www-data /usr/share/piwik

chmod -R 0755 /usr/share/piwik
```

3.启用GeoIP (PECL)

```
sudo apt-get install php5-geoip php5-dev libgeoip-dev

sudo pecl install geoip

sudo nano /etc/php5/mods-available/geoip.ini
```

加入以下配置：

```
geoip.custom_directory=/usr/share/piwik/misc
```


安装完成后，建议查看“检查系统”看下当前是否存在什么问题，有则改之。不过，如果你使用RDS的话，LOAD DATA INFILE会提示出错，这是没有问题的。

除此之外，你还可以对nginx的配置进行一些性能调优，做安全防护、服务监控之类的，水太深，不在本文范畴之内。

好吧，有点偏技术，不过懂技术的童鞋可能觉得有点啰嗦。

如果你使用虚拟主机，控制面板为cPanel之类的，那么使用其内置的Piwik一键安装程序也是一个不错的选择，可以设置自动更新、自动备份和归档的计划任务等。不过，如果你的网站流量非常大，比如日PV超过10万，那么最好用VPS、云主机或者独立服务器吧。

基本的生产环境已经OK了，根据复杂程度，大概的成本可能会是：

1.几天的服务器配置时间

2.每年几百、几千或者几万块钱的服务器托管成本

3.DBA人员的日常管理维护成本

请记住：这个步骤非常重要，它是对数据精准性的重要保障，主要考验的是DBA的运维能力。

这步有问题，后面都是浪费时间，并引起决策偏差等一系列连锁反应。

除此之外，我们还应该花更多的时间、精力以及预算（Avinash大师的建议，黄金配比是[1:9](http://www.kaushik.net/avinash/the-10-90-rule-for-magnificient-web-analytics-success/)）在工具的使用上面，这样才能更好地发挥其价值，且听下回分解。
