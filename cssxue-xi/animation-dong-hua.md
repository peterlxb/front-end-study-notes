# Animation 动画

在 CSS3 中，动画效果使用 animation 属性来实现。animation 属性和transition 属性功能 是相同的，都是通过改变元素的“属性值”来实现动画效果。但是这两者又有很大的区别:

> transition 属性只能通过指定属性的开始值与结束值，然后在这两个属性值之间进行平滑
>
> 过渡来实现动画效果，因此只能实现简单的动画效果。
>
> animation 属性则通过定义多个关键帧以及定义每个关键帧中元素的属性值来实现复杂的动画效果。

> transition 属性只能实现简单的动画\(一个\)，而 animation 属性却可以实现复杂的动画\(一系列\)。

### 定义动画@keyframes \(keyframes:关键帧\)

> 使用 animation 属性定义 CSS3 动画需要 2 步:  
>  \(1\)定义动画;  
>  \(2\)调用动画;

在 CSS3 中，在使用动画之前，我们必须使用@keyframes 规则定义动画。

语法:

```
@keyframes <identifier> '{' <keyframes-blocks> '}';
<keyframes-blocks>:[ [ from | to | <percentage> ]{ sRules } ] [ [ , from | to | <percentage> ]{ sRules } ]*
```

取值:

> &lt;identifier&gt;:identifier定义一个动画名称  
> &lt;keyframes-blocks&gt;: 定义动画在每个阶段的样式，即帧动画。

#### 1. 定义动画时，简单的动画可以直接使用关键字 from 和 to，即从一种状态过渡到另一种状态:

示例代码:

```
@keyframes testanimations {
         from { opacity: 1; }
         to { opacity: 0; }
}
```

其中 testanimations 是该动画的名字，该动画表示某个东西将逐渐消失。

#### 2. 如果复杂的动画，可以混合&lt;percentage&gt;去设置某个时间段内的任意时间点的样式: 

示例代码:

```
@keyframes testanimations {
        from { transform: translate(0, 0); }
        20% { transform: translate(20px, 20px); } 
        40% { transform: translate(40px, 0); } 
        60% { transform: translate(60px, 20); } 
        80% { transform: translate(80px, 0); }
        to { transform: translate(100px, 20px); }
}
```

#### 3. 当然，也可以不使用关键字 from 和 to，而都使用&lt;percentage&gt;: 

示例代码:

```
@keyframes testanimations{
        0% { transform: translate(0, 0); }
        20% { transform: translate(20px, 20px); } 
        40% { transform: translate(40px, 0); }
        60% { transform: translate(60px, 20px); } 
        80% { transform: translate(80px, 0); }
        100% { transform: translate(100px, 20px); }
}
```

> **注意，这里的 0%不能简写成 0。**  
>  **使用@keyframes 规则时，如果仅仅只有 0%和 100%这两个百分比的话，这时 0%和 100%还可 以使用关键词 from 和 to 来代表，其中 0%对应的是 from，100%对应的是 to。**

### 调用动画 animation-name 属性

在 CSS3 中，使用@keyframes 规则定义的动画并不会自动执行，我们还需要使用 animation-name 属性来调用动画，之后动画才会生效。

```
语法:animation-name:动画名;
```

> 注意，animation-name 调用的动画名需要和@keyframes 规则定义的动画名称完全一致\(区分大小写\)，如果不一致将不具有任何动画效果。为了浏览器兼容 性，针对 Chrome 和 Safari 浏览器需要加上-webkit-前缀，而针对 Firefox 浏览器需 要加上-moz-。

### 持续时间 animation-duration 属性

在 CSS3 中，我们可以使用 animation-duration 属性来设置动画的持续时间，也 就是完成从 0%到 100%所使用的总时间。

```
语法:animation-duration: <time>[,<time>]*
```

### 播放方式 animation-timing-function 属性

在 CSS3 中，我们可以使用 animation-timing-function 属性来设置动画的播放方 式，所谓的“播放方式”主要用来指定动画在播放时间内的速率。其中，语法:

