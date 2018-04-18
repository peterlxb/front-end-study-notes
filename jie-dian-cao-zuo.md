# 节点操作

## 获取节点

> getElementById  
> getElementsByClassName
>
> getElementsByTagName
>
> querySelector

### getElementById 返回指定ID的节点

![](/assets/屏幕快照 2018-04-14 上午8.57.12.png)示例:![](/assets/屏幕快照 2018-04-14 上午9.01.14.png)

### getElementsByClassName

#### ![](/assets/屏幕快照 2018-04-14 上午9.02.19.png)示例:获取span元素

#### ![](/assets/屏幕快照 2018-04-14 上午9.02.55.png)

### getElementsByTagName

![](/assets/屏幕快照 2018-04-14 上午9.03.36.png)

#### 示例:获取span标签

### ![](/assets/屏幕快照 2018-04-14 上午9.04.06.png)querySelector

### ![](/assets/屏幕快照 2018-04-14 上午9.04.41.png)![](/assets/屏幕快照 2018-04-14 上午9.05.06.png)

## 创建节点

> **createElement**
>
> **innerHTML**

### createElement

![](/assets/屏幕快照 2018-04-14 上午9.07.49.png)![](/assets/屏幕快照 2018-04-14 上午9.08.11.png)

### innerHTML

![](/assets/屏幕快照 2018-04-14 上午9.08.53.png)

![](/assets/屏幕快照 2018-04-14 上午9.09.16.png)

![](/assets/屏幕快照 2018-04-14 上午9.09.34.png)

## 创建文本节点 createTextNode

createTextNode\(\) 方法创建新的文本节点，返回新创建的 Text 节点。

![](/assets/屏幕快照 2018-04-14 上午9.10.24.png)createElement & innerHTML应用:

> **节点个数  
> 事件处理  
> 结合使用**

以下代码是createElement & innerHTML两者结合使用的例子:

## ![](/assets/屏幕快照 2018-04-14 上午9.11.35.png)插入节点

```
appendChild
isertBefore
insertAdjacentElement
insertAdjacentHTML
```

### appendChild

![](/assets/屏幕快照 2018-04-17 上午8.40.57.png)![](/assets/屏幕快照 2018-04-17 上午8.40.57.png)

![](/assets/屏幕快照 2018-04-17 上午8.44.41.png)

![](/assets/屏幕快照 2018-04-17 上午8.40.57.png)

### insertBefore![](/assets/屏幕快照 2018-04-18 上午8.21.34.png)

![](/assets/屏幕快照 2018-04-18 上午8.23.34.png)![](/assets/屏幕快照 2018-04-18 上午8.24.09.png)



### insertAdjacentElement![](/assets/屏幕快照 2018-04-18 上午8.24.42.png)

### ![](/assets/屏幕快照 2018-04-18 上午8.25.03.png)insertAdjacentHTML

### ![](/assets/屏幕快照 2018-04-18 上午8.25.40.png)



应用-insertAdjacentElement-兼容性方法:

![](/assets/屏幕快照 2018-04-18 上午8.26.04.png)

## 修改节点

### innerHTML

万能的innerHTML![](/assets/屏幕快照 2018-04-18 上午8.26.57.png)

### textContent\(innerText\):

textContent是W3C定义的标准，而innerText不是一个标准，但是一个流行使用的属性。

FF兼容innerText解决方法:![](/assets/屏幕快照 2018-04-18 上午8.28.04.png)

### innerHTML VS textContent\(innerText\)

![](/assets/屏幕快照 2018-04-18 上午8.28.43.png)在 JavaScript 中，我们可以使用 innerHTML 和 innerText 这 2 个属性很方便地获 取和设置某一个元素内部子元素或文本。innerHTML 属性被多数浏览器所支持，而 innerText 只能被 IE、chrome 等支持 而不被 Firefox 支持。

> **innerHTML 属性声明了元素含有的 HTML 文本，不包括元素本身的开始标记和结 束标记。设置该属性可以用于为指定的 HTML 文本替换元素的内容。**

> **innerText 属性与 inerHTML 属性的功能类似，只是该属性只能声明元素包含的文本内容。即使指定的是 HTML 文本，它也会认为是普通文本而原样输出。**

## 删除节点

### removeChild

![](/assets/屏幕快照 2018-04-18 上午8.30.48.png)

### replaceChild

![](/assets/屏幕快照 2018-04-18 上午8.31.45.png)![](/assets/屏幕快照 2018-04-18 上午8.32.06.png)应用:

replaceChild == removeChild&appendChild

### innerHTML

elm.innerHTML=" "



### 

### 

### 

### 

### 

### 

### 

### 

### 

###  











