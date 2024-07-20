---
title: JavaScript
published: 2024-07-20
description: 'JavaScript复习'
image: ''
tags: [JavaScript,java]
category: 'java'
draft: false 
---
## JS基础语法
----------------------------
### 输出语句
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
<script>
    window.alert("Hello JavaScript!");
    document.write("Hello JavaScript!");
    console.log("Hello JavaScript!");
</script>
</html>
```
### 变量
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
<script>
    var a = 10;
    var a = "张三";
/*     let b = 1;
    let b = "张";
    报错 */
    alert(a);
    const pi = 3.14;
    // pi = 3.15;
    alert(pi);
</script>
</html>
```
### 数据类型
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
<script>
/*     alert(typeof 3);
    alert(typeof 3.14);
    
    alert(typeof "A");
    alert(typeof 'Hello');
    
    alert(typeof true);
    alert(typeof false);
    
    alert(typeof null);//object
    
    var a;
    alert(typeof a);//undefined */
    alert(parseInt("12"));
    alert(parseInt("12A45"));
    alert(parseInt("A45"));
</script>
</html>
```
## JS函数
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
<script>
    //var add = function(a, b){}
    function add(a, b){
        return a + b;
    }
    var result = add(10, 20);
    alert(result);     
</script>
</html>
```
## JS对象
----------------------------
### array
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
<script>
    // var arr = new Array(1,2,3,4);
    // console.log(arr[1]);
    // console.log(arr[2]);
    // var arr=[1,2,3,4];
    // arr[10] = 50;

    // console.log(arr[10]);
    // console.log(arr[9]);
    // console.log(arr[8]); 

    // arr[9] = true;
    // arr[8] = 'A';

    // console.log(arr);

    var arr=[1,2,3,4];

    // arr.forEach(element => {
    //     console.log(arr[element-1])
    // });
    // for(let i = 0; i <arr.length; i ++){
    //     console.log(arr[i])
    // }

    arr.push(7,8,9)
    // console.log(arr);

    arr.splice(2,1);
    console.log(arr);
</script>
</html>
```
### String
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
<script>
    // var str = new String("Hello String");
    var str = "Hello String";

    console.log(str);
    console.log(str.length);
    console.log(str.charAt(4));
    console.log(str.indexOf("lo"));
    var s = str.trim();
    console.log(s);
    console.log(str.substring(1,7));//左闭右开
</script>
</html>
```
### JSON
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
<script>
    /* var user = {
        name: "Tom",
        age: 10,
        gender: "male",
        // eat: function(){
        //     alert("用膳~");
        // }
        eat(){
            alert("用膳~");
        }
    }
    alert(user.name);
    user.eat(); */

    //定义JSON
    var jsonstr = '{"name": "Tom", "age":18, "addr": ["北京", "上海", "西安"]}';
    // alert(jsonstr.name);
    var obj = JSON.parse(jsonstr);
    // alert(obj.name);
    alert(JSON.stringify(obj));
</script>
</html>
```
### BOM
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
<script>
    // var flag = confirm("确认删除？");
    // alert(flag);
    //定时执行，每隔两秒一次 
    /*var count = 0;
    setInterval(() => {
        count ++;
        console.log("函数执行了"+count+"次");
    }, 2000); */
    //延迟执行，仅一次
    /* setTimeout(function(){
        alert("JS");
    },3000); */
    alert(location.href);
    location.href = "https://baidu.com";
</script>
</html>
```
### DOM演示
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JS-对象-DOM演示</title>
</head>

<body>
    <div style="font-size: 30px; text-align: center;" id="tb1">课程表</div>
    <table width="800px" border="1" cellspacing="0" align="center">
        <tr>
            <th>学号</th>
            <th>姓名</th>
            <th>分数</th>
            <th>评语</th>
        </tr>
        <tr align="center" class="data">
            <td>001</td>
            <td>张三</td>
            <td>90</td>
            <td>很优秀</td>
        </tr>
        <tr align="center" class="data">
            <td>002</td>
            <td>李四</td>
            <td>92</td>
            <td>优秀</td>
        </tr>
        <tr align="center" class="data">
            <td>003</td>
            <td>王五</td>
            <td>83</td>
            <td>很努力,不错</td>
        </tr>
        <tr align="center" class="data">
            <td>004</td>
            <td>赵六</td>
            <td>98</td>
            <td>666</td>
        </tr>
    </table>
    <br>
    <div style="text-align: center;">
        <input id="b1" type="button" value="改变标题内容" onclick="fn1()">
        <input id="b2" type="button" value="改变标题颜色" onclick="fn2()">
        <input id="b3" type="button" value="删除最后一个" onclick="fn3()">
    </div>
</body>

<script>
    function fn1(){
        document.getElementById('tb1').innerHTML="学员成绩表";
    }
    
    function fn2(){
        document.getElementById('tb1').style="font-size: 30px; text-align: center; color: red;"
    }

    function fn3(){
       var trs = document.getElementsByClassName('data');
       trs[trs.length-1].remove();
    }
</script>

</html>
```
### DOM获取元素
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JS-对象-DOM</title>
</head>

<body>
    <img id="h1" src="img/off.gif">  <br><br>

    <div class="cls">传智教育</div>   <br>
    <div class="cls">黑马程序员</div>  <br>

    <label><input type="checkbox" name="hobby"> 电影</label>
    <label><input type="checkbox" name="hobby"> 旅游</label>
    <label><input type="checkbox" name="hobby"> 游戏</label>
</body>

<script>
    // var img = document.getElementById('h1');
    // alert(img);
    // var divs = document.getElementsByTagName('div');
    // for (let i = 0; i < divs.length; i++) {
    //     alert(divs[i]);
    // }
    // var n = document.getElementsByName('hobby');
    // for (let i = 0; i < n.length; i++) {
    //     alert(n[i]);
    // }
    // var c = document.getElementsByClassName('cls');
    // for (let i = 0; i < c.length; i++) {
    //      alert(c[i]);
    //  }
    var c = document.getElementsByClassName('cls');
    var c1 = c[0];
    c1.innerHTML = "传智教育666";
</script>
</html>
```
### DOM案例
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JS-对象-DOM-案例</title>
</head>

