## Display:设置元素的显示方式

> 默认值:inline  
> 取值:  
> none:隐藏对象。与visibility属性的hidden值不同，其不为被隐藏的对象保留其物理空间  
> **inline: 指定对象为内联元素。**  
> **block: 指定对象为块元素。**  
> list-item: 指定对象为列表项目。  
> **inline-block: 指定对象为内联块元素。\(CSS2\)**  
> **table:指定对象作为块元素级的表格。类同于html标签&lt;table&gt;\(CSS2\)**  
> inline-table:指定对象作为内联元素级的表格。类同于html标签&lt;table&gt;\(CSS2\)  
> table-caption:指定对象作为表格标题。类同于html标签&lt;caption&gt;\(CSS2\)  
> **table-cell:指定对象作为表格单元格。类同于html标签&lt;td&gt;\(CSS2\)**  
> **table-row:指定对象作为表格行。类同于html标签&lt;tr&gt;\(CSS2\)**  
> table-row-group:指定对象作为表格行组。类同于html标签&lt;tbody&gt;\(CSS2\)  
> table-column:指定对象作为表格列。类同于html标签&lt;col&gt;\(CSS2\)  
> table-column-group:指定对象作为表格列组显示。类同于html标签&lt;colgroup&gt;\(CSS2\)  
> table-header-group:指定对象作为表格标题组。类同于html标签&lt;thead&gt;\(CSS2\)  
> table-footer-group:指定对象作为表格脚注组。类同于html标签&lt;tfoot&gt;\(CSS2\)  
> run-in: 根据上下文决定对象是内联对象还是块级对象。\(CSS3\)  
> box: 将对象作为弹性伸缩盒显示。\(伸缩盒最老版本\)\(CSS3\)  
> inline-box: 将对象作为内联块级弹性伸缩盒显示。\(伸缩盒最老版本\)\(CSS3\)  
> flexbox: 将对象作为弹性伸缩盒显示。\(伸缩盒过渡版本\)\(CSS3\)  
> inline-flexbox: 将对象作为内联块级弹性伸缩盒显示。\(伸缩盒过渡版本\)\(CSS3\)  
> **flex: 将对象作为弹性伸缩盒显示。\(伸缩盒最新版本\)\(CSS3\)**  
> inline-flex: 将对象作为内联块级弹性伸缩盒显示。\(伸缩盒最新版本\)\(CSS3\)

## Display: Block\(块级元素\)![](/assets/屏幕快照 2018-03-30 上午9.27.01.png)

#### 默认的display:block元素有:div,h1-h6,p,ul,form,......



### Display: inline\(行内元素\)

![](/assets/屏幕快照 2018-03-30 上午9.28.40.png)



#### 默认display:inline元素有:span,a,label,cite,em,......

### Display:block与display:inline比较![](/assets/屏幕快照 2018-03-30 上午9.29.28.png)

## Display: inline-block\(行内元素\)

#### ![](/assets/屏幕快照 2018-03-30 上午9.30.12.png)默认display:inline-block元素有:img,input,textarea,select,button,......



## Display: none

设置元素不显示。

display:none 或 visibility:hidden

隐藏一个元素可以通过把display属性设置为"none"，或把visibility属性设置为"hidden"。display属性设置一个元素应如何显示，visibility属性指定一个元素应可见还 是隐藏。这两种方法会产生不同的结果。

> **visibility:hidden可以隐藏某个元素，但隐藏的元素仍需占用与未隐藏之前一样的空 间。也就是说，该元素虽然被隐藏了，但仍然会影响布局.**

> **display:none可以隐藏某个元素，且隐藏的元素不会占用任何空间。也就是说，该元 素不但被隐藏了，而且该元素原本占用的空间也会从页面布局中消失。**



## 与 Display 相关布局模式

### 1.块级元素水平居中![](/assets/屏幕快照 2018-03-30 上午9.32.30.png)![](/assets/屏幕快照 2018-03-30 上午9.32.52.png)2.居中导航![](/assets/屏幕快照 2018-03-30 上午9.34.12.png)![](/assets/屏幕快照 2018-03-30 上午9.34.31.png)

