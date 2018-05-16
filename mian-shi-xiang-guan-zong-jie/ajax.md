#### 1.什么是Ajax？

Ajax（Asynchronous JavaScript + XML），即异步JavaScript + XML的缩写，主要用来页面异步刷新，也是构建RIA的一种基础技术。

#### 2.如何使用Ajax从服务器获取数据？

①创建XMLHttpRequest对象，注意兼容IE6的情况

②使用XMLHttpRequest对象的open方法，其中有三个参数：

> **a.字符串，代表html的请求:GET,POST。**
>
> ** b.要访问的服务器的URL。**
>
> ** c.Boolean值，true表示异步，flase表示同步，一般情况下是异步，默认为true。**

③ajax的回调函数。xhr.readyState==4表示请求已经结束，服务器响应完成。

> ** status表示http请求的状态，200表示正常响应；404表示资源找不到；500表示服务器端错误。**

 ④发送ajax请求。如果没有数据，可以不传或者传递null；如果post请求传递数据：首先设置xhr的请求头信息：

一个简单的Ajax操作如下。

```
var xhr = new XMLHttpRequest();
//在环境中需要做浏览器兼容，这里省略了
xhr.onreadystatechange = function() {
//这里注册当xhr状态发生改变后调用事件
if( xhr.readyState == 4 ) {
//通常在读取状态为4的时候才能获取到部分数据
所以一般状态在4的时候才进行处理
if(status==200) {
            //当正常请求到资源时的处理,
可以调用xhr.responseText或xhr.responseXml获取数据
        }
        else {
        //当请求资源失败时的处理
        }
    }
}
xhr.open( "GET", url);
//设置xhr的请求方式和url,这里使用的是GET方式，
 //如果有参数，则连接在url后面
 /*
  如果是POST请求，还当设置请求的Content-Type
  数据使用send作为参数发送
  */
xhr.send();

作者：樱桃小丸子儿
链接：https://www.jianshu.com/p/2f7eb1ad7174
來源：简书
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。

```





