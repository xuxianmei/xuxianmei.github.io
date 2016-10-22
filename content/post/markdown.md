+++
date = "2016-04-24T16:56:42+08:00"
draft = false
title = " Markdown语法总结"
+++

## 语法介绍
 
### 区块元素



  一个 Markdown 段落是由一个或多个连续的文本行组成，它的前后要有一个以上的空行（空行的定义是显示上看起来像是空的，便会被视为空行。比方说，若某一行只包含空格和制表符，则该行也会被视为空行）。普通段落不该用空格或制表符来缩进。  
  
Markdown 允许段落内的强迫换行（插入换行符），如果你确实想要依赖 Markdown 来插入 <br \/> 标签的话，在插入处先按入两个以上的空格然后回车。    

但是简单地 [ 每个换行都转换为 <br \/> ] 的方法在 Markdown 中并不适合， Markdown 中 email 式的 **区块引用** 和 多段落的 **列表** 在使用换行来排版的时候，不但更好用，还更方便阅读。

#### 标题
	# 这是 H1
	## 这是 H2
	###### 这是 H6
#### 区块引用
Markdown 标记区块引用是使用类似 email 中用 > 的引用方式。如果你还熟悉在 email 信件中的引言部分，你就知道怎么在 Markdown 文件中建立一个区块引用，那会看起来像是你自己先断好行，然后在每行的最前面加上 >  ，下面这个就是使用了区块引用现实的的效果。
> This is a blockquote with two paragraphs. Lorem ipsum dolor sit amet,
> consectetuer adipiscing elit. Aliquam hendrerit mi posuere lectus.
> Vestibulum enim wisi, viverra nec, fringilla in, laoreet vitae, risus.

区块引用可以嵌套（例如：引用内的引用），只要根据层次加上不同数量的 > ：

	> This is the first level of quoting.
	>
	> > This is nested blockquote.
	>
	> Back to the first level.
引用的区块内也可以使用其他的 Markdown 语法，包括标题、列表、代码区块等：
#### 列表
Markdown 支持有序列表和无序列表。

无序列表使用星号、加号或是减号作为列表标记：
	
	* 列表1
	* 列表2 	
	* 列表3  
等同于：

	*   Red
	*   Green
	*   Blue
也等同于：
	
	-   Red
	-   Green
	-   Blue
有序列表则使用数字接着一个英文句点：
	
	1.  Bird	
	2.  McHale
	3.  Parish	
列表项目标记通常是放在最左边，但是其实也可以缩进，最多 3 个空格，项目标记后面则一定要接着至少一个空格或制表符。
要让列表看起来更漂亮，你可以把内容用固定的缩进整理好：
	
	*   Lorem ipsum dolor sit amet, consectetuer adipiscing elit.
	    Aliquam hendrerit mi posuere lectus. Vestibulum enim wisi,
	    viverra nec, fringilla in, laoreet vitae, risus.
	*   Donec sit amet nisl. Aliquam semper ipsum sit amet velit.
	    Suspendisse id sem consectetuer libero luctus adipiscing.
		
列表项目可以包含多个段落，每个项目下的段落都必须缩进 4 个空格或是 1 个制表符：
		
	1.  This is a list item with two paragraphs. Lorem ipsum dolor
	    sit amet, consectetuer adipiscing elit. Aliquam hendrerit
	    mi posuere lectus.
	
	    Vestibulum enim wisi, viverra nec, fringilla in, laoreet
	    vitae, risus. Donec sit amet nisl. Aliquam semper ipsum
	    sit amet velit.
	
	2.  Suspendisse id sem consectetuer libero luctus adipiscing.
如果要在列表项目内放进引用，那 > 就需要缩进：
	
	*   A list item with a blockquote:
	
	    > This is a blockquote
	    > inside a list item.
如果要放代码区块的话，该区块就需要缩进两次，也就是 8 个空格或是 2 个制表符:	

	*   一列表项包含一个列表区块：
        <代码写在这>
#### 代码区块
和程序相关的写作或是标签语言原始码通常会有已经排版好的代码区块，通常这些区块我们并不希望它以一般段落文件的方式去排版，而是照原来的样子显示，Markdown 会用 <pre\> 和 <code\> 标签来把代码区块包起来。 

