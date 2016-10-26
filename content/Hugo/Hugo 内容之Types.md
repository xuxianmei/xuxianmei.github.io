+++
date = "2016-10-26"
draft = false
title = "Hugo 内容之Types"
categories=["Hugo"]
weight = 10
+++

Hugo 支持众多不同的格式的文件内容。

每一种内容格式，都有唯一的一套元数据设置、模块以及可以通过 content archetypes的数据用hugo new命令创建。

    hugo new [my-content-type/post-name]
比如：

    hugo new post/my-newest-post.md
    
post 为type my-newest-post为名称
当需要使用一种新的格式时，支持新的一种格式，主要有如下步骤：

* 创建类型目录

根据新格式的名称，在layouts创建目录。
比如：/layouts/post

* 创建单个模板

创建single.html文件在刚刚创建的目录当中。
比如：/layouts/post/single.html
* 创建列表模板

Create a file called post.html inside the section lists template directory, /layouts/section. E.g. /layouts/section/post.html

* 创建 views

Many sites support rendering content in a few different ways, for instance, a single page view and a summary view to be used when displaying a list of contents on a single page. Hugo makes no assumptions here about how you want to display your content, and will support as many different views of a content type as your site requires. All that is required for these additional views is that a template exists in each /layouts/TYPE directory with the same name


* 创建对应的架构（archetype）

Create a file called type.md in the /archetypes directory. E.g. /archetypes/post.md.

==**注：以上操作全部都是可选的，如果没有对应的文件，那么Hugo会使用普通的templates和默认的archetype。**==