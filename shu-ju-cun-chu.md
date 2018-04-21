## 数据存储

### Cookie

浏览器中的 Cookie 是指小型文本文件，通常在 4KB 大小左右。

Cookie 由键值对构成用 ，键值对间用;\(分号空格\)隔开

存储在浏览器端，但大部分时候是在服务器端对 Cookie 进行设置，在头文件 中Set-Cookie来对 Cookie 进行设置。

#### Cookie属性

![](/assets/屏幕快照 2018-04-21 上午8.08.55.png)

> **Name,Value为必填属性  
> Expires\(时间戳\)、Max-Age\(毫秒数值\)  
> 标识唯一的Cookie值:Name + Domain + Pat**h

#### Cookie作用域

![](/assets/屏幕快照 2018-04-21 上午8.09.49.png)

#### Cookie作用路径

![](/assets/屏幕快照 2018-04-21 上午8.10.24.png)

#### Cookie读取

以下代码，将Cookie转化为JavaScript对象:

![](/assets/屏幕快照 2018-04-21 上午8.11.08.png)

#### Cookie设置/修改

1. 为 document.cookie 进行赋值: 

document.cookie = 'name=value';

2.设置Cookie值的封装函数

![](/assets/屏幕快照 2018-04-21 上午8.12.13.png)

![](/assets/屏幕快照 2018-04-21 上午8.12.34.png)

#### Cookie缺陷

![](/assets/屏幕快照 2018-04-21 上午8.13.16.png)

**Cookie 作用:一定程度上弥补了 http 无状态协议对交互式 web 应用的影响，它可以使用客 户端存储部分信息，维护用户和服务器会话中的状态。**

### Storage

因为 Cookie 弊端的存在，所以在 HTML5 中提供了 Storage 作为客户端存储的替代方案。 

根据有效期与作用域的不同， Storage 分为 Local Storage 和 Session Storage，前者在 用户不清理的情况下默认时间为永久，后者默认时间则为浏览器。

![](/assets/屏幕快照 2018-04-21 上午8.14.26.png)

#### Storage作用域

![](/assets/屏幕快照 2018-04-21 上午8.15.04.png)

#### Storage大小:

不同浏览器对 Storage 实现的不同导致支持大小也不太一样，通常在 5MB 作用。

### JS对象

可以简单的将Storage理解为一个对象，其增删查改可以以对象的方式进行。

读取  
localStorage.name

  
添加或修改

localStorage.name = 'Value'; 

目前浏览器只支持字符串在 Storage 中的存储。

删除  
delete localStorage.name  


#### API

W3C 有定义专门的 API 来对 Storage 进行增删查改.  
 使用 API 操作 Storage 的作用:  
 可以进行向下兼容的功能，在不支持 Storage 的情况下可以用 Cookie 来代替。

![](/assets/屏幕快照 2018-04-21 上午8.17.08.png)











  
























  




























