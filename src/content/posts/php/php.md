---
title: php
published: 2024-07-10
description: '一篇关于php的基础入门教程'
image: './php1.jpg'
tags: []
category: ''
draft: false 
---

# 关于php

- PHP 是 "PHP Hypertext Preprocessor" 的首字母缩略词

- **PHP 是一种创建动态交互性站点的强有力的服务器端脚本语言。**
- **PHP 是开源免费的，并且使用广泛** , 可供免费下载和使用，可商用
- **PHP 脚本在服务器上执行**
- **PHP 是解释型语言，按顺序从上往下执行，无需编译，直接运行**

- 它强大到足以成为在网络上最大的博客系统的核心（WordPress）！
- 它深邃到足以运行最大的社交网络（facebook）！
- 而它的易用程度足以成为初学者的首选服务器端语言！

### 什么是 PHP 文件？

- PHP 文件能够包含文本、HTML、CSS 以及 PHP 代码
- PHP 文件的后缀是 ".php"
- PHP 代码在服务器上执行，而结果以纯文本返回浏览器


### PHP 能够做什么？

- PHP 能够生成动态页面内容 （Html页面渲染）
- PHP 能够创建、打开、读取、写入、删除以及关闭服务器上的文件 （文件操作）
- PHP 能够接收表单数据 （例如注册登录）
- PHP 能够发送并取回 cookies （记录用户状态等信息）
- PHP 能够添加、删除、修改数据库中的数据 （数据操作）
- PHP 能够限制用户访问网站中的某些页面 （权限管理）
- PHP 能够对数据进行加密和压缩
- PHP 通常用于小程序 app 浏览器插件等的后端服务接口

通过 PHP，您可以不受限于只输出 HTML。您还能够输出图像、PDF 文件、甚至 Flash 影片。您也可以输出任何文本，比如 XHTML 和 XML。

### 为什么使用 PHP？

