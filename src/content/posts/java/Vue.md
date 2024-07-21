---
title: Vue
published: 2024-07-21
description: 'Vue入门'
image: ''
tags: [vue, java]
category: 'java'
draft: false 
---
# Vue

### Vue快速入门
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="js/vue.js"></script>
</head>
<body>
    <div id="app">
        <input type="text" v-model="message">
        {{message}}
    </div>
    
</body>
<script>
    new Vue({
        el: "#app",
        data: {
            message: "Hello Vue"
        },
    })
</script>
</html>
```

### V-bind & V-model
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="js/vue.js"></script>
</head>
<body>
<div id="app">
    <a v-bind:href="url">链接1</a>
    <a :href="url">链接2</a>
    <input type="text" v-model = "url"></div>
</body>
<script>
    new Vue({
        el: "#app",
        data: {
            url: "https://www.baidu.com"
        },
    })
</script>
</html>
```

### V-model
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="js/vue.js"></script>
</head>
<body>
<div id="app">
    <input type="button" value="点我一下" v-on:click="handle()">
    <input type="button" value="点我一下" @click="handle()">
</div>
</body>
<script>
    new Vue({
        el: "#app",
        data: {

        },
        methods: {
            handle:function(){
                alert("你点我了一下.......");
            }
        },
    })
</script>
</html>
```