<body>
    <img id="h1" src="img/off.gif">  <br><br>

    <div class="cls">传智教育</div>   <br>
    <div class="cls">黑马程序员</div>  <br>

    <label><input type="checkbox" name="hobby"> 电影</label>
    <label><input type="checkbox" name="hobby"> 旅游</label>
    <label><input type="checkbox" name="hobby"> 游戏</label>
</body>

<script>
    //1. 点亮灯泡 
    var img = document.getElementById('h1');
    img.src =  "./img/on.gif";
    //2. 将所有div标签的内容后面加上 very good(红色字体)
    var divs = document.getElementsByTagName('div');
    for (let index = 0; index < divs.length; index++) {
        const element = divs[index];
        element.innerHTML += "<font color='red'>very good</font>"
    }
    //3. 使所有的复选框呈现选中状态
    var divs = document.getElementsByName('hobby');
    for (let index = 0; index < divs.length; index++) {
        const element = divs[index];
        element.checked = true;
    }
</script>
</html>
```
## JS事件
--------------------------------------
### 事件绑定
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JS-事件-事件绑定</title>
</head>

<body>
    <input type="button" id="btn1" value="事件绑定1" onclick="on()">
    <input type="button" id="btn2" value="事件绑定2">
</body>

<script>
    function on(){
        alert("按钮一被点击了......");
    }
    document.getElementById('btn2').onclick=function(){
        alert("按钮二被点击了......");
    };
</script>
</html>
```
### 常见事件
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JS-事件-常见事件</title>
</head>

<body onload="load()">

    <form action="" style="text-align: center;" onsubmit="subfn()">
        <input type="text" name="username" onblur="bfn()" onfocus="ffn()" onkeydown="kfn()">
        
        <input id="b1" type="submit" value="提交">

        <input id="b1" type="button" value="单击事件" onclick="fn1()">
    </form>  

    <br><br><br>

    <table width="800px" border="1" cellspacing="0" align="center" onmouseover="over()" onmouseout="out()">
        <tr>
            <th>学号</th>
            <th>姓名</th>
            <th>分数</th>
            <th>评语</th>
        </tr>
        <tr align="center">
            <td>001</td>
            <td>张三</td>
            <td>90</td>
            <td>很优秀</td>
        </tr>
        <tr align="center">
            <td>002</td>
            <td>李四</td>
            <td>92</td>
            <td>优秀</td>
        </tr>
    </table>

</body>

<script>
    //onload : 页面/元素加载完成后触发
    function load(){
        console.log("页面加载完成...")
    }

    //onclick: 鼠标点击事件
    function fn1(){
        console.log("我被点击了...");
    }

    //onblur: 失去焦点事件
    function bfn(){
        console.log("失去焦点...");
    }

    //onfocus: 元素获得焦点
    function ffn(){
        console.log("获得焦点...");
    }

    //onkeydown: 某个键盘的键被按下
    function kfn(){
        console.log("键盘被按下了...");
    }

    //onmouseover: 鼠标移动到元素之上
    function over(){
        console.log("鼠标移入了...")
    }

    //onmouseout: 鼠标移出某元素
    function out(){
        console.log("鼠标移出了...")
    }

    //onsubmit: 提交表单事件
    function subfn(){
        alert("表单被提交了...");
    }

</script>
</html>
```
### 案例
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>JS-事件-案例</title>
</head>
<body>

    <img id="light" src="./JS/img/off.gif"> <br>

    <input type="button" value="点亮"  onclick="on()"> 
    <input type="button"  value="熄灭" onclick="off()">

    <br> <br>

    <input type="text" id="name" value="ITCAST" onfocus="lower()" onblur="upper()">
    <br> <br>

    <input type="checkbox" name="hobby"> 电影
    <input type="checkbox" name="hobby"> 旅游
    <input type="checkbox" name="hobby"> 游戏
    <br>

    <input type="button" value="全选" onclick="checkAll()"> 
    <input type="button" value="反选" onclick="checkNone()">

</body>

<script>

    //1. 点击 "点亮" 按钮, 点亮灯泡; 点击 "熄灭" 按钮, 熄灭灯泡; 
    function on(){
    document.getElementById('light').src = "./JS/img/on.gif"
    }
    function off(){
    document.getElementById('light').src = "./JS/img/off.gif"
    }

    //2. 输入框聚焦后, 展示小写; 输入框离焦后, 展示大写; 
    function lower(){
        var input = document.getElementById('name');
        input.value = input.value.toLowerCase();
    }
    function upper(){
        var input = document.getElementById('name');
        input.value = input.value.toUpperCase();
    }



    //3. 点击 "全选" 按钮使所有的复选框呈现选中状态 ; 点击 "反选" 按钮使所有的复选框呈现取消勾选的状态 ; -- onclick
    function checkAll(){
        var hobbys = document.getElementsByName('hobby');
        for (let index = 0; index < hobbys.length; index++) {
            const element = hobbys[index];
            element.checked = true;
        }
    }
    function checkNone(){
        var hobbys = document.getElementsByName('hobby');
        for (let index = 0; index < hobbys.length; index++) {
            const element = hobbys[index];
            element.checked = false;
        }
    }


</script>
</html>
```