- PHP 是跨平台的，可运行于各种平台（Windows, Linux, Unix, Mac OS X 等等）
- PHP 兼容几乎所有服务器（Apache，Nginx, IIS 等等）
- PHP 支持多种数据库 (Mysql)
- PHP 是免费的。请从官方 PHP 资源下载：[www.php.net](http://www.php.net/)
- PHP 易于学习，并可高效地运行在服务器端

## 最好应具备的基础知识

在继续学习之前，您需要对下面的知识有基本的了解：

- HTML
- CSS
- JavaScript（入门级这个无所谓）


# 环境安装和编辑器推荐


编辑器根据自己喜好即可，我推荐vscode /notepad-- /notepad next /phpstorm
环境我推荐使用phpstudy（小皮）
演示创建一个站点

注意：把电脑文件扩展名显示出来

![[Pasted image 20230920100234.png]]

# php语法

### 基础 PHP 语法

PHP 脚本以 `<?php` 开头，以 `?>` 结尾：

```php
<?php // 此处是 PHP 代码 ?>

<?php
// 此处是 PHP 代码
?>
```


PHP 脚本可放置于文档中的**任何**位置，文件扩展名是 ".php"。
PHP 文件通常包含 HTML 标签以及一些 PHP 脚本代码，注意： html js css可以写在php文件里运行，但php不能写在html js css文件里运行。

PHP 语句以分号结尾（;）

```html
<!DOCTYPE html>
<html>
<body>

<h1>我的第一张 PHP 页面</h1>

<?php
echo "Hello maoshu!";
?>

</body>
</html>
```

### **输出方法：echo 和 print**

不同点：
- echo - 能够输出一个以上的字符串，英文逗号隔开
- print - 只能输出一个字符串，并**始终返回 1**
- echo 比 print 稍快，并且开销低

```php
<?php
echo "<h2>猫叔123!</h2>";
echo "Hello world!<br>";
echo "Maoshu", " string", 1, " 2 ";
?>
```

相同点：

- 都是一个语言结构，有无括号均可使用：echo 或 echo()  print 或 print()

### 注释

注释不会被作为程序来读取和执行。它唯一的作用是供代码编辑者阅读（让别人阅读明白，提醒自己做过什么，特别是一些函数方法的用途等）

```php
<?php
// 这是单行注释

# 这也是单行注释

/*
这是多行注释块
它横跨了
多行
随意换行没问题
echo '猫叔';
*/
?>
```

### 变量

变量是存储信息的容器，有点类似初中数学里的代数 `x=1,y=2`

```php
$a=5;
$_a = 5;
$b=6;
$c=$a+$b;
echo $c;
```

=号并不是真实的等号，而是叫赋值

#### 变量命名规则

- 变量以 $ 符号开头，其后是变量的名称
- 变量名称必须以字母或下划线开头
- 变量名称不能以数字开头，不能有空格
- 变量名称只能包含字母 数字 字符和 下划线（A-z、0-9 以及 _）
- 变量名称对大小写敏感（$y 与 $Y 是两个不同的变量）

注释：PHP 变量名称对大小写敏感！

推荐的几种命名方法：

- 下划线命名法 `$first_name = 'zhang';`
- 小驼峰命名法 `$firstName = 'zhang';`
- 大驼峰命名法 `$FirstName = 'zhang';`
- 


```php
$txt="Hello world!";
$a=5;
$b=8.5;
```

不必告知 PHP 变量的数据类型，php会根据它的值，自动把变量转换为正确的数据类型

变量也有**作用域**之分，等到后面函数的时候再说。

#### 空白符

```php

echo '猫叔

你在干什么

？

';

/**

我在

看抖音小姐姐


*/
```


### 大小写敏感
所有用户定义的函数、类和关键词（例如 if、else、echo 等等）都对大小写**不敏感**，
但是所有变量都对大小写**敏感**

```php
ECHO "Hello 猫叔!<br>";
echo "Hello 猫叔!<br>";

EcHo "Hello 猫叔!<br>";
PRint "Hello 猫叔!<br>";
```

```php
$color="red";
echo "My car is " . $color . "<br>";
echo "My house is " . $COLOR . "<br>";
```

## 命令行的使用

可以像python一样在命令行里运行php
用cmd或者vscode插件

可以获取用户输入的内容

```php
$input = readline("请输入内容："); 
echo "您输入的内容是： " . $input;
```

```php
echo "请输入内容："; 
$input = fgets(STDIN); 
echo "您输入的内容是： " . $input;
```


## 数据类型
**字符串、整数、浮点数、逻辑（布尔型）、数组、对象、NULL、资源类型**
用var_dump() 会返回变量的数据类型和值，一般用于开发调试时使用

只获取数据类型 `echo gettype($a);`

### 字符串
字符串是字符序列，比如 "Hello world!"。

字符串可以是引号内的任何文本，可以使用单引号或双引号
注意双引号和单引号的区别

```php
$x = "Hello world!";
echo $x;
echo "<br>"; 
$x = 'Hello world!';
var_dump($x);
```

### 整数
和数学里的整数有些区别

- 整数必须有至少一个数字（0-9）
- 整数不能包含逗号或空格
- 整数不能有小数点
- 整数正负均可
- 可以用三种格式规定整数：十进制、十六进制（前缀是 0x）或八进制（前缀是 0）


```php
$x = 5985;
var_dump($x);
echo "<br>"; 
$x = -345; // 负数
var_dump($x);
echo "<br>"; 
$x = 0x8C; // 十六进制数
var_dump($x);
echo "<br>";
$x = 047; // 八进制数
var_dump($x);
```

### 浮点数

浮点数是有小数点或指数形式的数字

```php
$x = 10.365;
var_dump($x);
echo "<br>"; 
$x = 2.4e3;
var_dump($x);
echo "<br>"; 
$x = 8E-5;
var_dump($x);
```

### 逻辑（布尔值）

```php
$x=true;
$y=false;
```

### 数组
在一个变量中存储多个值
分为一维数组和多维数组，认识即可，不要深究，后面会专门讲
```php
$cars=array("Volvo","BMW","SAAB");
$_cars=["Volvo","BMW","SAAB"];
var_dump($cars);
var_dump($_cars);
```
### 对象
需要用到类和封装的知识
等学到类的时候再讲

### Null
特殊的 NULL 值表示变量无值。NULL 是数据类型 NULL 唯一可能的值
注意：可以通过设置变量值为 NULL 来清空变量数据
```php
$x="Hello world!"; 
var_dump($x);

$x=null; 
var_dump($x);

```

### resource 资源类型
等学到数据库的时候再讲

## 初级实战 - 个人博客的开头部分

实战目标：
html简单介绍
复习变量声明和输出
复习注释
了解变量重复赋值

## EOF(heredoc) 定界符使用说明

 
- 以 <<<EOF 开始标记开始，以 EOF 结束标记结束
- 结束标记必须顶头写，独自占一行，不能有缩进和空格
- 在结束标记末尾要有分号

- **EOF** 可以用任意其它字符代替，开始标记和结束标记相同即可，比如常用大写的 EOT、EOD、EOF 来表示，但是不只限于那几个(也可以用：JSON、HTML等)，只要保证开始标记和结束标记不在正文中出现即可。

- 位于开始标记和结束标记之间的变量可以被正常解析，但是函数则不可以。在 heredoc 中，变量不需要用连接符 . 或 , 来拼接

- 当内容需要内嵌引号（单引号或双引号）时，不需要加转义符，本身对单双引号转义。


```php
<?php
$name="变量会被解析";
$a=<<<EOF
$name<br>
看上面的name已经不是name啦！！！<br>
EOF;
echo $a;

echo '<hr>';

$a=<<<EOF
<a>html格式会被解析</a><br/>你看看a标签显示了没？
你看看br显示了没？
<br>
EOF;
echo $a;

echo '<hr>';

echo <<<EOF
"双引号外所有被排列好的格式都会被保留"

"但是双引号内会保留转义符的转义效果,比如table:\t和换行：\n下一行"

你看页面里有\t吗？
\n \t 和引号没关系吧？

那单'引'号呢？'\t \n 是否能看到？'
EOF;
```

## 运算符

> 注：资料来源于菜鸟教程 www.runoob.com

### 算术运算符

![[Pasted image 20230922152416.png]]

```php
<?php 
$x=10; 
$y=6;
echo ($x + $y); // 输出16
echo '<br>';  // 换行
 
echo ($x - $y); // 输出4
echo '<br>';  // 换行
 
echo ($x * $y); // 输出60
echo '<br>';  // 换行
 
echo ($x / $y); // 输出1.6666666666667
echo '<br>';  // 换行
 
echo ($x % $y); // 输出4
echo '<br>';  // 换行
 
echo -$x;

//整数之间的整除，参数也必须是整数，向下取整
var_dump(intdiv(10, 3));
?>
```

### 赋值运算符

![[Pasted image 20230922155033.png]]


```php
<?php 
$x=10; 
echo $x; // 输出10
 
$y=20; 
$y += 100;
$y = $y + 100;
echo $y; // 输出120
 
$z=50;
$z -= 25;
echo $z; // 输出25
 
$i=5;
$i *= 6;
echo $i; // 输出30
 
$j=10;
$j /= 5;
echo $j; // 输出2
 
$k=15;
$k %= 4;
echo $k; // 输出3
?>
```


### 递增/递减运算符

![[Pasted image 20230922160114.png]]

```php
<?php
$x=10; 
echo ++$x; // 输出11
 
$y=10; 
echo $y++; // 输出10
 
$z=5;
echo --$z; // 输出4
 
$i=5;
echo $i--; // 输出5
?>
```

### 比较运算符

![[Pasted image 20230922160145.png]]

```php
<?php
$x=100; 
$y="100";
 
var_dump($x == $y);
echo "<br>";
var_dump($x === $y);
echo "<br>";
var_dump($x != $y);
echo "<br>";
var_dump($x !== $y);
echo "<br>";
 
$a=50;
$b=90;
 
var_dump($a > $b);
echo "<br>";
var_dump($a < $b);
?>
```

### 逻辑运算符

![[Pasted image 20230922160442.png]]


#### and 和 && 的区别， or 和 || 的区别

主要体现在优先级： 
   -  &&  运算符的优先级比  and  运算符高。 
   - 这意味着，在一个表达式中， &&  运算符会先被执行，然后才是  and  运算符。 
   
```php
<?php 
// 在表达式中使用&&运算符
$bool = true && false; 

// 显示&&运算符的运算结果
echo "&&运算符的结果为：";
if($bool){
    echo 'true';
}
else{
    echo 'false';
}

echo '----';
// 在表达式中使用and运算符
$bool = true and false; 
// 显示and运算符的运算结果
echo "and运算符的结果为：";
if($bool){
    echo 'true';
}
else{
    echo 'false';
}
?>
```

#### 阻断效果

```php
//or-前面语句值为真，or后面不执行；否则，执行
$result = 0 or var_dump('执行我的语句');  //输出-执行我的语句
var_dump($result);  //int 0
$result = 2 or var_dump('执行我的语句');  //不输出
var_dump($result);  //int 2
```

## 条件语句 (条件分支)

#### if语句
**仅当指定条件成立时执行代码**
```php
if (条件)
{
    条件成立时要执行的代码;
}

```

#### if...else...语句
**在条件成立时执行一块代码，条件不成立时执行另一块代码**

```php
if (条件)
{  
    条件成立时执行的代码; 
}  
else  
{  
    条件不成立时执行的代码;  
}
```
![RUNOOB][php2]
![RUNOOB][php3]

[php2]: ./php2.jpg
[php3]: ./php3.png