要在 Markdown 中建立代码区块很简单，只要简单地缩进 4 个空格或是 1 个制表符就可以，例如，下面的输入：
	
	这是一个普通段落：
		这是一个代码区块。
Markdown 会转换成：

	<p>这是一个普通段落：</p>	
	<pre><code>这是一个代码区块。
	</code></pre>
这个每行一阶的缩进（4 个空格或是 1 个制表符），都会被移除，例如：
	
	Here is an example of AppleScript:
	    tell application "Foo"
	        beep
	    end tell	   
会被转换为：

	<p>Here is an example of AppleScript:</p>
	<pre><code>tell application "Foo"
 	   beep
	end tell
	</code></pre>
一个代码区块会一直持续到没有缩进的那一行（或是文件结尾）。
#### 分隔线

你可以在一行中用三个以上的星号、减号、底线来建立一个分隔线，行内不能有其他东西。你也可以在星号或是减号中间插入空格。下面每种写法都可以建立分隔线： 

	* * *
	***	
	*****	
	- - -	
	---------------------------------------
### 区段元素
####链接
Markdown 支持两种形式的链接语法： **行内式**和**参考式**两种形式。
不管是哪一种，链接文字都是用 **[方括号]** 来标记。

要建立一个**行内式**的链接，只要在方块括号后面紧接着圆括号并插入网址链接即可，如果你还想要加上链接的 title 文字，只要在网址后面，用双引号把 title 文字包起来即可，例如：
	
	This is [an example](http://example.com/ "Title") inline link.
	[This link](http://example.net/) has no title attribute.
会产生：

	<p>This is <a href="http://example.com/" title="Title">
	an example</a> inline link.</p>
	<p><a href="http://example.net/">This link</a> has no
	title attribute.</p>
**参考式**的链接是在链接文字的括号后面再接上另一个方括号，而在第二个方括号里面要填入用以辨识链接的标记：

	This is [an example][id] reference-style link.
接着，在文件的任意处，你可以把这个标记的链接内容定义出来：

	[id]: http://example.com/  "Optional Title Here"
链接内容定义的形式为：
> * 方括号（前面可以选择性地加上至多三个空格来缩进），里面输入链接文字
> * 接着一个冒号
> *接着一个以上的空格或制表符
> * 接着链接的网址
> * 选择性地接着 title 内容，可以用单引号、双引号或是括弧包着


下面这三种链接的定义都是相同：
	
		[foo]: http://example.com/  "Optional Title Here"
		[foo]: http://example.com/  'Optional Title Here
		[foo]: http://example.com/  (Optional Title Here)
隐式链接标记功能让你可以省略指定链接标记，这种情形下，链接标记会视为等同于链接文字，要用隐式链接标记只要在链接文字后面加上一个空的方括号，如果你要让 "Google" 链接到 google.com，你可以简化成：

	[Google][]
然后定义链接内容：

	[Google]: http://google.com/
由于链接文字可能包含空白，所以这种简化型的标记内也许包含多个单词：

	Visit [Daring Fireball][] for more information.
然后接着定义链接：

	[Daring Fireball]: http://daringfireball.net/
链接的定义可以放在文件中的任何一个地方，我比较偏好直接放在链接出现段落的后面，你也可以把它放在文件最后面，就像是注解一样。

下面是一个参考式链接的范例：

	I get 10 times more traffic from [Google] [1] than from
	[Yahoo] [2] or [MSN] [3].

 	[1]: http://google.com/        "Google"
 	[2]: http://search.yahoo.com/  "Yahoo Search"
 	[3]: http://search.msn.com/    "MSN Search"
上面两种写法都会产生下面的 HTML。

	<p>I get 10 times more traffic from <a href="htt				p://google.com/"
	title="Google">Google</a> than from
	<a href="http://search.yahoo.com/" title="Yahoo Se	arch">Yahoo</a>
	or <a href="http://search.msn.com/" title="MSN Sea	rch">MSN</a>.</p>


下面是用行内式写的同样一段内容的 Markdown 文件，提供作为比较之用：

	I get 10 times more traffic from [Google](http://g	oogle.com/ "Google")
	than from [Yahoo](http://search.yahoo.com/ "Yahoo 	Search") or
	[MSN](http://search.msn.com/ "MSN Search").
参考式的链接其实重点不在于它比较好写，而是它比较好读，比较一下上面的范例，使用参考式的文章本身只有 81 个字符，但是用行内形式的却会增加到 176 个字元，如果是用纯 HTML 格式来写，会有 234 个字元，在 HTML 格式中，标签比文本还要多。

使用 Markdown 的参考式链接，可以让文件更像是浏览器最后产生的结果，让你可以把一些标记相关的元数据移到段落文字之外，你就可以增加链接而不让文章的阅读感觉被打断。

#### 强调
Markdown 使用星号（*）和底线（_）作为标记强调字词的符号，被 \* 或 _ 包围的字词会被转成用 <em\> 标签包围，用两个 * 或 _ 包起来的话，则会被转成 \<strong\>，例如：
	
	*single asterisks*
	_single underscores_
	**double asterisks**
	__double underscores__
会转成：

	<em>single asterisks</em>
	<em>single underscores</em>
	<strong>double asterisks</strong>
	<strong>double underscores</strong>


#### 代码


如果要标记一小段行内代码，你可以用反引号把它包起来（`），例如：

	Use the `printf()` function.
会产生：

	<p>Use the <code>printf()</code> function.</p>
如果要在代码区段内插入反引号，你可以用多个反引号来开启和结束代码区段：

	``There is a literal backtick (`) here.``
这段语法会产生：

	<p><code>There is a literal backtick (`) here.</code></p>

代码区段的起始和结束端都可以放入一个空白，起始端后面一个，结束端前面一个，这样你就可以在区段的一开始就插入反引号：
	
	A single backtick in a code span: `` ` ``

	A backtick-delimited string in a code span: `` `foo` ``
会产生：
	
	<p>A single backtick in a code span: <code>`</code></p>

	<p>A backtick-delimited string in a code span: <code>`foo`</code></p>

#### 图片
很明显地，要在纯文字应用中设计一个「自然」的语法来插入图片是有一定难度的。
Markdown 使用一种和链接很相似的语法来标记图片，同样也允许两种样式： **行内式** 和 **参考式**。

行内式的图片语法看起来像是：

	![Alt text](/path/to/img.jpg)

	![Alt text](/path/to/img.jpg "Optional title")
详细叙述如下：
> * 一个惊叹号 !
> * 接着一个方括号，里面放上图片的替代文字
> * 接着一个普通括号，里面放上图片的网址，最后还可以用引号包住并加上 选择性的 'title' 文字。

参考式的图片语法则长得像这样：

	![Alt text][id]
「id」是图片参考的名称，图片参考的定义方式则和连结参考一样：

	[id]: url/to/image  "Optional title attribute"
到目前为止， Markdown 还没有办法指定图片的宽高，如果你需要的话，你可以使用普通的 <img> 标签。
### 其它
#### 自动链接
Markdown 支持以比较简短的自动链接形式来处理网址和电子邮件信箱，只要是用方括号包起来， Markdown 就会自动把它转成链接。一般网址的链接文字就和链接地址一样，例如：

	<http://example.com/>
Markdown 会转为：

	<a href="http://example.com/">http://example.com/</a>
#### 反斜杠

Markdown 可以利用反斜杠来插入一些在语法中有其它意义的符号，例如：如果你想要用星号加在文字旁边的方式来做出强调效果（但不用 <em> 标签），你可以在星号的前面加上反斜杠：

	\*literal asterisks\*
Markdown 支持以下这些符号前面加上反斜杠来帮助插入普通的符号：
	
	\   反斜线
	`   反引号
	*   星号
	_   底线
	{}  花括号
	[]  方括号
	()  括弧
	#   井字号
	+   加号
	-   减号
	.   英文句点
	!   惊叹号

`注：排版布局、段落啥的，主要使用区块引用和列表来完成。`
文章引用:http://www.appinn.com/markdown/#precode

 