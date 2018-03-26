# 文本、颜色

## CSS 字体属性

### ![](/assets/屏幕快照 2018-03-26 上午11.09.51.png)

### Font-family:

CSS定义了5种通用字体系列:

```
  Serif 字体\(衬线字体，如 Times New Rome\)

  Sans-serif字体\(无衬线字体，如Arial \) 

  Monospace字体 \(等宽字体\)

  Cursive字体   \(草书字体，手写字体\)

   Fantasy字体 \(相当于印刷学中的装饰体\)
```

默认情况下，浏览器的字体是宋体。

### font-size语法:

font-size:&lt;absolute-size&gt;\|&lt;relative-size&gt;\|&lt;length&gt;\|&lt;percentage&gt;&lt;absolute-size&gt;= xx-small \| x-small \| small \| medium \| large \| x-large \| xx-large&lt;relative-size&gt;= smaller \| larger  
默认值:medium

Font-size 属性值可以有很多种方式:

```
使用关键字\(small/medium/large/x-small/xx-small/x-large/xx-large\);

使用像素做单位的数值\(如 20px\),  
使用 em、%等来做单位。
```

### font-style属性

![](/assets/屏幕快照 2018-03-26 上午11.14.23.png)

### font-weight 属性

字体粗细值可以取关键字和 100~900 的数值。也可使用关键字。

![](/assets/屏幕快照 2018-03-26 上午11.14.57.png)

### Font-variant 属性

![](/assets/屏幕快照 2018-03-26 上午11.15.32.png)

### Text-transform 属性 ---英文大小写转换

![](/assets/屏幕快照 2018-03-26 上午11.16.02.png)

### Line-height--行间距\(行高\)

![](/assets/屏幕快照 2018-03-26 上午11.16.34.png)

### Color 颜色

![](/assets/屏幕快照 2018-03-26 上午11.17.31.png)

## **文本对齐方式**

### Text-align:

text-align属性规定元素中的文本的水平对齐方式。

该属性通过指定行框与哪个点对齐，从而设置块级元素内文本的水平对齐方式。通过允许用户代理调整行 内容中字母和字之间的间隔，可以支持值justify;不同用户代理可能会得到不同的结果。

![](/assets/屏幕快照 2018-03-26 上午11.18.34.png)**text-align 属性只能针对文本文字和img标签，对其他标签无效。**

最后一个水平对齐属性是justify。

在两端对齐文本中，文本行的左右两端都放在父元素的内边界上。然后，调整单词和字母间的间隔，使各

行的长度恰好相等。两端对齐文本在打印领域很常见。

### vertical-align

Vertical-align属性设置元素的垂直对齐方式。

**该属性定义行内元素的基线相对于该元素所在行的基线的垂直对齐。允许指定负长度值和百分比值。这会**

**使元素降低而不是升高。在表单元格中，这个属性会设置单元格框中的单元格内容的对齐方式。**

![](/assets/屏幕快照 2018-03-26 上午11.21.46.png)

### Text-indent

Text-indent 设置首行缩进。 中文文字中的段前习惯空两个文字的空白，这个特殊的样式可以用下面代码来实现:

![](/assets/屏幕快照 2018-03-26 上午11.22.30.png)

## 文本格式处理

### White-space

white-space属性设置如何处理元素内的空白\(空白符\)。

![](/assets/屏幕快照 2018-03-26 上午11.23.05.png)

![](/assets/屏幕快照 2018-03-26 上午11.23.28.png)

white-space属性的行为:![](/assets/屏幕快照 2018-03-26 上午11.23.58.png)

### Word-wrap

在 CSS3 中，我们可以使用 word-wrap 属性来设置“长单词”或“URL 地址”是 否换行到下一行。  
 语法:word-wrap:取值;  
 说明:word-wrap 属性只有 2 个取值:normal 和 break-word。

![](/assets/屏幕快照 2018-03-26 上午11.24.45.png)

默认情况下，文本是自动换行的，但是如果单词或者 URL 地址太长的话，就会超出区域范围， 需要使用 word-wrap 属性来调节。  
word-wrap 属性是针对英文来说的，中文中没有什么所谓的“长单词”之说。

