#                                    Flex 伸缩布局

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
>
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
 

.flex{display:flex;width:400px;margin:0;padding:0;list-style:none;}  
 .flex li{width:200px;}  
 .flex li:nth-child\(3\){flex-shrink:3;}  


flex-shrink 的默认值为 1，如果没有显示定义该属性，将会自动按照默认值 1 在所有因子 相加之后计算比率来进行空间收缩。  


本例中 c 显式的定义了 flex-shrink，a,b 没有显式定义，但将根据默认值 1 来计算，可以 看到总共将剩余空间分成了5份，其中a占1份，b占1份，c占3分，即1:1:3 我们可以看到父容器定义为 400px，子项被定义为 200px，相加之后即为 600px，超出父容 器 200px。那么这么超出的 200px 需要被 a,b,c 消化  


通过收缩因子，所以加权综合可得 200\*1+200\*1+200\*3=1000px;  
 于是我们可以计算 a,b,c 将被移除的溢出量是多少:  
 a 被移除溢出量:\(200\*1/1000\)\*200，即约等于 40px  
 b 被移除溢出量:\(200\*1/1000\)\*200，即约等于 40px  
 c 被移除溢出量:\(200\*3/1000\)\*200，即约等于 120px  
 最后 a,b,c 的实际宽度分别为:200-40=160px, 200-40=160px, 200-120=80px









