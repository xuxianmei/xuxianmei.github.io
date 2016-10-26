+++
date = "2016-10-26"
draft = false
title = "Hugo 内容之Archetypes"
categories=["Hugo"]
weight = 9
+++
主要用于，当使用hugo new命令创建新的内容文件时，自动产生相应的front matter 头部内容。

### 例子
* Creating an archetype

    **archetypes/default.md**
    
    
    +++
    tags = ["x", "y"]
    categories = ["x", "y"]
    +++

当创建时，会自动加上上面这些字符。

### 创建自定义格式
**archetypes/musician.md**
    
    +++
    name = ""
    bio = ""
    genre = ""
    +++
然后使用

    hugo new musician/mozart.md
    
这个时候，Hugo使用的不再是archetypes当中默认的。而是使用**archetypes/musician.md**。

#### 何时使用相应的archetype
当创建一个新内容文件时，有如下规则：
* 如果有一个archetype里的文件名与新创建的内容文件类型一样，会被使用。
* 如果没有，会使用 ==archetypes/default.md==
* 如果两个都没有，会使用主题里的
    * 在主题里，重复上面两个步骤

Hugo provides a simple archetype which sets the title (based on the file name) and the date in RFC 3339 format based on now(), which returns the current time.

>    Note: hugo new does not automatically add draft = true when the user provides an archetype. This is by design, rationale being that the archetype should set its own value for all fields. title and date, which are dynamic and unique for each piece of content, are the sole exceptions.
The content type is automatically detected based on the file path passed to the Hugo CLI command hugo new [my-content-type/post-name]. To override the content type for a new post, include the --kind flag during creation.