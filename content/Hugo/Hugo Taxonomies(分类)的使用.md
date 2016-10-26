+++
date = "2016-10-26"
draft = false
title = "Hugo Taxonomies(分类)的使用"
categories=["Hugo"]
weight = 15
+++

#### 定义一个站点的分类

分类标准需要在被使用前，提前在站点当中配置。  

比如：在config.toml当中配置
    
    [taxonomies]
    tag = "tags"
    category = "categories"
    series = "series"
    
或者在config.yaml当中配置

    taxonomies:
      tag: "tags"
      category: "categories"
      series: "series"
    
网站现在会根据Cotent当中fronat-matter设置的
tags catgories series的值来进行自动的分类。

比如：
Front Matter Example (in TOML)

    +++
    title = "Hugo: A fast and flexible static site generator"
    tags = [ "Development", "Go", "fast", "Blogging" ]
    categories = [ "Development" ]
    series = [ "Go Web Dev" ]
    slug = "hugo"
    project_url = "https://github.com/spf13/hugo"
    +++