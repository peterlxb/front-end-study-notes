# BOM

##### 广义的JS包含三部分:

![](/assets/屏幕快照 2018-04-21 上午8.35.29.png)

BOM为浏览器窗口对象的一组API.

## BOM结构图

## ![](/assets/屏幕快照 2018-04-21 上午8.36.04.png)BOM属性:

## ![](/assets/屏幕快照 2018-04-21 上午8.36.40.png)

### navigator.userAgent

可以通过navigator.userAgent判断当前设备运行在什么浏览器上，其包含信息:

![](/assets/屏幕快照 2018-04-21 上午8.37.24.png)

### location:浏览器定位和导航

location最重要属性为href,，它代表浏览器访问当前资源的完整路径，可以通过修改url属性进行浏览器跳转。  
![](/assets/屏幕快照 2018-04-21 上午8.38.21.png)

#### location属性的方法:

> **assign\(url\) 载入新的 url，记录浏览记录**
>
> **replace\(url\) 载入新的 url 不记录浏览记录**
>
> **reload\(\) 重新载入当前页**

### history属性:

浏览器当前窗口的浏览历史，其包含的方法有:

> **back\(\)后退**
>
> **forward\(\)前进  
> go\(\)正数向前，负数向后**

### Screen属性:屏幕信息

![](/assets/屏幕快照 2018-04-21 上午8.40.29.png)

## Window对象\(BOM\)下的方法:

![](/assets/屏幕快照 2018-04-21 上午8.40.55.png)

打开或关闭窗口:open\(\)/close\(\)

```
var w = window.open('subwindow.html', 'subwin', 'width=300, height=300, status=yes, resizable=yes');
// 既可关闭窗口
w.close();
```

## Window对象事件

![](/assets/屏幕快照 2018-04-21 上午8.41.48.png)













