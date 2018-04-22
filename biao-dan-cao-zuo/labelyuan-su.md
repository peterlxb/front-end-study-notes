## label元素

![](/assets/屏幕快照 2018-04-23 上午7.10.23.png)

![](/assets/屏幕快照 2018-04-23 上午7.10.44.png)

### htmlFor属性:

> **关联表单控件的激活行为\(可使点击label与点击表单控件的行为一致\)**
>
> **可关联元素:button,input\(除 hidden 外\)，keygen, meter,output, progress,select,textaea**

![](/assets/屏幕快照 2018-04-23 上午7.11.58.png)

### control属性

> **如果指定了for属性，则为该for属性对应ID的可关联元素**
>
> **如果没有指定for属性,则为第一个子孙可关联元素。**

![](/assets/屏幕快照 2018-04-23 上午7.13.05.png)

### form属性

> **关联归属表单**
>
> **可关联元素:button/fieldset,input,keygen,laberl,object, output,select, textarea**
>
> **只读属性，不可在程序中修改**

可通过label.setAttribute\(‘form’,’newFormID’\)来修改。















































