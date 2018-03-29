# CSS3 渐变

**CSS3 渐变共有 2 种:\(1\)线性渐变\(linear-gradient\);\(2\)径向渐变 \(radial-gradient\)。**

## 1、线性渐变-linear-gradient

线性渐变，指的就是指在一条直线上进行渐变，在网页中大多数渐变效果都是线性渐变。![](/assets/屏幕快照 2018-03-29 上午8.21.43.png)说明:线性渐变的方向取值有 2 种，一种是使用角度\(deg\)，另外一种是使用关键字:

![](/assets/屏幕快照 2018-03-29 上午8.22.19.png)第 2 个参数和第 3 个参数，表示开始颜色和结束颜色，取值可以为关键字、十六进

制颜色值、RGBA 颜色等。你可以使用在线调色板来获取颜色值。线性渐变可以有多个 颜色值。

也可以定义多种颜色的线性渐变效果，如:![](/assets/屏幕快照 2018-03-29 上午8.23.06.png)![](/assets/屏幕快照 2018-03-29 上午8.23.33.png)

## 2、径向渐变-radial-gradient

径向渐变，是一种从起点到终点颜色从内到外进行圆形渐变\(从中间向外拉，像圆 一样\)。CSS3 径向渐变是圆形或椭圆形渐变，颜色不再沿着一条直线渐变，而是从一 个起点向所有方向渐变。

语法:background:radial-gradient\(position ,shape size,start-color,...,stop-color\)

说明:

1.position:定义圆心位置,如果提供 2 个参数，第一个表示横坐标，第二个表示纵坐 标;如果只提供一个，第二值默认为 50%，即 center.

2.shape size:由 2 个参数组成，shape 定义形状\(圆形或椭圆\)，size 定义大小; 

3.start-color:定义开始颜色值;  
4.stop-color:定义结束颜色值;  
5.position、shape size 都是可选参数，如果省略，则表示该项参数采用默认值\(center,ellipse\)。start-color 和 stop-color 为必选参数，并且径向渐变可以有多个颜色值。

### 1、定义圆心位置 position

**position 用于定义径向渐变的圆心位置，属性值跟 background-position 属性值相似，也 有 2 种情况:\(1\)长度值，如 px、em 或百分比等;\(2\)关键字。**![](/assets/屏幕快照 2018-03-29 上午8.25.51.png)

### 2、定义形状 shape 和定义大小 size

\(1\)定义形状 shape![](/assets/屏幕快照 2018-03-29 上午8.27.40.png)\(2\)定义大小 size

size 主要用于定义径向渐变的结束形状大小。![](/assets/屏幕快照 2018-03-29 上午8.28.19.png)

### 3、开始颜色 start-color 和结束颜色 stop-color

参数 start-color 用于定义开始颜色，参数 stop-color 用于定义结束颜色。颜色可以为关 键词、十六进制颜色值、RGBA 颜色值等。

径向渐变也接受一个颜色值列表，用于同时定义多种颜色的径向渐变。

默认情况下，径向渐变颜色节点是均匀分布的，不过我们也可以为每一种颜色添加百分比来使得各个颜色节点不均匀分布.

##### 案例:

#####  1. 用默认的渐变方向绘制一个最简单的径向渐变 

##### 示例代码:

![](/assets/屏幕快照 2018-03-29 上午8.29.35.png)

\(图一\)

radial-gradient\(circle, \#f00, \#ff0, \#080\);  
radial-gradient\(circle at center, \#f00, \#ff0, \#080\);  
radial-gradient\(circle at 50%, \#f00, \#ff0, \#080\);  
radial-gradient\(circle farthest-corner, \#f00, \#ff0, \#080\);

以上几句代码都可以实现如\(图一\)的渐变效果

##### 2.&lt;shape&gt;和&lt;size&gt;使用注意:

错误代码:

`radial-gradient(circle 50px 50px, #f00, #ff0, #080);`  
 因为 circle 是正圆，一个值就能表示其直径长度，所以此时&lt;size&gt;只能是一个值。

  
错误代码:

`radial-gradient(circle 50%, #f00, #ff0, #080);` 

circle 不接受&lt;size&gt;的值是&lt;percentage&gt;。

#####  3.不通过&lt;shape&gt;来表示圆和椭圆的方法:

以下 2 行代码都可以表示一个圆:

radial-gradient\(100px, \#f00, \#ff0, \#080\); /\* 1 \*/

radial-gradient\(100px 100px, \#f00, \#ff0, \#080\); /\* 2 \*/

radial-gradient\(50px 100px, \#f00, \#ff0, \#080\); /\* 3 \*/  
代码1:只给出100px，所以被当成是正圆的半径，于是就能确定一个直径为100px的圆;

代码2:给出了2个值，按理应该是要画一个椭圆的，但2个值相等，所以这个椭圆其实此时是个正圆形态。需要注意的是，代码 2 如果加上 circle，那将是错误语法，因为这是 2 个值只有椭圆才接受

代码3:表示了一个水平半径为50px，垂直半径为100px的椭圆

## 3、渐变重复: repeating-\*-gradient

1.用重复的线性渐变创建图像。

 repeating-linear-gradient\(\)的语法与 linear-gradient\(\)相同。 

示例代码:

![](/assets/屏幕快照 2018-03-29 上午8.35.12.png)

repeating-linear-gradient\(\#f00, \#ff0 10%, \#f00 15%\);  
repeating-linear-gradient\(to bottom, \#f00, \#ff0 10%, \#f00 15%\);

repeating-linear-gradient\(180deg, \#f00, \#ff0 10%, \#f00 15%\);  
repeating-linear-gradient\(to top, \#f00, \#ff0 10%, \#f00 15%\);



2.用重复的径向渐变创建图像。 

repeating-radial-gradient\(\)的语法与 radial-gradient\(\)相同。

![](/assets/屏幕快照 2018-03-29 上午8.36.23.png)

repeating-radial-gradient\(circle closest-side, \#f00, \#ff0 10%, \#f00 15%\);







