##使用方式： 
* 1、引用 js：`jquery.uiAlertView-1.0.0.js，css:uiAlertView-1.0.0.css`

* 2、弹出提示信息
```javascript
  $.alertView("弹出提示信息");
```
* 3、自定义标题、按钮
```javascript
  var json = {
    title:"标题",
    msg:"自定义标题、按钮",
    buttons:[
        { title:"Delete",color:"red",click:function(){alert("你点了Delete")} },
        { title:"Cancel",click:function(){alert("你点了Cancel")} }
    ]
}
 
$.alertView(json);
```
* 4、设置多个按钮
```javascript
  var json = {
    title:"提示",
    msg:"定义多个按钮，定义多个按钮，定义多个按钮，定义多个按钮",
    buttons:[
        { title:"first",click:function(){alert("你点了first")} },
        { title:"second",click:function(){alert("你点了second")} },
        { title:"delete",color:"red" }
    ]
}
 
$.alertView(json);
```
* 5、带文本框的弹窗
```javascript
  var json = {
    title:"标题",
    msg:"请输入姓名",
    input:{ type:"text", value:"张三" },
    buttons:[
        { title:"OK",click:function(text){alert("您输入的是:" + text)} },
        { title:"Cancel" }
    ]
}
 
$.alertView(json);
```
* 6、密码输入框
```javascript
  var json = {
    title:"标题",
    msg:"请输入密码",
    input:{ type:"password", placeholder:"请输入密码" },
    buttons:[
        { title:"OK",click:function(text){alert("您输入的是:" + text)} },
        { title:"Cancel" }
    ]
}
 
$.alertView(json);
```
* 7、手动关闭弹窗
```javascript
  var json = {
    title:"标题",
    msg:"密码输入123,手动关闭弹窗",
    input:{ type:"password", placeholder:"请输入密码" },
    buttons:[
        // 设置 autoClose:false 会禁止自动关闭弹窗
        { title:"OK", autoClose:false, click:
            function(text,element){
                if (text == "123") {
                    // 使用 $.closeView() 关闭弹窗
                    $.closeView();
                }
                else {
                    element.find("input").css("border","red solid 1px");
                }
            } 
        },
        { title:"Cancel" }
    ]
}
 
$.alertView(json);
```
##参数说明：
* showMask：是否开启遮罩，默认值 true

* title：弹窗标题

* msg：弹窗消息

* input：输入框，json 对象

* input 输入框参数：

* type：输入框类型，可为"text","password"

* value：输入框默认值

* placeholder：属性提供可描述输入字段预期值的提示信息

* buttons：按钮设定，json 数组

##按钮参数设定：
* title：按钮显示名称

* color：按钮颜色，默认蓝色

* click：回调函数，如 click:function(a,b){}，a是输入框的值，b是弹出窗的Div
