# 一、文档树

## DOM 对象

DOM，全称“DocumentObjectModel\(文档对象模型\)”，它是由 W3C 组 织定义的一个标准。

在前端开发时，我们往往需要在页面某个地方添加一个元素或者删除元素，这种添 加元素、删除元素的操作就是通过 DOM 来实现的。

> **DOM 就是一个接口\(API\)，我们可以通过 DOM 来操作页面中各种元 素，例如添加元素、删除元素、替换元素等**

DOM 就是文档对象模型，文档对象模型就是 DOM。

### DOM 包含内容:

####     DOM Core

####     DOM HTML

####     DOM Style

####     DOM Event

### DOM 结构

DOM 采用树形结构作为分层结构，以树节点形式表示页面中各种元素或内容。下图左边的 HTML 文档用 DOM 树形结构表示如下:

##### ![](/assets/屏幕快照 2018-04-14 上午8.41.14.png)在 DOM 中，每一个元素看成一个节点，而每一个节点就是一个“对象”。也就是我 们在操作元素时，把每一个元素节点看成一个对象，然后使用这个对象的属性和方法进行相关操作。

#### 节点遍历:![](/assets/屏幕快照 2018-04-14 上午8.43.51.png)

在 DOM 中，遍历 HTML 文档树，我们可以通过使用 parentNode、firstChild、 lastChild、previousSibling 和 nextSibling 等属性来实现。

![](/assets/屏幕快照 2018-04-14 上午8.44.35.png)其实除了上表列举的属性之外，还有 nodeName、nodeValue 和 nodeType 等几个比 较重要的属性。

#### 节点类型:

![](/assets/屏幕快照 2018-04-14 上午8.45.21.png)

> **1. 元素节点:上图中&lt;body&gt;、&lt;p&gt;、&lt;div&gt;等都是元素节点，即标签。  
> 2. 文本节点:向用户展示的内容，如&lt;p&gt;...&lt;/p&gt;中的 hello/mooc 等文本。  
> 3. 属性节点:元素属性，如&lt;a&gt;标签的链接属性 href="http://www.163.com"。 \(COMMENT\_NODE/DOCUMENT\_TYPE\_NODE 节点不经常使用。\)**



#### 节点属性

在文档对象模型 \(DOM\) 中，每个节点都是一个对象。DOM 节点有三个重要的属性 : 

> ** 1. nodeName : 节点的名称  
>  2. nodeValue :节点的值  
>  3. nodeType :节点的类型**

一、**nodeName 属性:**节点的名称，是只读的。

> 1. 元素节点的 nodeName 与标签名相同  
>  2. 属性节点的 nodeName 是属性的名称  
>  3. 文本节点的 nodeName 永远是 \#text  
>  4. 文档节点的 nodeName 永远是 \#document

二、**nodeValue 属性:**节点的值

> 1. 元素节点的 nodeValue 是 undefined 或 null
>
> 2. 文本节点的 nodeValue 是文本自身
>
> 3. 属性节点的 nodeValue 是属性的值

三、**nodeType 属性:节点的类型，是只读的**。以下常用的几种结点类型:

![](/assets/屏幕快照 2018-04-14 上午8.49.03.png)

#### 元素遍历![](/assets/屏幕快照 2018-04-14 上午8.49.37.png)

## 如何实现浏览器兼容版的element.children

在Javascript中，可以通过children来获取所有子节点。  
语法:nodeObject.children  
其中，nodeObject为节点对象\(元素节点\)，返回值为所有子节点的集合\(数组\)。

例如，获取id="demo"的节点的所有子节点:

```
document.getElementById("demo").children;
```

**children只返回HTML节点，甚至不返回文本节点**，虽然不是标准的DOM属性，但是得到 了几乎所有浏览器的支持。  
注意:在IE中，children包含注释节点。

一般情况下，我们是希望获取元素节点，可以通过nodeType属性来进行筛选，nodeType==1的节点为元素节点

![](/assets/屏幕快照 2018-04-14 上午8.51.54.png)