# 参考知识:

## 1. 元素分类

> 在 CSS 中，html 中的标签元素大体被分为三种不同的类型:块状元素、内联元素\(又叫行内 元素\)和内联块状元素。  
>  **常用的块状元素有: &lt;div&gt;、&lt;p&gt;、&lt;h1&gt;...&lt;h6&gt;、&lt;ol&gt;、&lt;ul&gt;、&lt;dl&gt;、&lt;table&gt;、&lt;address&gt;、&lt;blockquote&gt; 、&lt;form&gt;**

> ** 常用的内联元素有: &lt;a&gt;、&lt;span&gt;、&lt;br&gt;、&lt;i&gt;、&lt;em&gt;、&lt;strong&gt;、&lt;label&gt;、&lt;q&gt;、&lt;var&gt;、&lt;cite&gt;、&lt;code&gt; **

> **常用的内联块状元素有: &lt;img&gt;、&lt;input&gt;**

## 元素分类--块级元素

设置display:block就是将元素显示为块级元素。  
 如下代码就是将内联元素 a 转换为块状元素，从而使 a 元素具有块状元素特点。 a{display:block;}块级元素特点:

* 每个块级元素都从新的一行开始，并且其后的元素也另起一行。\(真霸道，一个块级元

  素独占一行\)

* 元素的高度、宽度、行高以及顶和底边距都可设置。

* 元素宽度在不设置的情况下，是它本身父容器的100%\(和父元素的宽度一致\)，除非

  设定一个宽度。

## 元素分类--内联元素

在 html 中，&lt;span&gt;、&lt;a&gt;、&lt;label&gt;、 &lt;strong&gt; 和&lt;em&gt;就是典型的内联元素\(行内元素\) \(inline\)元素。当然块状元素也可以通过代码 display:inline 将元素设置为内联元素。 如下代码就是将块状元素 div 转换为内联元素，从而使 div 元素具有内联元素特点。

div {display:inline}

内联元素特点:

> **和其他元素都在一行上;**
>
> **元素的高度、宽度及顶部和底部边距不可设置;**
>
> **元素的宽度就是它包含的文字或图片的宽度，不可改变。**



# 解决内联元素\(行内元素\)间隙 bug 问题

行内元素之间会产生间隙 bug 问题的场景: 

内元素之间有“回车”、“tab”、“空格”时就会出现间隙。

如下代码:

![](/assets/屏幕快照 2018-03-30 上午9.39.37.png)

解决方法:

1、写在一行，之间不要有空格之类的符号。

```
<div> 
<a>1</a><a>2</a><span>33333</span><span>44444</span><em>555555</em> 
</div>
```

2、使用 font-size:0，设置内联元素的父元素字体大小为 0，然后设置内联元素字体大小。

```
div{font-size:0;}
a,span,em{font-size:16px;}/*div 为 a、span、em 元素的父元素*/
```

3、标签分开写，例如:

```
<div>
   <a>1</a
> <a>2</a
> <span>33333</span
> <span>44444</span
> <em>555555</em>
</div>
```

## 元素分类--内联块状元素

内联块状元素\(inline-block\)就是同时具备内联元素、块状元素的特点，代码display:inline-block就是将元素设置为内联块状元素。\(css2.1 新增\)，&lt;img&gt;、&lt;input&gt;标签就是这种内联块状标签。 inline-block 元素特点:

> **1、和其他元素都在一行上;**
>
> **2、元素的高度、宽度、行高以及顶和底边距都可设置。**

## 2. 如何实现浏览器兼容版的 inline-block 显示

IE6,7 支持 inline 元素转换成 inline-block，但不支持 block 元素转换成 inline-block，所以非 inline 元素在 IE6,7 下要转换成 inline-block，需先转换成 inline， 然后触发 hasLayout，以此来获得和 inline-block 类似的效果;可以这样:  
 全兼容的 inline-block:  
 div {

```
         display: inline-block;
         *display: inline;
         *zoom: 1;

```

}  
 对应的脚本特性为 display。



















