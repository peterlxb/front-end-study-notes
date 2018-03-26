# HTML的概念:

HTML，全称“Hyper Text Markup Language\(超文本标记语言\)”，简单来说，网页就

是用 HTML 语言制作的。HTML 是一门描述性语言，是一门非常容易入门的语言。

使用标记标签来描述网页

## 文档声明:

&lt;!DOCTYPE HTML&gt;声明这是一个 HTML 文档。

HTML也有多个不同的版本，只有完全明白页面中使用的确切HTML版本，浏览器才能完全正确地显示 出HTML页面。这就是&lt;!DOCTYPE&gt;的用处。

&lt;!DOCTYPE&gt;不是HTML标签。它为浏览器提供一项信息\(声明\)，即HTML是用什么版本编写的。

HTML4.01 文档声明:

```
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN"
"http://www.w3.org/TR/html4/loose.dtd">
```

HTML5 文档声明:  
&lt;!DOCTYPE html&gt;

##  文档头部:

  
head 标签是页面的“头部”，只能定义一些特殊的内容。

```
一般来说，只有 6 个标签能放在<head>标签内:
```

| &lt;head&gt;内部标签 | 说明 |
| :--- | :--- |
| &lt;title&gt; | 定义网页的标题 |
| &lt;meta&gt; | 定义网页的基本信息\(供搜索引擎\) |
| &lt;style&gt; | 定义 CSS 样式 |
| &lt;link&gt; | 链接外部 CSS 文件或脚本文件，以及 favicon 样式 |
| &lt;script&gt; | 定义脚本语言 |
| &lt;base&gt; | 定义页面所有链接的基础定位 |



文档主体&lt;body&gt;&lt;body&gt;标签内可以放置各种标签。

## HTML标签

HTML标签通常是成对出现的，比如&lt;b&gt;和&lt;/b&gt;

       标签对中的第一个标签是开始标签，第二个标签是结束标签  

       开始和结束标签也被称为开放标签和闭合标签

HTML标签书写规范:

       标签统一用小写;

       属性值用双引号;

       嵌套缩进。

HTML常用属性\(全局属性\):

        id  
        class

       Style

       Title

HTML标记标签通常被称为HTML标签\(HTML tag\)。

## HTML标签语义化:

标签的用途:语义化，让网页更好的被搜索引擎理解。 什么叫做语义化呢，说的通俗点就是:明白每个标签的用途\(在什么情况下使用此标签合理\) 比如，网页上的文章的标题就可以用标题标签，网页上的各个栏目的栏目名称也可以使用标 题标签。文章中内容的段落就得放在段落标签中，在文章中有想强调的文本，就可以使用 em 标签表示强调等等。 语义化可以带来的好处  
 更容易被搜索引擎收录\(SEO\)。更容易让屏幕阅读器读出网页内容\(可访问性\)。代码可读性

HTML常用标签  
HTML常见的标签，如下图所示，记住常用标签的用法、作用即可。

实体字符

在 HTML 中，某些字符是预留的。

在 HTML 中不能使用小于号\(&lt;\)和大于号\(&gt;\)，这是因为浏览器会误认为它们是标签。

如果希望正确地显示预留字符，我们必须在 HTML 源代码中使用字符实体\(character entities\)。 字符实体类似这样:

&entity\_name;

如需显示小于号，我们必须这样写:&lt;或&\#60;或&\#060;  
一个字符实体\(Character Entity\)分成三部分:第一部分是一个&符号，英文叫 ampersand; 第二部分是实体\(Entity\)名字或者是\#加上实体\(Entity\)编号;第三部分是一个分号。

用实体\(Entity\)名字的好处是比较好理解，一看 lt，大概就猜出是 less than 的意思，但是其 劣势在于并不是所有的浏览器都支持最新的 Entity 名字。而实体\(Entity\)编号，各种浏览器 都能处理。

显示结果

|  | 描述 | 实体名称 | 实体编号 |
| :--- | :--- | :--- | :--- |
|  | 空格 | &nbsp; | &\#160; |
| &lt; | 小于号 | &lt; | &\#6 |

| &gt; | 大于号 | &gt; | &\#62; |
| :--- | :--- | :--- | :--- |
| & | 和号 | &amp; | &\#38; |
| " | 引号 | &quot; | &\#34; |
| ' | 撇号 | &apos; \(IE不支持\) | &\#39; |
| § | 小节 | &sect; | &\#167; |
| © | 版权 | &copy; | &\#169; |
| ® | 注册商标 | &reg; | &\#174; |
| TM | 商标 | &trade; | &\#8482; |
| × | 乘号 | &times; | &\#215; |
| ÷ | 除号 | &divide; | &\#247; |

关于HTML5的文章

# [https://thegeekdaily.com/everything-you-need-to-know-about-html-5-and-its-impact-on-seo/](https://thegeekdaily.com/everything-you-need-to-know-about-html-5-and-its-impact-on-seo/ "everything-you-need-to-know-about-html-5-and-its-impact-on-seo/")

关于HTML5常用标签

[http://www.calcresult.com/reference/development/HTML5-periodic-table.html](http://www.calcresult.com/reference/development/HTML5-periodic-table.html "Periodic Table of HTML5 Elements")

