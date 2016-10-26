+++
date = "2016-10-26"
draft = false
title = " Hugo 内容之Sections"
categories=["Hugo"]
weight = 8
+++

Hugo认为，一般来说生成站点内容的结构和源内容结构都一样。
content为源内容结构的根目录，在这下面的所有直接子目录，都被当作Section  。

比如：下面的例子，使用两个sections，"post"和"quote"

        .
    └── content
        ├── post
        |   ├── firstpost.md       // <- http://1.com/post/firstpost/
        |   ├── happy
        |   |   └── ness.md        // <- http://1.com/post/happy/ness/
        |   └── secondpost.md      // <- http://1.com/post/secondpost/
        └── quote
            ├── first.md           // <- http://1.com/quote/first/
            └── second.md          // <- http://1.com/quote/second/


### Sections 列表
Hugo会根据目录的结构自动生成section。
当然也可以通过[List Templates](https://gohugo.io/templates/list/)）来自定义如何生成。

### Sections　和 Types
Sections and Types

By default everything created within a section will use the content type that matches the section name.

Section defined in the front matter have the same impact.

To change the type of a given piece of content, simply define the type in the front matter.

If a layout for a given type hasn’t been provided, a default type template will be used instead provided it exists.