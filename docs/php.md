# PHP学习笔记
BY BUDUAN  
QQ：2393982461  
![php](imgs\PHP学习笔记海报.png)
## 了解与安装

### 关于PHP语言
PHP是一款比较热门的编程语言，常用于服务端开发，目前世界使用率排名大概在第9名。像百度、B站这种热门网站的服务端开发都有PHP的参与。

### 安装WAMP开发环境（For Windows）
WAMP（Windowa， Apache ，Mysql and PHP）是目前最常用的PHP开发环境，也是最推荐安装在Windows系统中的开发环境。

#### 官网获取安装包
访问[WampServer官网（wampserver.com）](http://www.wampserver.com/)，找到自己电脑对应位数(bit)的版本，下载即可。
#### 进行安装
打开安装程序，按照我们安装常规软件的方式安装即可。
#### 设置网站目录
设置的安装目录，即我们的网站目录，根据自己的需求选择即可，后续可以更改。
#### 访问localhost
安装好后，浏览器访问localhost或127.0.0.1，若出现Wamp的面板，即为安装成功。
#### 查看php_info( )
安装成功后，我们在www目录下新建一个phpinfo.php文件，文件中输入``php_info()``，保存后，浏览器打开loaclhost/phpinfo.php；或在localhost页面中，底部tools一栏中找到php_info()，点击打开页面。若出现图中页面，即PHP安装成功，第一行PHP Version后面的数字，就是PHP版本。
![phpinfo页面](imgs\459c25cd62f1f3bb3cdc75e3e89bf5d.png)

### 安装MAMP开发环境（For Mac）
在Mac电脑上面，安装一个名为MAMP PRO的应用。  
关于MAMP的使用请参考[MAMP使用方法](http://php.docs.461blog.cn/#/mamp)

### 安装编辑器
说到编辑器这里，由于PHP的执行方式，只要你电脑里面装了开发环境，就可以运行，PHP文件即使没有编辑器，仅有一个记事本也可以编辑，只不过有了编辑器，可以使我们的开发更加顺畅。

#### 安装VS Code
VS Code是微软开发的一款代码编辑工具，这款工具是完全免费的，并且支持中文，并且支持多平台，在Windows、OS X、Linux系统中均可用，非常适合初学者。  
安装地址：[https://code.visualstudio.com/](https://code.visualstudio.com/)

#### 安装PHP Storm（付费，学生用户免费）
后续教程中我大部分都会用这个软件来编辑。  
PHPStorm是有Jetbrain开发的一款针对PHP开发者的一个开发集成工具(IDE)，支持多平台，最新版支持中文，用起来要比VS Code舒服一些，除了这款工具以外，Jetbrain还有针对其他语言的开发工具，如：Webstorm、Pycharm等。  
PHP Storm对学生用户或大型开源项目作者的拥有者免费授权，对普通用户采用付费授权。
PHPstorm安装地址：[https://www.jetbrains.com/phpstorm/](https://www.jetbrains.com/phpstorm/)

### PHP手册
学习一门编程语言，不论多么厉害的教程，最重要的还是官方文档，后续开发最重要的也是官方文档，开发文档可以提供给我们所需要的函数、语法及定义，也可以清楚地看到语言每一次迭代更新的变化，以及所支持函数点变化。
PHP官方开发文档（PHP手册），请前往PHP官网获取：[www.php.net](www.php.net)，PHP的文档是具有中文版本的，但仅一部分内容带有中文翻译，大部分仍为英文。
## 基础
### PHP是什么
PHP(PHP: Hypertext Preprocessor，超文本预处理器的缩写)，是一种被广泛应用的开放源代码的、基于服务器端的用于产生动态网页的、可嵌入HTML中的脚本程序语言，尤其适合 WEB 开发。  
当客户端向服务器的程序提出请求时，web服务器根据请求响应对应的页面，当页面中含有php脚本时，服务器会交给PHP解释器进行解释执行，将生成的html代码再回传给客户端，客户端的浏览器解释html代码，最终形成网页格式的页面。（此段文字来自网络，不用背下来，了解即可）
### 执行方式
PHP的代码常包含在特定起始符``<?php``和结束符``?>``中，使得网页的脚本可进出为"PHP 模式".
与其他语言对比，其他如C等语言写的脚本，需大量命令来编写程序，以输出HTML，而用PHP来编写一个HTML脚本，只需要嵌入一些代码来完成相关操作  
与JavaScript区分，JavaScript的代码是运行在前端，也就是客户端，而PHP的代码是运行在服务端，也就是我们服务器上面的，客户是完全看不到代码是如何运作的。

### PHP的特点
简单，易懂。上手难度不高，但是要是深入学习也比较难。  
开源（开放源代码，即将源码向大众公开，简称为**开源**。科普一下，全球最大的~~男性交友社区~~开源社区：Github）的一种服务端脚本语言。  
不受操作系统的限制，在Windows、Linux中都可用  
不受服务器的限制Apache、IIS等都可用  
流行度高，使用率高，很多大厂网站也都在用，是目前最常用的服务端开发语言。  
PHP是世界上最好的语言（手动滑稽）

### C/S结构和B/S结构
我们常说的C/S结构，即Client-Server，指的是客户端-服务端结构，随着互联网的发展，逐渐出现了B/S，即Brower-Server，指的是浏览器-服务端结构，下面就来了解一下两个结构。
#### C/S结构
C/S结构（Client-Server），是客户端-服务端结构，即通过客户通过客户端与服务器进行交互。客户端主要完成与客户的交互任务，服务端主要是对数据的处理。
#### B/S结构
B/S结构（Brower-Server），是浏览器-服务端结构，随着互联网发展而慢慢出现的一种交互结构，是对C/S改进的一种结构。客户无需通过单独的客户端，而是通过浏览器与服务器进行交互，浏览器代替C/S结构中的客户端完成与客户的交互任务。用户工作页面通过浏览器实现，少部分逻辑通过前端实现，大部分逻辑通过服务端来实现，减少用户电脑的负载，降低了用户的成本。
### 标记格式和执行符(分号)
PHP的标记风格为``<?php ... ?>``,这是推荐使用的标记风格，管理员无法对这种风格进行禁用。  
在一些程序中还会出现``<? ... ?>``这种简短的风格，该风格在多数环境中，默认是不支持的，需要在php.ini中启用``short_open_tage``选项。
如果文件内容是纯 PHP 代码，最好在文件末尾删除 PHP 结束标记。这可以避免在 PHP 结束标记之后万一意外加入了空格或者换行符，会导致 PHP 开始输出这些空白，而脚本中此时并无输出的意图。
PHP中常用``;``来分隔简单的语句，即分号为PHP的执行符，我们需要输入``;``来执行我们所输入的PHP语句
### 注释
在PHP中常用两种分隔的注释，为单行注释和多行注释。提示：代码千万行，注释第一行。写程序时候一定要及时加注释！
单行注释，如：
```
//单行注释内容
```
多行注释。如：
```
/*
 *多行注释内容
 *嘿嘿！
*/
```
### 查看数据
在一个语言中，输出数据是最简单，但也是最重要的。这里以PHP最常见的两种输出数据的方式为例。
#### echo
在PHP中我们常用echo语句来输出数据，如：变量、字符串、数值等，如：
```php
//输出字符串（string）
echo "Hello wordld!";
//输出数值（int）
echo 3;
//输出变量，关于变量后面会提到
$a = "hello";
echo $a;
```
输出内容：
```
Hello world!
3
hello
```
echo不是函数，所以他不需要使用``()``，输出多个数据，请用``,``或``.``分隔
#### var_dump()
var_dump是一个函数，所以我们需要在``()``中如我们想要输出的变量，不同于``echo``的是，``echo``是直接输出数据，而var_dump是输出数据及数据类型。
```php
var_dump(1);
```
## 数据类型
在程序中，我们用不同的类型，去储存不同的数据。在PHP中，我们常用的数据类型有整型(int)、浮点型(float)、布尔型(bool)、字符串(string)等，下面就来对这些数据类型进行说明。
### 整型
整型值可以使用十进制，十六进制，八进制或二进制表示，前面可以加上可选的符号（- 或者 +）,如：
```
$a = 1234; // 十进制数
$a = -123; // 负数
$a = 0123; // 八进制数 (等于十进制 83)
$a = 0x1A; // 十六进制数 (等于十进制 26)
$a = 0b11111111; // 二进制数字 (等于十进制 255)
```
要使用八进制表达，数字前必须加上 0（零）。要使用十六进制表达，数字前必须加上 0x。要使用二进制表达，数字前必须加上 0b。
int型的数值一定是整数，若带有小数点，或进行运算后的数字为非整数字，数据就会被定义为浮点型。
如果给定的一个数超出了整型的范围，将会被定义为浮点型。同样如果执行的运算结果超出了整型范围，也会返回浮点型。
### 浮点型
浮点型可以看做是数学中的实数，可以是有限小数，也可以是无限小数，如：``0.66``、``2.333``、``1.0``等
### 布尔型
布尔型，为``true``和``false``。   
其他数据类型转化为布尔型，通常为``false``的：  
- 数值为0的整数型和浮点型(0.0)
- 数据为空的字符串
- 数据为"0"的字符串
- 无成员变量的数组
- NULL空值  

### 字符串
字符串，即文本形式的数据，常包含在``' '``/``" "``中，但要区别的是，双引号中可以引入变量，如：
```php
$a = "buduan";
echo "Hello $a";
```
这样，输出的内容就是：
```
Hello buduan
```
#### 定界符
定界符在字符串中，能起到双引号的作用，常常用于具有大量文本的字符串，如：
```php
$a=<<<str
在这里输入大量的内容...
str;
```
注意：定界符前后不能有任何“其他的东西”，**空格也不可以**，在定界符后面只能加分号。
#### 连接符
字符串的输出常用``.``进行连接，如：
```php
$a = "Hello";
$b = "Buduan";
echo $a . $b;
```
则输出的内容为：
```
Hello Buduan
```
#### 转义
转义，是对同样一个字符，具有多种含义的转换，如在被``" "``包含的字符串中的的``"``就需要用到转义来输出；再比如$美元符号，他既可以表示成一个符号，也可以被解析成一个定义变量的符号，这个时候也需要转义。
转义方法，在具有特殊意义的标点前，加一个**反斜线**``\``，如：需要在单引号中输出一个单引号，就需要在单引号前加一个``\``如：
```php
$a = '我是123\'4\'';
```
若要输出反斜线，即需要用到``\\``来表示。  
在双引号包含的内容中，PHP也可以对一些特殊的字符进行转义。
转义符对照表(来自PHP手册)：  

| 序列 | 含义 |  
| - | ------ |  
| \n  |换行（ASCII 字符集中的 LF 或 0x0A (10)）|  
| \r  |回车（ASCII 字符集中的 CR 或 0x0D (13)）|  
| \t  |水平制表符（ASCII 字符集中的 HT 或 0x09 (9)）|  
| \v  |垂直制表符（ASCII 字符集中的 VT 或 0x0B (11)）（自 PHP 5.2.5 起）|  
| \e  |Escape（ASCII 字符集中的 ESC 或 0x1B (27)）（自 PHP 5.4.0 起）|  
| \f  |换页（ASCII 字符集中的 FF 或 0x0C (12)）（自 PHP 5.2.5 起）|  
| \\  |反斜线 |  
| \$  |美元标记 |  
| \"  |双引号 |  
| \[0-7]{1,3} | 符合该正则表达式序列的是一个以八进制方式来表达的字符 |  
| \x[0-9A-Fa-f]{1,2}  |符合该正则表达式序列的是一个以十六进制方式来表达的字符 |  

#### 输出中文
为了避免乱码，我们可以通过在PHP的开头中插入这样一行代码，来避免有格式错误导致的乱码：``header(content-type:text/html;charset:utf-8)``
这行代码的作用是，设置文本格式为UTF-8
#### 和字符串相关的函数
此处内容，详细请参考[PHP手册：字符串处理](https://www.php.net/manual/zh/book.strings.php)，此处仅对几个常用的函数进行说明。
**strlen()**  
**mb_strlen()**  
**trim()**  
**rtrim()**、**ltrim**  
...  
### 空值 NULL
空值，从字面上理解，就是没有任何值的一个量。  
一般什么情况会被定义为空值(NULL)  
1.被定义为NULL的量
2.为空的量
3.被unset()注销掉的量
空值(NULL)可转化为布尔型的false，整型和浮点型的0。
### 相关函数

### 类型转换

## 常量和变量
### 变量
#### 什么是变量
#### 定义一个变量
#### 弱类型
#### 赋值和使用
#### 变量作用域
### 常量
#### 声明常量
#### 检测常量
#### 系统常量
## 数组 array
## 运算符
## 流程控制
## 函数 function
## 数据库 Mysqli
## 文件操作 files
## 会话处理 cookie和session
## 数据库PDO
对于PHP中通过PDO函数对数据库进行操作，我还在学习中，等我学习差不多会把我自己的学习过程和学习思路整理上来
## 面向对象
对于PHP中通过面向对象，我还在学习中，等我学习差不多会把我自己的学习过程和学习思路整理上来
