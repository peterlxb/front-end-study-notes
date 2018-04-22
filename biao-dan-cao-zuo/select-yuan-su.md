## select元素![](/assets/屏幕快照 2018-04-23 上午7.19.21.png)

### select具有的属性和\(接口\)方法如下:

> **        name:表单名称**
>
> * ** value:第一个选中的选项的value值**
>
> * ** multiple:多选**
>
> * ** options\(动态节点集合\)**
>
> * ** selectedOptions\(所有已经选中的选项集合，动态节点集合\)**
>
> * ** selectedIndex:第一个选中选项的索引值，没有元素选中的话，返回-1.**
>
> * ** add\(element\[,before\]\):在指定的位置之前添加选项用，无指定参照物则在最后添加**
>
>   **选项。**
>
> * ** remove\(\[index\]\):删除某个选项**



#### optgroup所具有的属性和方法:

> **disabled \(分组选项不可选\)**
>
> **label\(分组说明\)**

#### option所具有的属性和方法:

> **disabled  
> label\(描述信息\)  
> value\(提交表单时的数据信息\)  
> text\(显示在页面上用户看到的文字\)  
> index:当前选项的索引值  
> selected  
> defaultSelected:默认情况下选项是否选中**



### select选项操作

#### 创建选项

```
document.createElement('option')
new Option([text[, value[, defaultSelected[, selected]]]])
```

#### ![](/assets/屏幕快照 2018-04-23 上午7.23.09.png)

#### 添加选项

> **insertBefore**
>
> **select.add**

![](/assets/屏幕快照 2018-04-23 上午7.24.07.png)

![](/assets/屏幕快照 2018-04-23 上午7.24.27.png)

#### 删除选项

> **removeChild**
>
> **select.remove**

![](/assets/屏幕快照 2018-04-23 上午7.25.17.png)

![](/assets/屏幕快照 2018-04-23 上午7.25.33.png)

### 级联下列选择器案例:

![](/assets/屏幕快照 2018-04-23 上午7.26.15.png)

所需知识点:

> **onchange**
>
> **remove**
>
> **add**

![](/assets/屏幕快照 2018-04-23 上午7.28.04.png)

![](/assets/屏幕快照 2018-04-23 上午7.28.24.png)







































