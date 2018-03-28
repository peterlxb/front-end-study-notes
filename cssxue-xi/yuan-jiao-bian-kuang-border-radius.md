# Border-radius---圆角边框

在 CSS3 中，针对边框，增加了丰富的修饰效果，使得网页更加美观舒服。下面列

出了常用的 CSS3 边框属性:  
![](/assets/屏幕快照 2018-03-28 上午11.22.21.png)

## border-radius 属性

长度值可以是 px、百分比、em 等

Border-radius属性设置长度值顺序:“左上角、右上角、右下角和左下角

### border-radius 画实心半圆和实心圆

1、实心半圆

实现上半圆，实现方法:把高度\(height\)设为宽度\(width\)的一半， 并且只设置左上角和右上角的圆角半径与元素的高度一致，而右下角和左下角的圆角半径设置为0.

```
   width:200px;
   height:100px;
   border:1px solid red;
   border-radius:100px 100px 0 0;
```

2、实心圆

在 CSS3 中，使用 border-radius 属性实现实心圆方法:把宽度\(width\)与高度\(height\) 值设置为一致\(也就是正方形\)，并且四个圆角值都设置为它们值的一半。

```
width:100px;
height:100px;
border:1px solid red;
border-radius:50px;
```

### border-radius 属性派生子属性

border-radius 属性可以分开，分别为四个角设置相应的圆角值，分别是: 

 \(1\)border-top-right-radius:右上角; 

 \(2\)border-bottom-right-radius:右下角;

 \(3\)border-bottom-left-radius:左下角; 

 \(4\)border-top-left-radius:左上角;

## 边框阴影 box-shadow

在 CSS3 中，我们可以使用 box-shadow 属性轻松地为元素添加阴影效果。 

语法:box-shadow:x-shadow y-shadow blur spread color inset; 

说明:

    1.x-shadow:设置水平阴影的位置\(X 轴\)，可以使用负值; 

    2.y-shadow:设置垂直阴影的位置\(y 轴\)，可以使用负值;

    3.blur:设置阴影模糊半径; 

    4.spread:阴影扩展半径，设置阴影的尺寸;这个参数可选，缺省时值为 0。 

    5.color:设置阴影的颜色; 

    6.inset:这个参数默认不设置。默认情况下为外阴影，inset 表示内阴影。\(这个值

      可以放在开头位置。\)

**外阴影 outset 与内阴影 inset**  
box-shadow 属性最后一个参数用于设置阴影是否是内阴影，还是外阴影。  
 取值有2种:  
 \(1\)outset:默认值，外阴影;  
 \(2\)inset:内阴影;



# CSS 轮廓

轮廓\(outline\)是绘制于元素周围的一条线，位于边框边缘的外围，可起到突出元素的作 用。  
 CSS outline 属性规定元素轮廓的样式、颜色和宽度。

![](/assets/屏幕快照 2018-03-28 上午11.29.47.png)



# Overflow 属性

**overflow属性规定当内容溢出元素框时发生的事情.**

![](/assets/屏幕快照 2018-03-28 上午11.30.47.png)

![](/assets/屏幕快照 2018-03-28 上午11.31.10.png)

# Box-sizing 属性

box-sizing是CSS3的 box 属性之一。

语法:

box-sizing: content-box\|border-box\|inherit;

![](/assets/屏幕快照 2018-03-28 上午11.32.04.png)

![](/assets/屏幕快照 2018-03-28 上午11.32.32.png)









