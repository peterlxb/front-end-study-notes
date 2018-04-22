### 隐式提交

如:聚焦在输入框时按回车提交表单

满足以下任一条件

1.表单有非禁用的提交按键![](/assets/屏幕快照 2018-04-23 上午7.45.07.png)2.没有提交按键时，不超过一个类型为text search url email passport date time number的input元素。

![](/assets/屏幕快照 2018-04-23 上午7.46.45.png)

此时在输入框里输入后，按回车键，也可以隐式的提交表单。

## 提交过程

> **根据表单 enctype 指定的值构建要提交的数据结构  
> 使用method指定的方式发送数据到action指定的目标。**

## 构建提交数据

> **从可提交元素中提取数据组成指定的数据结构过程  
> 可提交元素有 button input keygen object select textarea**

### 编码方式\(enctype\)

enctype 所支持的形式:

> **application/x-www-form-urlencoded \(默认，数据格式为 & 分隔的键值对\)  
> multipart/form-data \(IFC 2388 字节流形式，例如文件上传所使用的数据编码形式\)**
>
> **text/plain \(回车换行符分隔的键值对\)**

### ![](/assets/屏幕快照 2018-04-23 上午7.50.22.png)![](/assets/屏幕快照 2018-04-23 上午7.50.44.png)特殊案例

1. 当一个表单元素name="isindex"并且type="text"而且满足如下要求时:

> **编码格式为 application/x-www-form-urlencoded**
>
> **作为表单的第一个元素  
> 则提交时只发送 value 值，不包含 name。**

![](/assets/屏幕快照 2018-04-23 上午7.52.13.png)

2. 当name="\_charset\_"并且类型为 type=”hidden”时，而且满足如下要求时:

> **没有设置 value 值**
>
> **提交时 value 自动使用当前提交的字符集填充。**

![](/assets/屏幕快照 2018-04-23 上午7.53.04.png)

## 表单提交接口:

### submit\(\)

提交表单:form.submit\(\);

### onsubmit\(\)

> **表单提交事件  
> 提交之前的数据验证  
> 阻止事件的默认行为来取消表单提交**

![](/assets/屏幕快照 2018-04-23 上午7.54.26.png)

### 无刷新表单提交范例:

常用的方式是通过 AJAX 进行实现，这里使用 iframe 来做中介代理实现。

![](/assets/屏幕快照 2018-04-23 上午7.55.06.png)

![](/assets/屏幕快照 2018-04-23 上午7.55.30.png)

利用iframe实现表单的无刷新提交，兼容到主流浏览器\(IE6+，Firefox最新，Chrome最新\).

![](/assets/屏幕快照 2018-04-23 上午7.56.48.png)![](/assets/屏幕快照 2018-04-23 上午7.57.24.png)



























































