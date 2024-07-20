---
title: JavaScript
published: 2024-07-20
description: 'JavaScript复习'
image: ''
tags: [JavaScript,java]
category: 'java'
draft: false 
---
```JS-语法基础-输出语句
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
```JS-基础语法-变量
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
```JS-基础语法-数据类型
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