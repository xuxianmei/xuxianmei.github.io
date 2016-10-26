+++
date = "2016-10-26"
draft = false
title = " Hugo 内容之Front Matter"
categories=["Hugo"]
weight = 6
+++

增强Hugo的特性之一。
主要用于为content添加和设置需要使用到的元数据。
### 支持格式
* TOML 通过'+++'识别
* YAML 通过'---'识别
* JSON 通过 '{ }' 大括号对
### 例子：
#### TOML
    +++
    title = "spf13-vim 3.0 release and new website"
    description = "spf13-vim is a cross platform distribution of vim plugins and resources for Vim."
    tags = [ ".vimrc", "plugins", "spf13-vim", "vim" ]
    date = "2012-04-06"
    categories = [
      "Development",
      "VIM"
    ]
    slug = "spf13-vim-3-0-release-and-new-website"
    +++
    这以后存放文件的内容content

#### YAML

    ---
    title: "spf13-vim 3.0 release and new website"
    description: "spf13-vim is a cross platform distribution of vim plugins and resources for Vim."
    tags: [ ".vimrc", "plugins", "spf13-vim", "vim" ]
    lastmod: 2015-12-23
    date: "2012-04-06"
    categories:
      - "Development"
      - "VIM"
    slug: "spf13-vim-3-0-release-and-new-website"
    ---
    这以后存放文件的内容content
    
#### JSON
         {
            "title": "spf13-vim 3.0 release and new website",
            "description": "spf13-vim is a cross platform distribution of vim plugins and resources for Vim.",
            "tags": [ ".vimrc", "plugins", "spf13-vim", "vim" ],
            "date": "2012-04-06",
            "categories": [
                "Development",
                "VIM"
            ],
            "slug": "spf13-vim-3-0-release-and-new-website"
    }
        
        这以后存放文件的内容content
        
### 变量
Hugo已经预定义了一些变量。用户也可以创建任何想要的变量。
自定义的变量存放到Params当中。字段名称一般小写。
比如：

    Params:
        camelCase:true
        
### 必需变量
* **title** 内容的标题
* **description** 内容的描述
* **date** 将来用来排序的时间
* **taxonomies** 使用 tags和categories 的字段值。
### 可选变量
* **aliases**  An array of one or more aliases (e.g. old published path of a renamed content) that would be created to redirect to this content. See Aliases for details.
* **draft** If true, the content will not be rendered unless hugo is called with --buildDrafts
* **publishdate** If in the future, content will not be rendered unless hugo is called with --buildFuture
* **expirydate** Content already expired will not be rendered unless hugo is called with --buildExpired
* **type** The type of the content (will be derived from the directory automatically if unset)
* **isCJKLanguage** If true, explicitly treat the content as CJKLanguage (.Summary and .WordCount can work properly in CJKLanguage)
* **weight** Used for sorting
* **markup** (Experimental) Specify "rst" for reStructuredText (requires rst2html) or "md" (default) for Markdown
* **slug** appears as tail of the url. It can be used to change the part of the url that is based on the filename.
* **url** The full path to the content from the web root. It makes no assumptions about the path of the content file. It also ignores any language prefixes of the multilingual feature.

如果slug和url都没有设置，filename会被使用。

### 其它设置：

* Configure Blackfriday rendering