```
animation-timing-function: 
<single-animation-timing-function>[,<single-animation-timing-function>]* 
<single-animation-timing-function> = ease | linear | ease-in | 
ease-out | ease-in-out | step-start | step-end | steps(<integer>[, [ start | end ] ]?) | 
cubic-bezier(<number>, <number>, <number>, <number>)
默认值:ease
```

说明:animation-timing-function 属性取值跟 transition-timing-function 属性取值一 样，共有 5 种，具体如下:

![](/assets/屏幕快照 2018-04-10 上午7.58.25.png)

### 延迟时间 animation-delay 属性

在 CSS3 中，我们可以使用 animation-delay 属性来定义动画播放的延迟时间。

```
语法:animation-delay:时间
```

animation-delay 属性默认值为 0，也就是说当我们没有设置 animation-delay 属性时，CSS3 动画就没有延迟时间。

### 播放次数 animation-iteration-count 属性

在 CSS3 中，我们可以使用 animation-iteration-count 属性来定义动画的播放次 数。

![](/assets/屏幕快照 2018-04-10 上午7.59.46.png)

说明:animation-iteration-count 属性取值有 2 种:

    正整数;  
    infinite

animation-iteration-count 属性默认值为 1。也就是默认情况下，动画从开始到结束只播 放一次。

“animation-iteration-count:n”表示动画播放 n 次，n 为正整数;  
当 animation-iteration-count 属性取值为 infinite 时，动画会无限次地循环播放。

### 播放方向 animation-direction 属性

在 CSS3 中，我们可以使用 animation-direction 属性定义动画的播放方向。

```
animation-direction: 
<single-animation-direction>[,<single-animation-direction>]* 
<single-animation-direction> = normal | reverse | alternate | alternate-reverse
```

                                                              animation-direction属性取值![](/assets/屏幕快照 2018-04-10 上午8.01.56.png)

### 播放状态 animation-play-state 属性

在 CSS3 中，我们可以使用 animation-play-state 属性来定义动画的播放状态。

```
语法:animation-play-state:取值;
```

> 说明:animation-play-state 属性取值只有 2 个:running 和 paused。

![](/assets/屏幕快照 2018-04-10 上午8.03.06.png)

### 时间外属性 animation-fill-mode 属性

在 CSS3 中，我们可以使用 animation-fill-mode 属性定义在动画开始之前和动画 结束之后发生的事情。

```
语法:animation-fill-mode:取值;
```

                                                       animation-fill-mode属性取值

![](/assets/屏幕快照 2018-04-10 上午8.04.04.png)

在默认情况之下，动画不会影响它的关键帧之外的属性，使用 animation-fill-mode 属性可以修改动画的 默认行为。简单的说就是告诉动画在第一关键帧上等待动画开始，或者在动画结束时停在最后一个关键帧 上而不回到动画的第一帧上。或者同时具有这两个效果。

例如:让动画停在最一帧处。代码如下:

![](/assets/屏幕快照 2018-04-10 上午8.04.43.png)

### animation

```
语法:animation:<single-animation>[,<single-animation>]*
```

```
<single-animation> = <single-animation-name> || <time> || 
<single-animation-timing-function> || <time> || <single-animation-iteration-count> || 
<single-animation-direction> || <single-animation-fill-mode> || <single-animation-play-state>
```

如果提供多组属性值，以逗号进行分隔。  
如果只提供一个&lt;time&gt;参数，则为 &lt;' animation-duration '&gt; 的值定义;  
如果提供二个&lt;time&gt;参数，则第一个为 &lt;' animation-duration '&gt; 的值定义，第二个为 &lt;' animation-delay '&gt; 的值定义 

案例:

```
animation:animations 2s ease-out forwards; 
@keyframes animations{
    0%{transform:translate(0);opacity:0;} 
    50%{transform:translate(30px);opacity:1;} 
    70%{transform:translate(35px);opacity:1;} 
    100%{transform:translate(60px);opacity:0;}
} 
......
```

动画演示地址[https://css-tricks.com/almanac/properties/a/animation/](https://css-tricks.com/almanac/properties/a/animation/)







  
















  


