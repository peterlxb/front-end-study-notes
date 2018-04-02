# Float 浮动:

浮动的框可以向左或向右移动，直到它的外边缘碰到包含框或另一个浮动框的边框为止。 由于浮动框不在文档的普通流中，所以文档的普通流中的块框表现得就像浮动框不存在一 样。

#### float 属性定义元素在哪个方向浮动.

以往这个属性总应用于图像，使文本围绕在图像周围，不过在 CSS 中，任何元素都可以浮 动。浮动元素会生成一个块级框，而不论它本身是何种元素。

> 语法:  
> float:none \| left \| right

![](/assets/屏幕快照 2018-04-02 上午8.27.16.png)

# Float 浮动基本特征:

## 1.float 的元素在同一文档流

## ![](/assets/屏幕快照 2018-04-02 上午8.28.13.png)2.float 元素半脱离文档流

![](/assets/屏幕快照 2018-04-02 上午8.29.09.png)对元素，脱离文档流;对内容，在文档流。

# Clear-清除浮动:

**元素浮动之后，周围的元素会重新排列**，为了避免这种情况，使用 clear 属性。

clear 属性规定元素的哪一侧不允许其他浮动元素。

> 语法:
>
> clear:none \| left \| right \| both
>
> ```
> 应用于\(浮动元素\)后续元素;
>
> 应用于块级元素;
> ```

#### 使用方式:

#### 1.增加空白元素

#### 2.Clearfix

#### 代码:

```
 .clearfix:after {
   .Content:”.”;
   display:block;
   clear:both;
   height:0;
   Overflow:hidden;
   visibility:hidden;
  }
 .clearfix{zoom:1;}
```

## Float 应用-两列布局:

![](/assets/屏幕快照 2018-04-02 上午8.33.10.png)![](/assets/屏幕快照 2018-04-02 上午8.33.19.png)

[https://css-tricks.com/all-about-floats/](https://css-tricks.com/all-about-floats/ "All-About-Floats/")

[https://css-tricks.com/almanac/properties/f/float/](https://css-tricks.com/almanac/properties/f/float/ "floats")

在头像中应用浮

```
<section>
  <button>toggle image size</button>
  <div class="user">
    <img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/652/ada-small.jpeg">
    <h3>Ada Lovelace</h3>
    <a href="#">Account</a>
    <a href="#">Change Password</a>
    <a href="#">Log Out</a>
  </div>
</section>
```

```
body {
  background-color: #1D1F1F;
  font-family: 'Source Sans Pro', sans-serif;
}

section {
width: 400px;
margin: 0 auto; 
}

.user {
  width: 400px;
  height: 165px;
  margin: 2em 0;
  border: 3px solid #E18728;
  border-radius: 10px;
  background-color: white;
}

img {
  padding: .5em;
  float: left;
}

a { display: block; }
```

```
$('button').on('click', function() {
  if ($('img').attr('src').indexOf('wide') > -1) {
    $('img').attr('src', 'https://s3-us-west-2.amazonaws.com/s.cdpn.io/652/ada-small.jpeg');
  } else {
    $('img').attr('src', 'https://s3-us-west-2.amazonaws.com/s.cdpn.io/652/ada-wide.jpeg');
  }
});
```

![](/assets/屏幕快照 2018-04-02 上午8.52.07.png)



