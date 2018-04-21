# Canvas

基本用法

![](/assets/屏幕快照 2018-04-21 上午8.29.36.png)

画布&lt;canvas&gt;的默认宽高为 300 与 150 ，但是同样可以使用 CSS 设定宽高。但因 为 CSS 与 JavaScript 在渲染工程中有速度的差异，所以不建议使用CSS 对&lt;canvas&gt;的宽高做设定。

###  渲染上下文对象

canvas起初是空白的。为了展示，首先脚本需要找到渲染上下文，然后在它的上面绘制。&lt;canvas&gt;元素有一个做getContext\(\)的方法，这个方法是用来获得渲染上下文和它 的绘画功能。getContext\(\)只有一个参数，上下文的格式。

下面代码中的ctx即为渲染上下文对象。

```
var canvas = document.getElementById('tutorial'); 
var ctx = canvas.getContext('2d');
// 绘画 canvas 的属性
ctx.globalCompositeOperation = 'destination-over';
```

globalCompositeOperation\(全局的组合操作\)为对于canvas绘画时的渲染属性 设置，具体表现如下图:

![](/assets/屏幕快照 2018-04-21 上午8.31.24.png)



#### 基本绘图的步骤

![](/assets/屏幕快照 2018-04-21 上午8.32.01.png)



![](/assets/屏幕快照 2018-04-21 上午8.32.22.png)

上图的实现代码如下:

![](/assets/屏幕快照 2018-04-21 上午8.32.46.png)

![](/assets/屏幕快照 2018-04-21 上午8.33.08.png)

Mozilla官方教程: [https://developer.mozilla.org/zh-CN/docs/Web/API/Canvas\_API/Tutorial](https://developer.mozilla.org/zh-CN/docs/Web/API/Canvas_API/Tutorial)







