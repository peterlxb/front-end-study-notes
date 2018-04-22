### 编写表单包括三个部分:

1.构建表单  
2.服务器处理\(提供接受数据接口\)

3.配置表单

### 构建表单:

以“披萨预订表单”为例来介绍

![](/assets/屏幕快照 2018-04-22 下午8.04.10.png)

### 服务器处理

提供接口来处理用户提交数据。服务器处理的基本信息包括:

> **https://pizza.example.com/order:服务器端提供接口地址**
>
> **application/x-www-form-urlencoded:服务器端接收数据使用url方式编码**
>
> **custname、custtel、custemail、size、topping、delivery:服务器端 接收参数信息。**

### 配置表单

### ![](/assets/屏幕快照 2018-04-22 下午8.06.09.png)

### 验证表单

通过在元素上增加”required”属性来强制用户填写相应信息:

![](/assets/屏幕快照 2018-04-22 下午8.07.00.png)



























