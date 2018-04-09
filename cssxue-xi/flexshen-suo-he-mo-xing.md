# Flex 伸缩布局

**Flex 容器\(flex container\):**  
采用 Flex 布局的元素，称为 Flex 容器\(flex container\)，简称”容器”。  
**Flex 项目\(flex item\)**  
Flex 容器的所有子元素自动成为容器成员，称为 Flex 项目\(flex item\)，简称”项目”。

![](/assets/屏幕快照 2018-04-09 上午9.31.45.png)

容器默认存在两根轴:水平的主轴\(main axis\)和垂直的交叉轴\(cross axis\)。主轴的 开始位置\(与边框的交叉点\)叫做main start，结束位置叫做main end;交叉轴的开始位 置叫做cross start，结束位置叫做 cross end。

项目默认沿主轴排列。单个项目占据的主轴空间叫做 main size，占据的交叉轴空间叫做 cross size。

**创建 flex container 容器:**

Display:flex

**Flex items\(flex 项目\)**

在文档流中的子元素是弹性子元素

![](/assets/屏幕快照 2018-04-09 上午9.33.21.png)

## 弹性布局特性:

### 与方向有关:

flex-direction

Flex-wrap  
Flex-flow  
order

### 与弹性有关:

Flex-basis

Flex-grow  
Flex-shrink  
flex

### 与对齐有关:

Justify-content

Align-items

Align-self  
Align-content

### Flex-direction:

**决定主轴的方向\(即项目的排列方向\)**

```
Flex-direction:row|row-reverse|column|column-reverse
```

![](/assets/屏幕快照 2018-04-09 上午9.36.26.png)

它可能有 4 个值。

row\(默认值\):主轴为水平方向，起点在左端。

row-reverse:主轴为水平方向，起点在右端。  
column:主轴为垂直方向，起点在上沿。  
column-reverse:主轴为垂直方向，起点在下沿。

### Flex-wrap:

默认情况下，项目都排在一条线\(又称”轴线”\)上。flex-wrap 属性定义，如 果一条轴线排不下，如何换行。

```
Flex-wrap:nowrap|wrap|wrap-reverse
```

![](/assets/屏幕快照 2018-04-09 上午9.38.19.png)

它可能取三个值。

\(1\)nowrap\(默认\):不换行。![](/assets/屏幕快照 2018-04-09 上午9.39.05.png)\(2\)wrap:换行，第一行在上方。

![](/assets/屏幕快照 2018-04-09 上午9.39.35.png)

\(3\)wrap-reverse:换行，第一行在下方。![](/assets/屏幕快照 2018-04-09 上午9.40.01.png)

### Flex-flow:

flex-flow 属性是 flex-direction 属性和 flex-wrap 属性的简写形式，默认值为 row nowrap。

```
Flex-flow::<'flex-direction'> || <'flex-wrap'>
```

![](/assets/屏幕快照 2018-04-09 上午9.41.27.png)

### Order:

order 属性定义项目的排列顺序。数值越小，排列越靠前，默认为 0。

Order:&lt;interger&gt;

Initial:0 \(初始值为 0\)![](/assets/屏幕快照 2018-04-09 上午9.42.18.png)

### Flex-basis

flex-basis 属性定义了在分配多余空间之前，项目占据的主轴空间\(main size\)。浏览器 根据这个属性，计算主轴是否有多余空间。它的默认值为 auto，即项目的本来大小。  
flex-basis: &lt;length&gt; \| auto; /\* default auto \*/  
设置flexitem的初始宽/高

它可以设为跟 width 或 height 属性一样的值\(比如 350px\)，则项目将占据固定空间。

### Flex-grow:

flex-grow属性定义项目的放大比例，默认为0，即如果存在剩余空间，也不放大。设置元素所能分配到的空余空间的比例。

```
Flex-grow:<number>
```

![](/assets/屏幕快照 2018-04-09 上午9.44.09.png)

** 1.默认情况下，flex-grow:0,flex-item 项目不占据额外空间。**

**2.如果只设置一个 flex-item 项目的 flex-grow 为 1，则它将占据剩余空间。**

** 3.如果一个项目的 flex-grow 属性为 2，一个项目为 1，则前者占据的剩余空间比后者多一 倍。**  
** 4.计算方法:flex-basis + flow-grow/sum\(flow-grow\) \* remain**

示例:b,c 将按照 1:3 的比率分配剩余空间

HTML Code:

```
<ul class="flex">
    <li>a</li>
    <li>b</li>
    <li>c</li>
</ul>
```

CSS Code:

```
.flex{display:flex;width:600px;margin:0;padding:0;list-style:none;}
.flex li:nth-child(1){width:200px;}
.flex li:nth-child(2){flex-grow:1;width:50px;}
.flex li:nth-child(3){flex-grow:3;width:50px;}
```