### Word-break

设置或检索对象内文本的字内换行行为。 对于解决防止页面中出现连续无意义的长字符打破布局，应该使用 break-all 属性值;语法:  
![](/assets/屏幕快照 2018-03-26 上午11.25.47.png)

## 文本修饰

### Text-decoration -文本修饰

![](/assets/屏幕快照 2018-03-26 上午11.26.40.png)

![](/assets/屏幕快照 2018-03-26 上午11.27.03.png)

underline会对元素加下划线，就像HTML中的U元素一样。overline的作用恰好相反，会在文本的 顶端画一个上划线。值line-through则在文本中间画一个贯穿线，等价于HTML中的S和strike元 素。

none值会关闭原本应用到一个元素上的所有装饰。通常，无装饰的文本是默认外观，但也不总是这样。 例如，链接默认地会有下划线。如果您希望去掉超链接的下划线，可以使用以下CSS来做到这一点:

```
a {text-decoration: none;}
```

### Text-shadow 文字阴影

text-shadow:x-offset y-offset blur color;

x-offset:\(水平阴影\)表示阴影的水平偏移距离，单位可以是px、em或者百分比等。 如果值为正，则阴影向右偏移;如果值为负，则阴影向左偏移;

y-offset:\(垂直阴影\)表示阴影的垂直偏移距离，单位可以是px、em或者百分比等。 如果值为正，则阴影向下偏移;如果值为负，则阴影向上偏移;

blur:\(模糊距离\)表示阴影的模糊程度，单位可以是px、em或者百分比等。blur值 不能为负。如果值越大，则阴影越模糊;如果值越小，则阴影越清晰。当然，如果不需 要阴影模糊效果，可以把 blur 值设置为 0;

color:\(阴影的颜色\)表示阴影的颜色。  
在 CSS3 中，可以使用 text-shadow 属性来给文字指定多个阴影，并且针对每个阴影使用不 同的颜色。也就是说，text-shadow 属性可以为一个以英文逗号隔开的“值列表”，

```
text-shadow:0 0 4px white, 0 -5px 4px #ff3, 2px -10px 6px #fd3;
```

当 text-shadow 属性值为“值列表”时，阴影效果会按照给定的值顺序应用到该元素的文本 上，因此有可能出现互相覆盖的现象。但是 text-shadow 属性永远不会覆盖文本本身，阴影 效果也不会改变边框的尺寸。

### text-stroke 属性

在 CSS3 中，我们可以使用 text-stroke 属性为文字添加描边效果。这个描边效果， 说白了就是给文字添加边框。由于 CSS3 的出现，“文字”也能添加边框了呢。

**语法:text-stroke:宽度值 颜色值;**

### text-overflow 属性

在 CSS3 中，文本溢出 text-overflow 用于设置是否使用一个省略标记\(...\)标示 对象内文本的溢出。

![](/assets/屏幕快照 2018-03-26 上午11.30.55.png)单独使用 text-overflow 属性是无法得到上面图 1 效果的。因为 text-overflow 属性只是说

明文字溢出时用什么方式显示，要实现溢出时产生省略号效果，还须定义 2 个内容:

```
\(1\)white-space:nowrap;\(强制文本在一行内显示\);

\(2\)overflow:hidden;\(溢出内容为隐藏\);
```

下面是实现文字溢出时产生省略号效果的完整语法:

```
text-overflow:ellipsis;
overflow : hidden;
white-space:nowrap;
```

### Cursor 属性

在 CSS 中，使用 cursor 属性来定义鼠标的样式。  
![](/assets/屏幕快照 2018-03-26 上午11.33.04.png)

### Inherit 属性

inherit 属于 CSS-wide 关键字，这表示所有的属性都可以接受该值。

如何让一个不具备继承特性的属性可以继承父元素的定义?

```
div {
         position: relative;
}
div a {
}
```

上述代码，超链接 a 将会继承父元素的position定义，也会定义为 relative。

常用的 CSS 属性继承性:

![](/assets/屏幕快照 2018-03-26 上午11.35.09.png)

