## 验证元素

### 可验证元素:button, input, select, textarea

### 以下情况不做验证:

> **input 元素，type 类型为 hidden, reset, button 时**
>
> **button 元素，type 类型为 reset, button 时  
> input /textarea, 当属性为 readonly 时  
> 所有可验证元素作为 datalist 的子孙节点时**
>
> **当元素被禁用时 disabled 的状态**

### 验证涉及到的属性和接口:

> **willValidate \(表明此元素在表单提交时是否会被验证\)  
> checkValidity\(\) \(用于验证元素，返回 true 当验证通过，否则触发 invalid 事件\)**
>
> **validity \(存储验证结果，不同的异常状态都会在这个属性里标明出来\)  
> validationMessage \(显示验证异常信息\)  
> setCustomValidity\(message\) \(自定义验证错误信息\)**

#### validity:存储验证过程中可能涉及到的错误信息，包含以下内容:

![](/assets/屏幕快照 2018-04-23 上午7.41.35.png)

### 自定义异常:

涉及的点包括

> **oninvalid  
> setCustomValidity**

![](/assets/屏幕快照 2018-04-23 上午7.42.33.png)![](/assets/屏幕快照 2018-04-23 上午7.42.57.png)![](/assets/屏幕快照 2018-04-23 上午7.43.15.png)

### 禁止验证:

![](/assets/屏幕快照 2018-04-23 上午7.43.44.png)

如上代码，input类型为number,当输入时，会弹出数字键盘来做验证。这时我们需要其不 对输入的内容进行验证，可以通过在表单里设置novalidate属性来禁止其验证



























