+++
date = "2016-10-26"
draft = false
title = "Hugo 内容之Ordering"
categories=["Hugo"]
weight = 11
+++

主要用来组织内容文件之间的排序问题

默认，排序参照：weight，然后date ，标题和链接标题也可以使用，排序相关主要在list template当中。
By default, content is ordered by weight, then by date with the most recent date first, but alternative sorting (by title and linktitle) is also available. The order the content would appear is specified in the list template.

**比如:**

    +++
    weight = 4
    title = "Three"
    date = "2012-04-06"
    +++
    Front Matter with Ordered Pages 3

* Ordering Content Within Taxonomies

Please see the [Taxonomy Ordering Documentation](https://gohugo.io/taxonomies/ordering/).
