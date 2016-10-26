
+++
date = "2016-10-26"
draft = false
title = "Hugo主题"
categories=["Hugo"]
weight = 13
+++
### 安装
将主题下载：git或者其它方式，放到themes对应的目录当中去。

### 使用
假设主题放在的目录为themes/theme_beauty。
* 两种方法 ：
    * 生成站点时通过命令使用
    
        hugo -t theme_beauty   
    * 在配置文件当中使用
    
        theme : theme_beauty


### 自定义主题 
#### 替换静态文件
比如：当前使用的主题当中的具有此静态文件

    /themes/themename/static/js/jquery.min.js
    
可以通过以下文件替换

    /static/js/jquery.min.js
#### 替换单条模板文件
比如：

    /themes/themename/layouts/_default/single.html
    
可以通过以下文件替换

    /layouts/_default/single.html
    
#### 替换一个架构

使用/archetypes当中的文件来替换，或者直接复制一个主题的archetypes到此来进行修改使用。

#### 注意Default

**Default** 在Hugo当中，可以通过一些本地文件来替换掉其它主题当中使用的视图等。



### 主题创建
可以通过hugo new来创建新主题
    
    hugo new theme [name] 
    

    
#### 主题的主要组件
##### Layouts
Hugo建立在各个东西越简单越好的概念上。  

基本上，站点内容主要有两种显示方式：
*  a single piece of content
*  a list of content items

##### Single Content
默认的single file layout存放在 layouts/_default/single.html
##### List of Contents
默认的 list file layout存放在
layouts/_default/list.html
##### Partial Templates
主要用于为了扩展的分部视图，单独组件化，方便修改小部分的内容。便于最小化管理和未来的兼容。
##### Static
站点渲染时，需要用到的所有静态文件 。

    /css
    /js
    /img
    
##### Archetypes
如果需要通过主题，将一些值放到front matter当中。
最好的方法是为每种content type提供一个archetype。
具体参考Hugo Content archetype。
##### Generator meta tag 
通过.Hugo.Generator 放在HTML的 head区域，帮助分析Hugo的使用和人气。