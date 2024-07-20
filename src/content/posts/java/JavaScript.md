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
----------------------
###　array
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