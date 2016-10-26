+++
date = "2016-10-26"
draft = false
title = "Hugo 内容之Summaries"
categories=["Hugo"]
weight = 12
+++
### 摘要
通过.Summary 页面变量，Hugo能够根据为内容产生相应的摘要，用来在摘要视图上显示。  

摘要根据定义的截取方式来截取一个片段的内容，作为摘要显示。  

内容摘要，通过.RelPermalink or .Permalink 变量，将原始内容的链接附加到"阅读更多"上。
同时，通过.Truncated  变量，可以设置阅读更多是否显示。

### Hugo 默认截取
默认，会截取前面70个字符作为.Summary变量的值。
.Summary 可以在 templates当中使用。

其它更多，[参考官方文档](https://gohugo.io/content/summaries/)