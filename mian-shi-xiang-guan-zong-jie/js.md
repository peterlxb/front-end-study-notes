#### 1.什么是函数柯里化？以及说一下JS的API有哪些应用到了函数柯里化的实现？

#### 2.undefined与null有何异同？

null是一个表示"无"的对象，转为数值时为0；undefined是一个表示"无"的原始值，转为数值时为NaN。

#### 3.String.match与RegExp.exec有何区别？

match只会返回没有分组的全部匹配结果或者有分组的第一次匹配结果；

而exec可以利用循环返回全部匹配结果。

#### 4.为验证手机号写一个正则。

```
function checkSubmitMobil()
 {
 if ($("#phoneNum").val() == "") {
 alert("手机号码不能为空！");
 //$("#moileMsg").html("<font color='red'>手机号码不能为空！</font>"); 
 $("#mobile").focus();
 return false;
   }
if (!$("#phoneNum").val().match(/^(?:13\d|15\d|18\d)\d{5}(\d{3}|\*{3})$/)) 
{
 alert("手机号码格式不正确！");
 //$("#moileMsg").html("<font color='red'>手机号码格式不正确！请重新输入！</font>"); 
$("#phoneNum").focus();
  return false;
  }
    return true;
}
```

#### 5.简述COOKIE。在JS中如何操作Cookie?

[https://www.jianshu.com/p/f348a388411d](https://www.jianshu.com/p/f348a388411d)





