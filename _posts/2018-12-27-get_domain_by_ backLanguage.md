---
layout: post
title: "怎么通过前端知道后台信息？？"
subtitle: "How do you know the background information through HTML？"
author: "乱码人生"
date: 2018-12-27 13:40:31
header-style: text
tags:
     - HTML
     - 杂七杂八
---

#### 1.通过域名了解后台信息（包括用什么语言、框架、服务器等）

> https://w3techs.com/sites/info/baidu.com(一个神奇的网站)

用法：只要把baidu.com 换成你想查找的域名就可以了.

效果：

![img](https://jiangdoc.github.io/blog/img/in-post/2018-12-27-get_domain_by_backLanguage/1.png)

#### 2.通过firebug或者chrome的开发者工具来查看网页的Response Headers

以chrome为例：

按：F12 后在要查看的页面中按F5刷新重新请求

效果：

![](https://jiangdoc.github.io/blog/img/in-post/2018-12-27-get_domain_by_backLanguage/2.png)

#### 3.通过网络请求扩展名来看

一般的情况看页面的后缀名

Server Side Includes 技术，拓展名为.shtml或.html或.htm 

PHP技术，拓展名为.php 

JSP技术，拓展名为.jsp或.jsf(JSF技术是JSP技术的拓展) 

ASP.NET技术，拓展名为.aspx (x 代表extension) 

ASP技术，拓展名为.asp

ColdFusion技术，拓展名为.cfc

