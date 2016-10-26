+++
date = "2016-10-26"
draft = false
title = " Hugo目录结构"
categories=["Hugo"]
weight = 2
+++

* archetypes 定义配置属性，无论hugo new 命令在何时使用，这些属性都会添加到 post front matter。

* config.toml 根目录下的配置文件，支持其它格式：YAML JSON。
* content 存放站点的的内容，可以创建子目录，相应的，站点会生成对应的sections。
* data 用来存放用来生成站点时，使用的配置的文件。
* layouts 布局文件，指定如何将content生成站点。
* static 存储静态文件，比如 css、javascript、images等其它静态内容。

#### 其它不同的目录和目的
* config [参考文档](https://gohugo.io/overview/configuration/)
* data [参考文档](https://gohugo.io/extras/datafiles/)
* i18n [参考文档](https://gohugo.io/content/multilingual/#translation-of-strings)
* archetypes [参考文档](https://gohugo.io/content/archetypes/)
* content [参考文档](https://gohugo.io/content/organization/)
* layouts [参考文档](https://gohugo.io/templates/overview/)
* static [参考文档](https://gohugo.io/themes/creation/#static)
* themes [参考文档](https://gohugo.io/themes/overview/)