flex-grow 的默认值为 0，如果没有显示定义该属性，是不会拥有分配剩余空间权利的。

> 本例中 b,c 两项都显式的定义了 flex-grow，flex 容器的剩余空间分成了 4 份，其中 b 占 1 份，c占3分，即1:3  
>  flex 容器的剩余空间长度为:600-200-50-50=300px，所以最终 a,b,c 的长度分别为:  
>  a: 200+\(300/4\*0\)=200px
>
> ```
> b: 50+(300/4*1)=125px
> a: 50+(300/4*3)=275px
> ```

### Flex-shrink:

**flex-shrink 属性定义了项目的缩小比例，默认为 1，即如果空间不足，该项目将缩小。**

```
Flex-shrink:<number>
Initial:1
```

![](/assets/屏幕快照 2018-04-09 上午9.47.35.png)

如果所有项目的 flex-shrink 属性都为 1，当空间不足时，都将等比例缩小。如果一个项目 的 flex-shrink 属性为 0，其他项目都为 1，则空间不足时，前者不缩小。 负值对该属性无效。  
计算方法:**flex-basis + flow-shrink/sum\(flow-shrink\) \* remain**

示例:a,b,c 将按照 1:1:3 的比率来收缩空间

HTML Code:

```
<ul class="flex">
    <li>a</li>
    <li>b</li>
    <li>c</li>
</ul>
```

CSS Code:

```
.flex{display:flex;width:400px;margin:0;padding:0;list-style:none;}
 .flex li{width:200px;}
 .flex li:nth-child(3){flex-shrink:3;}
```

flex-shrink 的默认值为 1，如果没有显示定义该属性，将会自动按照默认值 1 在所有因子 相加之后计算比率来进行空间收缩。

本例中 c 显式的定义了 flex-shrink，a,b 没有显式定义，但将根据默认值 1 来计算，可以 看到总共将剩余空间分成了5份，其中a占1份，b占1份，c占3分，即1:1:3 我们可以看到父容器定义为 400px，子项被定义为 200px，相加之后即为 600px，超出父容 器 200px。那么这么超出的 200px 需要被 a,b,c 消化

通过收缩因子，所以加权综合可得 200\*1+200\*1+200\*3=1000px;

  
 于是我们可以计算 a,b,c 将被移除的溢出量是多少:  
 a 被移除溢出量:\(200\*1/1000\)\*200，即约等于 40px  
 b 被移除溢出量:\(200\*1/1000\)\*200，即约等于 40px  
 c 被移除溢出量:\(200\*3/1000\)\*200，即约等于 120px

  
 最后 a,b,c 的实际宽度分别为:200-40=160px, 200-40=160px, 200-120=80px;



### Flex

**flex 属性是 flex-grow, flex-shrink 和 flex-basis 的简写，默认值为 0 1 auto。后两个 属性可选。**  


```
Flex: [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]|none
Initial:0 1 auto
```

该属性有两个快捷值:auto \(1 1 auto\) 和 none \(0 0 auto\)。 **建议优先使用这个属性，而不是单独写三个分离的属性，因为浏览器会推算相关值。**

#### 取值:

none: none 关键字的计算值为: 0 0 auto

&lt;'flex-grow'&gt;: 用来指定扩展比率

&lt;'flex-shrink'&gt;: 用来指定收缩比率

&lt;'flex-basis'&gt;: 用来指定伸缩基准值

如果缩写「flex: 1」, 则其计算值为「1 1 0%」

如果缩写「flex: auto」, 则其计算值为「1 1 auto」

如果「flex: none」, 则其计算值为「0 0 auto」

如果「flex:0auto」或者「flex:initial」,则其计算值为「01auto」，即「flex」 初始值

示例:如下情况每个元素的计算宽是多少

HTML Code:

```
<ul class="flex">
    <li>a</li>
    <li>b</li>
    <li>c</li>
</ul>
```

CSS Code:

```
.flex{display:flex;width:800px;margin:0;padding:0;list-style:none;}
.flex :nth-child(1){flex:1 1 300px;}
.flex :nth-child(2){flex:2 2 200px;}
.flex :nth-child(3){flex:3 3 400px;}
```

本例定义了父容器宽\(即主轴宽\)为 800px，由于子元素设置了伸缩基准值 flex-basis，相 加 300+200+400=900，那么子元素将会溢出 900-800=100px;

由于同时设置了收缩因子，所以加权综合可得 300\*1+200\*2+400\*3=1900px; 于是我们可以计算 a,b,c 将被移除的溢出量是多少:

```
a 被移除溢出量:(300*1/1900)*100，即约等于 16px
b 被移除溢出量:(200*2/1900)*100，即约等于 21px
c 被移除溢出量:(400*3/1900)*100，即约等于 63px
```

最后 a,b,c 的实际宽度分别为:300-16=284px, 200-21=179px, 400-63=337px

仍然是上面这个例子，不过**将容器的宽度改成了 1500px**

HTML Code:

```
<ul class="flex">
    <li>a</li>
    <li>b</li>
    <li>c</li>
</ul>
```

CSS Code:

```
.flex{display:flex;width:1500px;margin:0;padding:0;list-style:none;}
.flex :nth-child(1){flex:1 1 300px;}
.flex :nth-child(2){flex:2 2 200px;}
.flex :nth-child(3){flex:3 3 400px;}
```

本例定义了父容器宽\(即主轴宽\)为 1500px，由于子元素设置了伸缩基准值 flex-basis， 相加 300+200+400=900，那么容器将有 1500-900=600px 的剩余宽度;  
于是我们可以计算 a,b,c 将被扩展量是多少:

```
a 的扩展量:(1/(1+2+3))*600，即约等于 100px
b 的扩展量:(2/(1+2+3))*600，即约等于 200px
c 的扩展量:(3/(1+2+3))*600，即约等于 300px
```

最后 a,b,c 的实际宽度分别为:300+100=400px, 200+200=400px, 400+300=700px

从本例能看出:

   1.当「flex-basis」在「flex」属性中不为 0 时\(包括值为 auto，此时伸缩基准值等于自身内容宽度\)，「flex 子项」将分配容器的剩余空间\(剩余空间即等于容器宽度减去 各项的伸缩基准值\)

   2.当「flex-basis」在「flex」属性中等于 0 时，「flex 子项」将分配容器的所有空 间\(因为各项的伸缩基准值相加等于 0，剩余空间等于容器宽度减去各项的伸缩基准值，即 减 0，最后剩余空间值等于容器宽度\)，所以可以借助此特性，给各子项定义「flex: n」 来进行按比例均分容器总宽度

### Justify-content

```
justify-content:flex-start|flex-end|center|space-between|space-around
定义了项目在主轴(main-axis)上的对齐方式。
```

![](/assets/屏幕快照 2018-04-09 上午10.16.44.png)

它可能取 5 个值，具体对齐方式与轴的方向有关。下面假设主轴为从左到右。

```
flex-start(默认值):左对齐
flex-end:右对齐
center: 居中
space-between:两端对齐，项目之间的间隔都相等。
space-around:每个项目两侧的间隔相等,所以，项目之间的间隔比项目与边框的间隔大一倍
```

### Align-items

```
align-items: flex-start | flex-end | center | baseline | stretch
定义项目在交叉轴(辅轴，cross-axis)上如何对齐。
```

![](/assets/屏幕快照 2018-04-09 上午10.20.27.png)

它可能取 5 个值。具体的对齐方式与交叉轴的方向有关，下面假设交叉轴从上到下。

```
flex-start:交叉轴的起点对齐。
flex-end:交叉轴的终点对齐。
center:交叉轴的中点对齐。
baseline: 项目的第一行文字的基线对齐。
stretch(默认值):如果项目未设置高度或设为auto，将占满整个容器的高度。
```

### Align-self

align-self 属性允许单个项目有与其他项目不一样的对齐方式，可覆盖 align-items 属性。

默认值为 auto，表示继承父元素的 align-items 属性，如果没有父元素，则等同于 stretch。

```
align-self: auto | flex-start | flex-end | center | baseline | stretch
```

设置单个flexitem在cross-axis方向上对齐方式。

![](/assets/屏幕快照 2018-04-09 上午10.22.09.png)

### Align-content

align-content 属性定义了多根轴线的对齐方式。如果项目只有一根轴线，该属性不起作用。

```
align-content: flex-start | flex-end | center | space-between | space-around | stretch
设置cross-axis方向上行对齐方式
```

![](/assets/屏幕快照 2018-04-09 上午10.23.05.png)

该属性可能取 6 个值。

```
flex-start:与交叉轴的起点对齐。
flex-end:与交叉轴的终点对齐。
center:与交叉轴的中点对齐。
space-between:与交叉轴两端对齐，轴线之间的间隔平均分布。
space-around:每根轴线两侧的间隔都相等。所以，轴线之间的间隔比轴线与边框的间
隔大一倍。
stretch(默认值):轴线占满整个交叉轴。
```

### Flex布局应用-三行两列自适应布局

![](/assets/屏幕快照 2018-04-09 上午10.24.03.png)

![](/assets/屏幕快照 2018-04-09 上午10.24.23.png)

