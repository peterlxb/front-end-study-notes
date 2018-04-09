# Transition 过渡

  在CSS3中，我们可以使用transition属性来将元素的某一个属性从“一个属性值”在指定的时间内平滑地过渡到“另外一个属性值”来实现动画效果。

  CSS transform属性所实现的元素变形，呈现的仅仅是一个“结果”，而CSS transition呈现的是一种过渡“过程”，通俗点说就是一种动画转换过程，如**渐显、渐隐、动画快慢**等。

```
语法:transition:属性 持续时间 过渡方法 延迟时间;
```

在 CSS 中创建简单的过渡效果可以从以下几个步骤来实现: 

> **1. 在默认样式中声明元素的初始状态样式;  
> 2. 声明过渡元素最终状态样式，比如悬浮状态;  
> 3. 在默认样式中通过添加过渡函数，添加一些不同的样式。**

CSS3 的过度 transition 属性是一个复合属性，主要包含 4 个子属性:

### transition-property:对元素的哪一个属性进行操作;

使用 transition-property 属性来单独设定过渡动画所要操作的那个属性。

语法:

```
transition-property:none |<single-transition-property>[ ,<single-transition-property> ]* 
<single-transition-property> = all | <IDENT>
```

默认值:all。 默认为所有可以进行过渡的 css 属性。

> 说明:transition-property 属性的取值是一个“CSS 属性名”。

对于 CSS3 过渡动画，大多数情况下都是配合:hover 伪类来使用。其对应具有过渡的 CSS 属性主要有:



![](/assets/屏幕快照 2018-04-10 上午7.36.13.png)

## transition-duration:过渡的持续时间;

```
语法:transition-duration:时间;
```

> 说明:transition-duration 属性取值是一个时间，单位为 s\(秒\)，可以为小数如 0.5s。 如果提供多个属性值，以逗号进行分隔。

## transition-timing-function:过渡使用的方法\(函数\);

使用 transition-timing-function 属性来定义过渡方式。所谓的“过渡方式”主要用来指 定动画在过渡时间内的速率。  
语法:

```
transition-timing-function: 
<single-transition-timing-function>[,<single-transition-timing-function>]* 
<single-transition-timing-function> = ease | linear | ease-in | ease-out | 
ease-in-out | step-start | step-end | steps(<integer>[, [ start | end ] ]?) | 
cubic-bezier(<number>, <number>, <number>, <number>)

```

默认值:ease  
 transition-timing-function 属性取值共有 5 种，具体如下:

![](/assets/屏幕快照 2018-04-10 上午7.38.54.png)

取值:

linear: 线性过渡。等同于贝塞尔曲线\(0.0, 0.0, 1.0, 1.0\)

ease: 平滑过渡。等同于贝塞尔曲线\(0.25, 0.1, 0.25, 1.0\)

ease-in: 由慢到快。等同于贝塞尔曲线\(0.42, 0, 1.0, 1.0\)

ease-out: 由快到慢。等同于贝塞尔曲线\(0, 0, 0.58, 1.0\)

ease-in-out:由慢到快再到慢。等同于贝塞尔曲线\(0.42, 0, 0.58, 1.0\)

step-start: 等同于 steps\(1, start\)

step-end: 等同于 steps\(1, end\)

steps\(&lt;integer&gt;\[, \[ start \| end \] \]?\):接受两个参数的步进函数。第一个参数必

        须为正整数，指定函数的步数。第二个参数取值可以是 start 或 end，指定每一步的值

        发生变化的时间点。第二个参数是可选的，默认值为 end。

cubic-bezier\(&lt;number&gt;, &lt;number&gt;, &lt;number&gt;, &lt;number&gt;\): 特定的贝塞尔曲线类型，4 个数值需在\[0, 1\]区间内

## transition-delay:可选属性，指定过渡开始出现的延迟时间;

```
语法:transition-delay:时间;
```

说明:transition-delay 属性取值是一个时间，单位为 s\(秒\)，可以为小数如 0.5s。

transition-delay 属性默认值为 0，也就是说当我们没有设置 transition-delay 属性时， 过渡动画就没有延迟时间。如果提供多个属性值，以逗号进行分隔。  
案例:

![](/assets/屏幕快照 2018-04-10 上午7.41.12.png)

## transition

如果想要使用transition 属性同时对多个属性进行实现平滑过渡效果，只需要在transition-property 属性添加多个属性名即可，其中属性名之间用英文逗号隔开。然后各自可以有各自不同的延续时间和其时间的速率变换方式。

但需要值得注意的一点:第一个时 间的值为 transition-duration，第二个为 transition-delay。  
 例如:

```
a{ transition: background 0.8s ease-in 0.3,color 0.6s ease-out 0.3;}
```

参考资料

[https://css-tricks.com/almanac/properties/t/transition/](https://css-tricks.com/almanac/properties/t/transition/)















