# 盒模型

在“CSS 盒子模型”理论中，所有页面中的元素都可以看成一个盒子，并且占据着一定 的页面空间。一个页面由很多这样的盒子组成，这些盒子之间会互相影响，因此掌握盒子模 型需要从两个方面来理解:

一是理解单独一个盒子的内部结构，

二是理解多个盒子之间的相互关系。

**每个元素都看成一个盒子，盒子模型是由 content\(内容\)、padding\(内边距\)、margin\(外边距\)和 border\(边框\)这四个属性组成的。此外，在盒子模型中，还有宽度 width 和高度 height 两大辅助性属性。**

**在 CSS 中，width 和 height 指的是内容区域的宽度和高度。增加内边距、边框和外 边距不会影响内容区域的尺寸，但是会增加元素框的总尺寸**。

所有的元素都可以看作盒子。

CSS 盒子模型的内部结构:

![](/assets/box-model.png)![](/assets/屏幕快照 2018-03-28 上午10.57.25.png)

### 盒模型--宽度\(width\)和高度\(height\)

盒模型宽度和高度和我们平常所说的物体的宽度和高度理解是不一样的，css 内 定义的宽\(width\)和高\(height\)，指的是填充以里的内容范围。  
**一个元素实际宽度\(盒子的宽度\)=左边界+左边框+左填充+内容宽度+右填充+右边界。**

![](/assets/屏幕快照 2018-03-28 上午10.59.59.png)

元素的高度也是同理。

元素盒模型参考图:

![](/assets/屏幕快照 2018-03-28 上午11.00.42.png)

### 盒模型--填充\(padding\)

元素内容与边框之间是可以设置距离的，称之为“填充”。padding属性接受长度值或百分比值，不接受负值。

填充也可分为上、右、下、左\(顺时针\)。如下代码:

```
div{padding:20px 10px 15px 30px;}
```

顺序一定不要搞混。可以分开写上面代码:

```
div{
   padding-top:20px;
   padding-right:10px;
   padding-bottom:15px;
   padding-left:30px;
}
```

### 盒模型--边框\(border\)

**盒子模型的边框就是围绕着内容及补白的线，这条线你可以设置它的粗细、样式和颜色\(边框三个属性\)。**

如下面代码为 div 来设置边框粗细为 2px、样式为实心的、颜色为红色的边框:

```
div{
    border:2px  solid  red;
}
```

border-style\(边框样式\)常见样式有: dashed\(虚线\)\| dotted\(点线\)\| solid\(实线\)。

border-color\(边框颜色\)中的颜色可设置为十六进制颜色，如:border-color:\#888;

border-width\(边框宽度\)中的宽度也可以设置为:thin \| medium \| thick\(但不是

很常用\)，最常还是用象素\(px\)。

#### CSS 边框属性![](/assets/屏幕快照 2018-03-28 上午11.04.44.png)![](/assets/屏幕快照 2018-03-28 上午11.05.21.png)

### 盒模型--边界\(margin\)

元素与其它元素之间的距离可以使用边界\(margin\)来设置。

#### 这个属性接受任何长度单位、百分数值甚至负值。![](/assets/屏幕快照 2018-03-28 上午11.07.00.png)

边界也是可分为上、右、下、左

> **padding 和 margin 的区别，**
>
> **padding 在边框里，margin 在边框外。 **
>
> **Margin 在布局中的一个巧用是水平居中。设置 margin:0 auto, 可以使元素实现水平居中效果。**

### CSS 外边距合并

外边距合并\(叠加\)是一个相当简单的概念。但是，在实践中对网页进行布局时，它会造成许多混淆。![](/assets/屏幕快照 2018-03-28 上午11.09.29.png)                当一个元素出现在另一个元素上面时，第一个元素的下外边距与第二个元素的上外边距会发生合并。

![](/assets/屏幕快照 2018-03-28 上午11.11.23.png)

当一个元素包含在另一个元素中时\(假设没有内边距或边框把外边距分隔开\)，它们的上边距/或下外边距也会发生合并

![](/assets/屏幕快照 2018-03-28 上午11.13.33.png)

尽管看上去有些奇怪，但是外边距甚至可以与自身发生合并。  
假设有一个空元素，它有外边距，但是没有边框或填充。在这种情况下，上外边距和下外边距就碰到了一起，它们会发生合并。

![](/assets/屏幕快照 2018-03-28 上午11.17.44.png)

如果这个外边距遇到另一个元素的外边距，它还会发生合并:

![](/assets/屏幕快照 2018-03-28 上午11.18.24.png)

这就是一系列的段落元素占用空间非常小的原因，因为它们的所有外边距都合并到一起，形成了一个小 的外边距。

```
注释:只有普通文档流中块框的垂直外边距才会发生外边距合并。行内框、浮动框或绝对定位之间的外边距不会合并。
```
















