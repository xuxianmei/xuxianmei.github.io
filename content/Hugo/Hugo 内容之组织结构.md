+++
date = "2016-10-26"
draft = false
title = " Hugo内容之组织结构"
categories=["Hugo"]
weight = 5
+++

Huog在使用文件时，将front matter作为其头部。
Hugo推荐使用Organization来最小化额外配置，这些配置也可以在在front matter当中来重写。  

### Organization
在Hugo当中，不需要任何额外的配置，根据内容存放的目录结构自动生成相应的url。
Hugo支持内容文件存放在任何层级目录（都位于content目录下）。
最顶级目录被用作section。  

比如
    
    .
    └── content
        └── about
        |   └── index.md  // <- http://1.com/about/
        ├── post
        |   ├── firstpost.md   // <- http://1.com/post/firstpost/
        |   ├── happy
        |   |   └── ness.md  // <- http://1.com/post/happy/ness/
        |   └── secondpost.md  // <- http://1.com/post/secondpost/
        └── quote
            ├── first.md       // <- http://1.com/quote/first/
            └── second.md      // <- http://1.com/quote/second/
#### Destinations(生成的站点内容)

使用相同的内容结构来生成相同结构的站点内容。  

通过其它的设置可以达到特殊的控制。  

下面这些都可以进行相应的设置，同时后面的设置会覆盖前面的设置。

* filename

设置在文件在URL当中的name。不存在于 front matter。

* slug

在front matter当中定义，可以代替目标URL当中的filename。
* filepath

文件在硬盘当中的实际路径
* section

根据在硬盘当中的位置生成，不能在front matter当中生定义,
* type

类似section，但是可以在front matter当中定义。
* path

可以在front matter当中定义。path会替换文件在硬盘当中的实际路径。
目录地址同时会生成相同的path，包括setion
* url
完整的url。url会重写上面的所有。
url必须是相对baseURL的路径（以"/"开始）。
使用url会忽视 --uglyURLs设置。


### Hugo路径分解
* Content (原始内容)

    .             path           slug
    .       ⊢-------^----⊣ ⊢------^-------⊣
    content/extras/indexes/category-example/index.html
    
    
    .       section              slug
    .       ⊢--^--⊣        ⊢------^-------⊣
    content/extras/indexes/category-example/index.html
    
    
    .       section  slug
    .       ⊢--^--⊣⊢--^--⊣
    content/extras/indexes/index.html
    

* Destination（生成的页面）


    .           permalink
    ⊢--------------^-------------⊣
    http://spf13.com/projects/hugo
    
    
       baseURL       section  slug
    ⊢-----^--------⊣ ⊢--^---⊣ ⊢-^⊣
    http://spf13.com/projects/hugo
    
    
       baseURL       section          slug
    ⊢-----^--------⊣ ⊢--^--⊣        ⊢--^--⊣
    http://spf13.com/extras/indexes/example
    
    
       baseURL            path       slug
    ⊢-----^--------⊣ ⊢------^-----⊣ ⊢--^--⊣
    http://spf13.com/extras/indexes/example
    
    
       baseURL            url
    ⊢-----^--------⊣ ⊢-----^-----⊣
    http://spf13.com/projects/hugo
    
    
       baseURL               url
    ⊢-----^--------⊣ ⊢--------^-----------⊣
    http://spf13.com/extras/indexes/example
    
* section = 内容是什么类型的
    * 基于内容位置
    * front matter重新设置
* slug = 名称.ext 或者 名称/
    * 基于内容文件名称
    * front matter重新设置
* path = section + path + slug
    * 基于内容文件所处位置
* url = 相对 URL
    * 在front matter 定义
    * 重写上面所有
    