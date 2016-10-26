
+++
date = "2016-10-26"
draft = false
title = "Hugo Taxonomies(分类)"
categories=["Hugo"]
weight = 14
+++
Taxonomies，Hugo用于支持用户自定义内容的分组、分类。

Taxonomies 提供了我们将内容分类和在内容之间建立联系的方法。

默认的taxonomies是tags和categories。
但是可以扩展和自定义。
当taxnonmies被使用时（同时提供了templates），Hugo会自动的创建页面列出所有的taxnonmies，以及他们之间所有的联系。

### 定义
* Taxonomy: 一个可以用于将内容分类编排的分类方法。

* Term: A key within that taxonomy

* Value: A piece of content assigned to that Term

### 例子

比如一个关于电影的站点，需要以下分类
* Actors
* Directors
* Stuidios
* Genre
* Year
* Awards

通过在在所有内容的fornt-matter提供以上分类的terms。
Hugo会自动根据这些产生分类的列表页面（根据以上分类）

分类组织
通过taxonomy的角度来看。

    Actor                    <- Taxonomy
        Bruce Willis         <- Term
            The Six Sense    <- Content
            Unbreakable      <- Content
            Moonrise Kingdom <- Content
        Samuel L. Jackson    <- Term
            Unbreakable      <- Content
            The Avengers     <- Content
            xXx              <- Content

通过content的角度的来看。视图会不太一样。但是，数据和分类都完全是一样的。

    Unbreakable                 <- Content
        Actors                  <- Taxonomy
            Bruce Willis        <- Term
            Samuel L. Jackson   <- Term
        Director                <- Taxonomy
            M. Night Shyamalan  <- Term
        ...
    Moonrise Kingdom            <- Content
        Actors                  <- Taxonomy
            Bruce Willis        <- Term
            Bill Murray         <- Term
        Director                <- Taxonomy
            Wes Anderson        <- Term