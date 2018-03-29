# 背景 background属性

![](/assets/屏幕快照 2018-03-28 上午11.35.16.png)

## 1、背景颜色-background-color

在 CSS 中，使用background-color 属性来控制元素的背景颜色。默认值:transparent，即背景是透明的。

## 2、背景图像-background-image

![](/assets/屏幕快照 2018-03-29 上午8.02.41.png)![](/assets/屏幕快照 2018-03-29 上午8.03.07.png)

## 3.background-repeat

语法![](/assets/屏幕快照 2018-03-29 上午8.03.43.png)![](/assets/屏幕快照 2018-03-29 上午8.03.57.png)设置或检索对象的背景图像如何铺排填充。必须先指定&lt;'background-image'&gt;属性。  
    允许提供2个参数，如果提供全部2个参数，第1个用于横向，第二个用于纵向。

    如果只提供1个参数，则用于横向和纵向。特殊值repeat-x和repeat-y除外，因为repeat-x 相当于 repeat no-repeat，repeat-y 相当于 no-repeat repeat，即其实 repeat-x 和 repeat-y 等价于提供了 2 个参数值 .

## 4. background-position 属性

语法:

> background-position:&lt;position&gt;\[ , &lt;position&gt; \]\*
>
> &lt;position&gt;= \[ left \| center \| right \| top \| bottom \|&lt;percentage&gt;\|&lt;length&gt;\] \| \[ left \| center \| right \|&lt;percentage&gt;\|&lt;length&gt;\] \[ top \| center \| bottom \|&lt;percentage&gt;\|&lt;length&gt;\] \| \[ center \| \[ left \| right \] \[&lt;percentage&gt;\|&lt;length&gt;\]? \] && \[ center \| \[ top \| bottom \] \[&lt;percentage&gt;\|&lt;length&gt;\]? \]

默认值:0% 0%，效果等同于left top

####  \(1\). background-position 取值为“像素值”![](/assets/屏幕快照 2018-03-29 上午8.07.30.png)background-position:80px 40px;

#### \(2\). background-position 取值为“关键字”![](/assets/屏幕快照 2018-03-29 上午8.08.25.png)

## 5. background-attachment 属性

使用背景附件属性 background-attachment 可以设置背景图像是随对象滚动还是 固定不动。  
语法:

> background-attachment:&lt;attachment&gt;\[ , &lt;attachment&gt; \]\*
>
> &lt;attachment&gt;= fixed \| scroll \|local  
> 默认值:scroll

fixed: 背景图像相对于窗体固定。  
scroll: 背景图像相对于元素固定，也就是说当元素内容滚动时背景图像不会跟着滚动，因为背景图像总是要跟着元素本身。但会随元素的祖先元素或窗体一起滚动。

local:背景图像相对于元素内容固定，也就是说当元素随元素滚动时背景图像也会跟着滚动，因为背景图像总是要跟着内容。\(CSS3\)

## 6. background-size 属性

**在 CSS3 中，我们可以使用 background-size 属性来设置背景图片的大小，这使得我们可以 在不同的环境中重复使用背景图片。**![](/assets/屏幕快照 2018-03-29 上午8.10.32.png)![](/assets/屏幕快照 2018-03-29 上午8.10.41.png)背景图片不同于img标签引用的图片，对于img标签引用的图片，我们可以使用width和height属性来设置，但是这两个属性不能用于设置背景图片的大小。因此，在CSS3中，引入了background-size属性来设置背景图片的大小.。背景图片 的大小跟一般图片的大小设置有本质的区别。



## 7. background-origin 属性

在 CSS3 中，我们可以使用 background-origin 属性来设置元素背景图片平铺的最开始位置。![](/assets/屏幕快照 2018-03-29 上午8.12.11.png)![](/assets/屏幕快照 2018-03-29 上午8.12.18.png)background-origin 属性往往都是配合 background-position 属性来使用，其中background-origin 属性规定 background-position 属性相对于什么位置来定位。

浏览器默认采用“background-position:top left;”。因此不管 background-origin 属性值如何变化，背景图片都是从“左上”开始平铺。

效果如下:

![](/assets/屏幕快照 2018-03-29 上午8.14.00.png)

**需要注意的是，如果背景不是 no-repeat，这个属性无效，它会从边框开始显示。**

## 8. background-clip 属性

在 CSS3 中，使用 background-clip 属性来将背景图片根据实际需要进行剪切。![](/assets/屏幕快照 2018-03-29 上午8.14.57.png)backgroud-clip 默认值为 border-box。

效果如下图所示:

![](/assets/屏幕快照 2018-03-29 上午8.15.35.png)

**background-clip 属性指定了背景在哪些区域可以显示，**但与背景开始绘制的位置\(即 background-origin 属性\)无关。背景绘制的位置可以出现在不显示背景的区域。这就相当 于背景图片被不显示背景的区域裁剪了一部分一样。

## 9. Background

多重背景\(multiple backgrounds\)，也就是 CSS2 里 background 的属性外加 origin、clip 和 size 组成的新 background 的多次叠加，缩写时为用逗号隔开的每组值;

用分解写法时，如果有多个背景图片，而其他属性只有一个\(例如 background-repea只有一个\)，表明所有背景图片应用该属性值

语法缩写如下:![](/assets/屏幕快照 2018-03-29 上午8.18.26.png)![](/assets/屏幕快照 2018-03-29 上午8.19.44.png)



