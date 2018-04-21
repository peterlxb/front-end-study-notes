### 动画原理:

帧:为动画的最小单位，一个静态的图像。

帧频:每秒播放的帧的数量。

一个动画是由很多帧组成的，因为人眼的暂留特性，当图片交替的速度大于每秒 30 帧 以上即有动画的感觉。

### 实现方式

> **gif: 图像形式存储，容量大，需第三方制图工具制作。  
> CSS3: 实现动画具有局限性  
> JavaScript: 可实现大部分动画效果**

### JavaScript 动画三要素

![](/assets/屏幕快照 2018-04-21 上午8.18.55.png)

#### setInterval

```
var intervalId = setInterval(func, delay[, param1, param2, ...]); 
clearInterval(intervalId);
```

> **func为执行改变属性的操作  
> delay为触发的时间间隔\(毫秒为单位\)  
> para1为执行时可传入改变属性函数的参数**
>
> **clearInterval 为清除动画效果**

#### setTimeout

```
var timeoutId = setTimeout(func[, delay, param1, param2, ...]); 
clearTimeout(timeoutId);
```

#### requestAnimationFrame 

类似于setTimeout但是无需设定时间间隔。

此定时器为 HTML5 中的新标准，现代浏览器实现很好，其间隔时间不由用户控制，而 是由显示器的刷新频率控制。\(市面上的显示器刷新频率为每秒刷新 60 次，因此大概 16.67 毫秒刷新一次，每当浏览器刷新时，便会触发此函数。\)

```
var requestID = requestAnimationFrame(func); 
cancelAnimationFrame(requestID);
```

### 常见动画

大多数的复杂动画都是有下列的简单动画所组成的。

> **形变，改变元素的宽高 **
>
> **位移，改变元素相对位置 **
>
> **旋转 **
>
> **透明度**

#### 动画函数

```
var animation = function(ele, attr, from, to) { 
  var distance = Math.abs(to - from);
  var stepLength = distance/100;
  var sign = (to - from)/distance;
  var offset = 0;
  var step = function(){
    var tmpOffset = offset + stepLength; 
    if (tmpOffset < distance) {
      ele.style[attr] = from + tmpOffset * sign + 'px';
      offset = tmpOffset;
    } else {
      ele.style[attr] = to + 'px';
      clearInterval(intervalID);
    }
  }
  ele.style[attr] = from + 'px';
  var intervalID = setInterval(step, 10);
}
```

#### 图片轮播

##### 进度条

以下为三种实现方式\(setInterval/setTimeout/requestAnimationFrame\)

![](/assets/屏幕快照 2018-04-21 上午8.24.36.png)

![](/assets/屏幕快照 2018-04-21 上午8.24.57.png)

![](/assets/屏幕快照 2018-04-21 上午8.25.17.png)

![](/assets/屏幕快照 2018-04-21 上午8.25.36.png)

##### 左右移动

![](/assets/屏幕快照 2018-04-21 上午8.26.07.png)

































