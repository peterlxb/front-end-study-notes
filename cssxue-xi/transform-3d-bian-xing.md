# transform-3d 变形

## Perspective 属性-透视

```
语法:Perspective:none | <length>
```

**perspective属性定义3D元素距视图的距离，以像素计。**  
该属性允许改变3D元素查看3D元素的视图。当为元素定义perspective属性时，其子 元素会获得透视效果，而不是元素本身。  
理解:

> 当perspective:none/0;时，相当于没有设perspective\(length\)。比如要建立一个小立方 体，长宽高都是200px。如果perspective &lt; 200px，那就相当于站在盒子里面看的结果， 如果perspective非常大那就是站在非常远的地方看\(立方体已经成了小正方形了\)。
>
> 当元素没有设置perspective\(length\)时，所有后代元素被压缩在同一个二维平面上，不 存在景深的效果。如果设置perspective\(length\)后，将会看到三维的效果。默认的透视视角中心在容器\(是perspective所在的元素，不是他的后代元素\)的中点，也就是perspective-origin: 50% 50%。当然你也可以自己设置，比如:左上角-webkit-perspective-origin: 0px 0px;。

### Perspective-origin 属性

perspective-origin 属性定义 3D 元素所基于的 X 轴和 Y 轴。该属性允许您改变 3D 元 素的底部位置。  
 定义时的 perspective -Origin 属性，它是一个元素的子元素，透视图，而不是元素本身。 

语法:perspective-origin: x-axis y-axis;

![](/assets/屏幕快照 2018-04-10 上午7.18.53.png)

## Translate3d-指定对象的 3D 位移。

```
语法:translate3d(<translation-value>,<translation-value>,<length>)
```

> **第1个参数对应X轴，第2个参数对应Y轴，第3个参数对应Z轴，参数不允许省略 。**

![](/assets/屏幕快照 2018-04-10 上午7.19.53.png)

## Scale3d\(\)-指定对象的 3D 缩放

```
语法:scale3d(<number>,<number>,<number>)
```

> 第 1 个参数对应 X 轴，第 2 个参数对应 Y 轴，第 3 个参数对应 Z 轴，参数不允许省略

![](/assets/屏幕快照 2018-04-10 上午7.20.54.png)



## Rotate3d\(\)-指定对象的 3D 旋转角度。

```
语法:rotate3d(<number>,<number>,<number>,<angle>)
```

> ```
> 其中前3个参数分别表示旋转的方向 x,y,z，第4个参数表示旋转的角度，参数不允许省略
> ```

![](/assets/屏幕快照 2018-04-10 上午7.22.03.png)

## Transform-style

transform--style 属性指定嵌套元素是怎样在三维空间中呈现。

```
语法:transform-style: flat|preserve-3d;
```

![](/assets/屏幕快照 2018-04-10 上午7.23.02.png)



> **flat值为默认值，表示所有子元素在2D平面呈现。**

> **preserve-3d表示所有子元素在3D空间中呈现。**

> 也就是说，如果对一个元素设置了 transform-style 的值为 flat，则该元素的所有子元素 都将被平展到该元素的 2D 平面中进行呈现。沿着 X 轴或 Y 轴方向旋转该元素将导致位于正 或负Z轴位置的子元素显示在该元素的平面上，而不是它的前面或者后面。如果对一个元素 设置了 transform-style 的值为 preserve-3d，它表示不执行平展操作，他的所有子元素位 于 3D 空间中。

## Backface-visibility

backface-visibility 属性定义当元素不面向屏幕时是否可见。 如果在旋转元素不希望看到其背面时，该属性很有用。

```
语法:backface-visibility: visible|hidden;
```

![](/assets/屏幕快照 2018-04-10 上午7.24.35.png)

参考资源:  
[http://desandro.github.io/3dtransforms/](http://desandro.github.io/3dtransforms/)





















