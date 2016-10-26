+++
date = "2016-10-26"
draft = false
title = " Hugo配置"
categories=["Hugo"]
weight = 3
+++

*   [参考文档](https://gohugo.io/overview/configuration/#examples)  
### 配置方式
#### hugo环境变量
    env HUGO_TITLE="Some Title" hugo
#### 配置文件 
配置支持格式：  
* TOML
* YAML
* JSON

在这个配置文件里，可以通过配置参数，精确的指示hugo 如何渲染站点，同时，还可以定义菜单，以及其它一些全站范围内可以使用的参数。

* 配置变量

下面这些是配置文件当中可以配置的hugo变量，以及他们的默念值。

    ---
    archetypedir:               "archetype"
    # hostname (and path) to the root, e.g. http://spf13.com/
    baseURL:                    ""
    # include content marked as draft
    buildDrafts:                false
    # include content with publishdate in the future
    buildFuture:                false
    # include content already expired
    buildExpired:               false
    # enable this to make all relative URLs relative to content root. Note that this does not affect absolute URLs.
    relativeURLs:               false
    canonifyURLs:               false
    # config file (default is path/config.yaml|json|toml)
    config:                     "config.toml"
    contentdir:                 "content"
    dataDir:                    "data"
    defaultExtension:           "html"
    defaultLayout:              "post"
    # Missing translations will default to this content language
    DefaultContentLanguage:     "en"
    # Renders the default content language in subdir, e.g. /en/. The root directory / will redirect to /en/
    DefaultContentLanguageInSubdir: false
    disableLiveReload:          false
    # Do not build RSS files
    disableRSS:                 false
    # Do not build Sitemap file
    disableSitemap:             false
    # Build robots.txt file
    enableRobotsTXT:            false
    # Do not render 404 page
    disable404:                 false
    # Do not inject generator meta tag on homepage
    disableHugoGeneratorInject: false
    # edit new content with this editor, if provided
    editor:                     ""
    # Enable Emoji emoticons support for page content.
    # See www.emoji-cheat-sheet.com
    enableEmoji:                false
    # Show a placeholder instead of the default value or an empty string if a translation is missing
    enableMissingTranslationPlaceholders: false
    footnoteAnchorPrefix:       ""
    footnoteReturnLinkContents: ""
    # google analytics tracking id
    googleAnalytics:            ""
    languageCode:               ""
    layoutdir:                  "layouts"
    # Enable Logging
    log:                        false
    # Log File path (if set, logging enabled automatically)
    logFile:                    ""
    # "yaml", "toml", "json"
    metaDataFormat:             "toml"
    newContentEditor:           ""
    # Don't sync modification time of files
    noTimes:                    false
    paginate:                   10
    paginatePath:               "page"
    permalinks:
    # Pluralize titles in lists using inflect
    pluralizeListTitles:        true
    # Preserve special characters in taxonomy names ("Gérard Depardieu" vs "Gerard Depardieu")
    preserveTaxonomyNames:      false
    # filesystem path to write files to
    publishdir:                 "public"
    # enables syntax guessing for code fences without specified language
    pygmentsCodeFencesGuessSyntax: false
    # color-codes for highlighting derived from this style
    pygmentsStyle:              "monokai"
    # true: use pygments-css or false: color-codes directly
    pygmentsUseClasses:         false
    # default sitemap configuration map
    sitemap:
    # filesystem path to read files relative from
    source:                     ""
    staticdir:                  "static"
    # display memory and timing of different steps of the program
    stepAnalysis:               false
    # theme to use (located by default in /themes/THEMENAME/)
    themesdir:                  "themes"
    theme:                      ""
    title:                      ""
    # if true, use /filename.html instead of /filename/
    uglyURLs:                   false
    # Do not make the url/path to lowercase
    disablePathToLower:         false
    # if true, auto-detect Chinese/Japanese/Korean Languages in the content. (.Summary and .WordCount can work properly in CJKLanguage)
    hasCJKLanguage:             false
    # verbose output
    verbose:                    false
    # verbose logging
    verboseLog:                 false
    # watch filesystem for changes and recreate as needed
    watch:                      true
    ---


* 排除文件 
 

渲染的时候，排除的文件 。
比如：


    ignoreFiles = [ "\\.foo$", "\\.boo$" ]
    

* Configure Blackfriday rendering

Blackfriday 是Hugo的Markdown 渲染引擎。