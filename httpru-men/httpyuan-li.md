HTTP is the language that web browsers and web servers speak to each other.

## 1.背景知识

官方术语是超文本传输协议，是一种详细规定了浏览器和万维网\(WWW = World Wide Web\)服务器之间互相通信的规则，通过因特网传送万维网文档的数据传送协议。

**HTTP协议是用于从web服务器传输超文本到本地浏览器的传送协议。**它可以使浏览器更加高效，使网络传输减少。它不仅保证计算机正确快速地传输超文本文档，还确定传输文档中的哪一部分，以及哪部分内容首先显示\(如文本先于图形\)等。

**HTTP是一个应用层协议，由请求和响应构成，是一个标准的客户端服务器模型。HTTP是一个无状态的协议。**

**在Internet中所有的传输都是通过TCP/IP进行的。**HTTP协议作为TCP/IP模型中应用层的协议也不例外。HTTP协议通常承载于TCP协议之上，有时也承载于TLS或SSL协议层之上，这个时候，就成了我们常说的HTTPS。

## 2.特点

**HTTP协议永远都是客户端发起请求，服务器回送响应。**这样就限制了使用HTTP协议，无法实现在客户端没有发起请求的时候，服务器将消息推送给客户端。

HTTP协议的主要**特点**可概括如下：

1、支持客户/服务器模式。支持基本认证和安全认证。

2、简单快速：客户向服务器请求服务时，只需传送请求方法和路径。请求方法常用的有GET、HEAD、POST。每种方法规定了客户与服务器联系的类型不同。由于HTTP协议简单，使得HTTP服务器的程序规模小，因而通信速度很快。

3、灵活：HTTP允许传输任意类型的数据对象。正在传输的类型由Content-Type加以标记。

4、HTTP 0.9和1.0使用非持续连接：限制每次连接只处理一个请求，服务器处理完客户的请求，并收到客户的应答后，即断开连接。HTTP 1.1使用持续连接：不必为每个web对象创建一个新的连接，一个连接可以传送多个对象，采用这种方式可以节省传输时间。

5、无状态：HTTP协议是无状态协议。**无状态是指协议对于事务处理没有记忆能力。缺少状态意味着如果后续处理需要前面的信息，则它必须重传，这样可能导致每次连接传送的数据量增大。**

### **无状态协议：**

协议的状态是指下一次传输可以“记住”这次传输信息的能力。

http是不会为了下一次连接而维护这次连接所传输的信息,为了保证服务器内存。

比如客户获得一张网页之后关闭浏览器，然后再一次启动浏览器，再登陆该网站，但是服务器并不知道客户关闭了一次浏览器。

**由于Web服务器要面对很多浏览器的并发访问，为了提高Web服务器对并发访问的处理能力，在设计HTTP协议时规定Web服务器发送HTTP应答报文和文档时，不保存发出请求的Web浏览器进程的任何状态信息。**

这有可能出现一个浏览器在短短几秒之内两次访问同一对象时，服务器进程不会因为已经给它发过应答报文而不接受第二期服务请求。由于Web服务器不保存发送请求的Web浏览器进程的任何信息，因此HTTP协议属于无状态协议（Stateless Protocol）。

### **HTTP协议是无状态的和Connection: keep-alive的区别：**

无状态是指协议对于事务处理没有记忆能力，服务器不知道客户端是什么状态。从另一方面讲，打开一个服务器上的网页和你之前打开这个服务器上的网页之间没有任何联系。

HTTP是一个无状态的面向连接的协议，无状态不代表HTTP不能保持TCP连接，更不能代表HTTP使用的是UDP协议（无连接）。

从HTTP/1.1起，默认都开启了Keep-Alive，保持连接特性，**简单地说，当一个网页打开完成后，客户端和服务器之间用于传输HTTP数据的TCP连接不会关闭，如果客户端再次访问这个服务器上的网页，会继续使用这一条已经建立的连接。**

Keep-Alive不会永久保持连接，它有一个保持时间，可以在不同的服务器软件（如Apache）中设定这个时间。



HTTP是基于传输层的TCP协议，而TCP是一个端到端的面向连接的协议。所谓的端到端可以理解为进程到进程之间的通信。所以HTTP在开始传输之前，首先需要建立TCP连接，而TCP连接的过程需要所谓的“三次握手”。

因特网通过IP地址区分计算机。互联网上的每一项网络流量都标有发送和接收计算机的IP地址。

比如要与服务器地址为www.udacity.com的网站连接，客户端需要将这个主机名解析成相应的IP地址，两个IP地址之间才能相互通信。在操作系统的网络配置里有ISP运营商维护的DSN域名系统，查询主机名并返回IP地址。



### _**请求方法**_

HTTP/1.1协议中共定义了八种方法（有时也叫“动作”）来表明Request-URI指定的资源的不同操作方式：

OPTIONS - 返回服务器针对特定资源所支持的HTTP请求方法。也可以利用向Web服务器发送'\*'的请求来测试服务器的功能性。

HEAD - **向服务器索要与GET请求相一致的响应，只不过响应体将不会被返回。**这一方法可以在不必传输整个响应内容的情况下，就可以获取包含在响应消息头中的元信息。该方法常用于测试超链接的有效性，是否可以访问，以及最近是否更新。

GET - **向特定的资源发出请求**。注意：GET方法不应当被用于产生“副作用”的操作中，例如在web app.中。其中一个原因是GET可能会被网络蜘蛛等随意访问。

POST - **向指定资源提交数据进行处理请求（例如提交表单或者上传文件）**。数据被包含在请求体中。POST请求可能会导致新的资源的建立和/或已有资源的修改。

PUT - **向指定资源位置上传其最新内容。**

DELETE - **请求服务器删除Request-URI所标识的资源。**

TRACE - 回显服务器收到的请求，主要用于测试或诊断。

CONNECT - HTTP/1.1协议中预留给能够将连接改为管道方式的代理服务器。

PATCH - 用来将局部修改应用于某一资源，添加于规范RFC5789。

方法名称是区分大小写的。当某个请求所针对的资源不支持对应的请求方法的时候，服务器应当返回状态码405（Method Not Allowed）；当服务器不认识或者不支持对应的请求方法的时候，应当返回状态码501（Not Implemented）。

HTTP服务器至少应该实现GET和HEAD方法，其他方法都是可选的。



**GET和POST的区别**：

1、**GET提交的数据会放在URL之后，以?分割URL和传输数据，参数之间以 & 相连，**如EditPosts.aspx?name=test1&id=123456. POST方法是把提交的数据放在HTTP包的Body中。

2、**GET提交的数据大小有限制，最多只能有1024字节（因为浏览器对URL的长度有限制），而POST方法提交的数据没有限制。**

3、**GET方式需要使用Request.QueryString来取得变量的值，而POST方式通过Request.Form来获取变量的值。**

4、**GET方式提交数据，会带来安全问题，比如一个登录页面，通过GET方式提交数据时，用户名和密码将出现在URL上，如果页面可以被缓存或者其他人可以访问这台机器，就可以从历史记录获得该用户的账号和密码。**










