### day01

####   1.概述

-    html: 网页的基本的结构 提供内容
-   css:     美化页面（可重用、可维护）
-    js        给页面提供功能 动态的效果

####   2.定义

##### 	1.认识

​		祖师爷(Brendan Eich)

   	![1594606285450](assets/1594606285450.png)

​        2.javascript  vs  java

 		徐克清  vs  徐克

​        3.是执行在js解释器/引擎 上的脚本语言

#####         4.执行环境:

​		1.独立的js的解释器(node.js)

​		2.直接在浏览器端执行(内核中会自制js的解释器)

##### 	5.简单发展历史

​		1.95年  网景开发  客户端语法  解决问题（最早用户提交的数据 在通过表单转到服务器验证  可能会等待非常长的时间都没反馈结果）

​                livescript  但是java很火  发布的时候临时改为javascript

​                96 微软一看很好用  立马推出了 jscript

​		程序员需要2遍代码 

 	       97年 提交给了ECMA（欧洲计算机制造商协会） 定义统一的标准	

#####          6.组成:

​		1.核心部分: ECMAScript 

​			提供了核心的语法规范，数据结构的定义， 逻辑的定义 API的定义

​		2.DOM(document object model) 文档对象模型(w3c万维网联盟 )

​			提供了一套操作页面的函数和属性的标准

​	        3.BOM(browser object model)浏览器对象模型

​			提供了一套获取浏览器的信息(高度 分辨率 宽度 鼠标的位置...)的API

​                       API :已经定义好的 接口，函数 模块等，  可以直接拿来用

##### 	  7.语法特征

​		 类似java  是一门编程语言  : 基本数据类型+算法 

​		 区别：不需要编译(翻译)  浏览器自动去执行

​		 是一门弱类型语言(非常的不严谨)   无需预编译 编译一行 立马执行一行

​		 也是一门面向对象的语言

​		 跨平台行 可以在多个操作系统中运行

### 	3.基本语法

##### 	     1.书写

​		直接在元素中书写	 

```js
	<input type="button" value="点我" onclick="alert('傻帽你好')">
```

​		2.直接在script标签中写入

```js
		<script>
   			 // 注释写法
   			 //在控制台 输出内容
   			 console.log("hello javascript")
</script>
```

​	![1594608359134](assets/1594608359134.png)

​	 3.写在外部 的js文件中  

​		通过script标签引入

```js
<!--遵循 相对路径-->
<script src="out01.js"></script>
```

​	 注意:  

​		如果是引入标签 则里面不能写任何js代码

​		同一个页面中 支持多个js文件 默认是从上到下的加载

​		注释    //单行      多行/**/

​	        一个js标签中的所以的代码 如果一旦报错了 则后面的代码就不会执行了（单线程）

#####  2.变量

​     1.定义: 在内存中开辟一个空间 用来存放一个未知的数据(比如我们之前学的xy等)

​     2.声明:

​	*通过关键字 var 声明一个变量 

​     1.先声明  后赋值

​	注意：如果声明了一个变量没有赋值 则报 undefined  不是报错

```js
//声明变量 1
    var upwd;
    console.log(upwd) //undefined 找不到
    //2 赋值
    upwd="hello 隔壁老徐"  //将隔壁老徐 赋值 给 upwd变量
    console.log(upwd); //有值了
```

​     2.声明的同时 直接同时再赋值

```js
//  情况2  直接声明赋值
    var num=123;
    console.log(num);
```

​    3.可以同时声明多个变量	

```js
// 每一个;分号代表语句的结束
    var a=30 ,b=20, c=10;
    console.log(a+b+c); // 60
```

 注意问题

```js
 //  相当于 var uname;
  //  1.如果只声明没有赋值 报undefined
   var  xu;  //undefined
   console.log("xu"); //打印变量不能加 "" 加了就是字符串
   uname="隔壁老徐"  // 如果使用的是一个未声明的变量名 则js会自动的在最开头的位置给你声明
   console.log(uname); // 隔壁老徐
    
    //  var var; 报错  变量名不能使用js已经使用了的关键字
```

  变量的声明中

​	 变量名可以由 字母数字下划线  但是不能以数字开头也不建议使用$开头

​	 变量名项目中 尽量做到见名知意 

​        可以使用驼峰式命名法 ex: userName   helloWorld	 两个单词组合后面的大写

​	 使用未声明变量 默认会Js在开头部分 帮你声明

​         变量名不能使用关键字:  ex:  var  

​    ex:常见关键字 保留字API名字 都不能用。![1594611807177](assets/1594611807177.png)

#####      3.常量

​	一般常量的值用来存放固定的 不会变化的值。

> ​	  const  pai =3.1415926    //  建议使用常量    

```js
.toFixed(n)   保留n位小数的计算方法  
ex:  console.log(l.toFixed(1));// 314.2
```

#### 4.基本数据类型			

​    1.定义: 存储不同类型的数据(在内存中占据大小空间是不一样的)

​        bit:位数   

​         byte:字节     一个字节对应的是8位位数   1byte=8bit;

​         kb   : 1024byte;   文本级别

​	 Mb : 1024kb       图片 音乐 

​         Gb:  1024mb   u盘

​          T  :1024G     硬盘

##### 2.具体的数据类型（原始类型）

###### 	1.number    数字类型

​	   作用:用于存储数据  可以表示 32位(4字节)  或者是64位(8字节)

​	              一个整数对应的4字节      小数对应的是8字节

```js
    var num=123;
    var num1=456;
    console.log(num+num1); //579;

    // 小数部分会有误差
    var x=0.1;
    var y=0.2;

    console.log(x+y);  // 0.30000000000000004  默认有误差。
    //16进制的数字
    var D16=0x20;
    console.log(D16);//32  可以进行16进制的计算
  // 判断是否是数字 方法
    var num3="xu";
    console.log(isNaN(num3)); //true  NaN   not a Number
```

isNaN(num3)   判断是不是一个数字  返回true/false 

 **console.log(Number("  ")); // js中空格也算字符串  转为0**

######  2.string类型(字符串类型)

​    用来存储 姓名 性别 地址 字符等

   默认是使用unicode编码在计算机中保存字符串 

​	unicode编码保存全世界主流字符中 进行唯一的编码是由  16进制数表示	

```js
var str="隔壁老徐";
    //判断 字符串在unicode中的编码
    console.log(str.charCodeAt()); //38548 隔这个字在unicode编码中的编码
    //  下标 3 是从0开始算的。
    console.log(str.charCodeAt(3)); //24464 徐这个字在unicode编码中的编码
    //想看一下徐 16进制 原始值  .toString()
    console.log(str.charCodeAt(3).toString(16)) // 16进制5f90

    //测试   \uxxxx   16进制数字 需要加前缀\u  xxxx对应的是4位有效16进制数字
    console.log("\u5f90");  //徐


    //特点
    var str1="10";
    var str2="24";
    // 字符串的拼接  不会去计算
    console.log(str1+str2);// 1024
    // js中  字符串相减  自动的将字符串转为number类型
    console.log(str1-str2);// -14  自动转number 计算
```

​     注意:   +  表示拼接   - 如果里面有数字 会自动的转number计算

  获取字符串的长度:

```js
	var str6="are you ok?";
    console.log(str6.length)// 11 获取字符串的长度。 算个数从1开始算。
```

###### 3.boolean 布尔类型   

​	只有2个值   

> true: 真
>
> false :假

```js
	 console.log(4>5);//false
     // bool类型的值 参与计算  默认转换为number
     // true:1   false:0
     console.log(4+true+false); //5

     var a=true;
     console.log(a);//true  
```

###### 4.undefined  没有值

​     值就是undefined   表示不存在找不到

ex: 声明一个变量 没有赋值  输出undefined

###### 5.null   空

  一般手动的设置变量为null(在内存中灰飞烟灭)

```js
  //手动设置为null 清除空间  优化内存
    var a=null;
    console.log(a); //null
```

注意: null 的 typeof值是 object的原因

```js
为什么会出现这种情况呢？因为在 JS 的最初版本中，使用的是 32 位系统，为了性能考虑使用低位存储了变量的类型信息，000 开头代表是对象，然而 null 表示为全零，所以将它错误的判断为 object 。虽然现在的内部类型判断代码已经改变了，但是对于这个 Bug
```



###### 6.symbol :es6中 详细说

#### 4.数据类型转换

##### 	1.隐式转换

​		定义: js自动的数据的转换 不是人为参与的

​		1.数字+字符串=字符串

​		        var str1=10+"10";  //1010

​		2.数字+ 布尔= 数字
​			console.log(10+true); //  11

​		3.字符串+布尔=字符串

​			console.log("10"+true) //10true

​		4.布尔+布尔=数字

​			console.log(true+true);// 2

​		小结: 减法会转换 加法会拼接在字符串中    

##### 	 2.强制转换

​		1.将其他数据强转为string类型

​		    语法: xxx.toString(n)   n数据类型	  undefined，null 无法转换

​		    语法: String(变量)     可以转所有类型  

>  typeof  num;   判断数据类型

```js
//  typeof num  判断数据类型
//  number->string
    var num=10;
    console.log(typeof num); //number
   // num=num.toString() //默认是转为10进制
    //console.log(typeof num); //string

    var num1=num.toString(16);
    console.log(num1,typeof num1); //  a=>16进制的10
    var num2=0x5f90;
    console.log(num2.toString(10)); //24464  默认就是10进制
    console.log(num2.toString()); //24464  默认就是10进制

    //bool->string  ?
        var bool=true;
    console.log(bool.toString());// true

    //undefined->string ?
        var un;
     //console.log(un.toString()); //不可以转undefined类型

    //null->string  ?
     var  a=null;
    //console.log(a.toString()); //报错 不能做换null类型*/

     // String()  可以转  undefiend 和 null  而toString()则不行
      console.log(String(num)) //转 number

      console.log(String(un));// undefined  可以

      console.log(String(a));//  null   可以
```

##### 2.强转为number类型

​	1、parseInt(str) ->转为整数

```js
//强 转 number
var str1="123";
// 转为整数 parseInt()
var num1=parseInt(str1)
console.log(num1,typeof num1);// 123 number

var str2="123abc";
var num2=parseInt(str2);
console.log(num2);//123
```

​      2、 parseFloat(str) 0>转小数

```js
//转为小数 parseFloat()
var str3="123.456.abc";
var num3=parseFloat(str3)
console.log(num3.toFixed(1)); //123.5

var str4="abc.123.456";
console.log(parseInt(str4))// NaN   not a number
```

​        3、Number(str)   转为数字类型

​              要求严格只能是纯数字的字符串

```js
// Number()  转为数字类型  要求很严格 必须是纯数字的字符串
var str2="123abc";
console.log(parseInt(str1));//123
console.log(Number(str2)); //NaN
```

#### 5.运算符和表达式

#####  1.运算符

> ​	+ - *  / 除   %取余

```js
// 除法
    var a=8,b=3;
    console.log(a/b);//2.6666...
    //  % 取余: 两数字相除取余数
    console.log(a%b); //2
```

##### 2.表达式（计算和赋值）

​	 自增++/自减--

​          num++   等于    num=num+1

​	注意:    ++num  在前:  先自增 再赋值运算

 		     num++  在后  先赋值运算 再自增

```js
	var num=10;
    // ++ 在后  先赋值   再计算(自增)
    var b=num++;
    console.log(num,b); //11   b=10

    // ++ 在前  先计算(自增)  再赋值
    var c=++num;
    console.log(c,num); // c:12  num:12

    var d=num--;
    console.log(d,num);// d:12 num:11
```

  模拟用户输入数据

```js
//模拟用户输入    默认用户输入的数据类型是 string 如果涉及到加法计算要转换
    var score= prompt("请对隔壁老徐颜值打分");
     alert("分数:"+score);
输入的值是string类型
```

```js
 //  在浏览器中打印输出    写入了一个 h1元素
     document.write("<h1>hello javascript</h1>")
     document.write("<h1>"+"您的分数是:"+sum+"</h1>");
```

### day02

=====================================================

####  1.关系运算

```
 >  <  ==  ===(全等) !=  !==  >=  <=  
 返回的是bool值
```

字符串数字和数字比会隐式转换

 字符串和字符串比 比的是unicode编码     

NaN和任何人比 都是false

```js
	console.log(5<6);
    // 字符串和数字比较  默认转为数字再比较
    console.log(5<"6");
    //字符串比较  比的是unicode编码
    var a="16",b="8" ;//从第一个值开始比
    console.log(a.charCodeAt(),b.charCodeAt());//54  56
    console.log(a<b);// true

    //挨个比 如果相同就比下一个 比的是unicode编码
    var str1="隔壁老徐"; //38548
    var str2="壁老张";    // 22721
    console.log(str1>str2)//true
   
    //  隐式转换不了数字  返回的NaN 
    var m="1a",n=1;
    console.log(m>n); // NaN和任何人比 都是false
```

  **== vs ===（全等）**

```js
//  == vs ===
var num1=1;
var num2="1";
console.log(num1==num2);  //true     比的是值
console.log(num1===num2); //false    //值和数据类型要同时相等
```

#### 转义字符

​       通过  \  实现转义

```js
	console.log("我要\n换行");// \n 就是 换行
    console.log("我要\t空格");// \t 就是 空格
    console.log("我要\"引起来\"");// \' \" 就是 引号的写法
    console.log("我要\'引起来\'");// \' \" 就是 引号的写法
```

##### 逻辑运算

​     &&（与）     ||（或）  ！（非）

  1.&& ： 必须所以的条件都满足整体表达式才为true

  2.||  :    只要有一个条件满足  整体表达式就为true

3. !    :   取反  如果表达式是true   则整体为false

   ex: 相亲:  女方的条件:     存款8位数 身高180 年龄18岁  缺一不可  

   	&& 如果第一个表达式是false 则后面的运算都不会执行
   	||  如果第一个表达式是true 则后面的运算就不会执行

```js
//   &&
    console.log(6>5&&8>9);// true+false  =false 所以条件都需要满足

     // ||
    console.log(6>5||8>9);// true+false  =true 只要满足一个

    // !取反
    console.log(!true)   //false

    var a=100,b=100;
    //     && 如果第一个表达式是false 则后面的运算都不会执行
    var c=a>b&&a++;
    console.log(a,b,c);  // 100 100 false

     //  ||  如果第一个表达式是true 则后面的运算就不会执行
     var c=++a>b||a>b++;
     console.log(a,b,c);  // 101 100 true
```

  运算符优先级

| **优先级** | **运算符**                                            | **说明**                                                | **结合性**                 |
| ---------- | ----------------------------------------------------- | ------------------------------------------------------- | -------------------------- |
| 1          | `[]`、`.`、`()`                                       | 字段访问、数组索引、函数调用和表达式分组                | 从左向右                   |
| 2          | ++ -- -~!delete new typeof void                       | 一元运算符、返回数据类型、对象创建、未定 义的值         | 从右向左                   |
| 3          | *、/、%                                               | 相乘、相除、求余数                                      | 从左向右                   |
| 4          | +、-                                                  | 相加、相减、字符串串联                                  | 从左向右                   |
| 5          | <<、>>、>>>                                           | 左位移、右位移、无符号右移                              | 从左向右                   |
| 6          | <、<=、>、>=、instanceof                              | 小于、小于或等于、大于、大于或等于、是否 为特定类的实例 | 从左向右                   |
| 7          | ==、!=、===、!==                                      | 相等、不相等、全等，不全等                              | 从左向右                   |
| 8          | &                                                     | 按位“与”                                                | 从左向右                   |
| 9          | ^                                                     | 按位“异或”                                              | 从左向右                   |
| 10         | \|                                                    | 按位“或”                                                | 从左向右                   |
| 11         | &&                                                    | 短路与（逻辑“与”）                                      | 从左向右                   |
| 12         | \|\|                                                  | 短路或（逻辑“或”）                                      | 从左向右                   |
| 13         | ?:                                                    | 条件运算符                                              | 从右向左                   |
| 14         | =、+=、-=、*=、/=、%=、&=、\|=、^=、<、<=、>、>=、>>= | 混合赋值运算符                                          | 从右向左                   |
| 15         | ,                                                     | 多个计算                                                | 按优先级计算，然后从右向左 |

```js
var num=3;
console.log(1==num%2&&(4+num*2)=="10")// true
```

#### 流程控制语句

​     1.顺序结构

​     2.分支结构

​     3.循环结构

##### 2.分支

​      ![1594707286433](assets/1594707286433.png)

1.if判断(如果)

  if(判断条件){

​     条件成立，则会执行当前代码

 }

```js
   var a=90;
    // 只有a大于90的时候 {} 里面的代码才会执行
    if(a>90){ 
        console.log("优秀");
    }
    console.log("晚上不上自习")
```

2. if-else结构   如果-否则

   ```js
     //  if-else 结构  两者只能输出一种情况
       //及格
       if(a>60){
           console.log("及格"); //输出
       }else{
           console.log("不及格");
       }
   ```

3.多重复杂嵌套

```js
a=60;
    //多重复杂嵌套  if-else-if-else
    if(a<60){
        console.log("屌丝");
    }else if(a<80&&a>=60){
        console.log("入门级渣男");
    }else if(a<=100&&a>=80){
        console.log("骨灰级渣男");
    }
```

##### 三目/三元运算

​    简化的if-else

 语法： 条件表达式**?**执行表达式1**:**执行表达式2;

  解析；   ?理解为如果 如果条件成立则执行表达式1 ":"否则执行表达式2

```js
    //简化版的 if-else
    var s=prompt("请对隔壁老张打分");
    //     条件成立  表达式1  否则  表达式2            
    document.write(s>60?"中年油腻男":"小清新");
```

 复杂的嵌套 if-else if-else{}...

 语法；  条件 ? 表达式1 : 条件2?表达式2: 条件3 ? 表达式4:表达式5;          

```js
//简化版本的 if-else-if多重嵌套
  
    document.write(s>80?"优秀":s>60?"及格":"渣男");
// 用户输入的非数字或者是大于100 或者是小于0都是输出 不合法

 document.write(isNaN(s)||s>100||s<0?"输入不合法":s>80?"优秀":s>60?"及格":"渣男")
```

##### 2.switch-case

​       基于不同的条件 执行不同代码， 根据一个变量值，这个值是固定且已知的值

​        ex： 人工客服   自动售卖机..

​      语法: 

​          switch(表达式){

​		case    值1:   执行语句1  ;    break;   终止程序 如果不加继续执行下面的代码

​	         case    值2:   执行语句2 ;   break ;

​		 .....

​                  default :  所以条件都不满足 则执行当前行 

 }

```js
//客服
    var  num=Number(prompt("请输入0123数字"));
    // 不会进行隐式转换 需要自己转
    switch (num) {
        case 0: alert("人工服务"); break;
        case 1: alert("话费查询"); break;
        case 2: alert("积分查询"); break;
        case 3: alert("流量查询"); break;
        default:alert("再见！"); break;
    }
```

### day03

####   循环

   定义:  让程序反复执行相同的一段代码模块

   特点:  

​       1.循环的条件   :让程序反复执行的条件 什么时候结束?终止?

​       			    一旦不满足条件了  则程序不再执行 终止

​       2.循环的变量 :  用来做判断  每一次循环  都要向不满足条件的趋势发展一直到条件不满足 终止

​                                 如果没有循环变量  则该循环是个死循环

​        3.  循环体:     反复执行的内容 

##### 1.while循环

​	语法:  while(满足条件){  //满足条件才会执行

​       循环体;

​        修改循环变量的值;//离不满足的条件越来越近 直到终止

}

中途退出循环  使用 **break;**

```js
 //     0-100的和
    var num=0;  //初始化循环变量
    var sum=0;  // 总和
          //循环条件 满足才执行
    while (num<101){
        sum=sum+num; //循环体  反复执行的过程

        num++;  //必须有 循环变量的变化
    }
    console.log(sum);
```

##### 2.do-while循环

   语法  :

​      do{

​         循环体;

​          修改循环变量

}while(循环条件)

**区别:**  不管条件是否为真   都会执行一遍

```js
  var  num=15;
     // 不管条件 先执行一句话
     do{
         console.log("hello")
     }while (num>100);
```

```js
//随机生成一个0-1  1取不到的小数
 console.log(Math.random());
```

##### for循环

  定义: 如果知道循环次数是固定的则可以使用for循环，它是简化版的while

  语法: 

​                    1                  2                      4

​        for(循环变量 ;  循环条件  ;   循环变量的修改){   

​               3        

​	   循环体;

 }

```js
   //0-100的和
    var sum1=0;
   //       1       2         4     
    for(var num1=0;num1<101; num1++){
        //3循环体
        sum1+=num1;
    }
    console.log(sum1);
```

一些特殊的写法

 **注意:**  if  for  while 中的{} 如果不加 不会报错  默认下一行就是循环体

```js
 //  第一个分号前可以声明多个变量
    for(var num1=0,sum1=0;num1<101;  sum1+=num1, num1++){

    }
        //3循环体
    console.log(sum1);
    /*
    * 大括号是可以省略  默认将下一行的代码当做是循环体执行
    * 第一个分号 和最后一个分号 都可以添加多个内容
    * */

    if(6<5)
    console.log("hello javascript")  //此时不会执行  当成大括号中的内容


    // 如果不加条件 是死循环
    for(;;){
        console.log("123")
    }
```

##### 断点调试

​    通过chrome浏览器进行查看 代码的执行过程

   步骤:1.  f12打开控制台 进入到sources模块 找到对应的调试文件

​		 在想要查看的地方 单击最左边 设置断点

   步骤2:   watch模块 添加想要查看的 变量   手动添加

   步骤3   刷新页面   按f10进行一步一步执行 观察到watch里面的变量的变化

![1594798815852](assets/1594798815852.png)

#####   多重循环

   画图分析

![1594800483389](assets/1594800483389.png)



特点:

```js
//外围循环打印的是 行数  里面循环打印的是当前行的个数
```

关于continue和break之间的关系

​     continue:  跳出当前一次循环

​      break:  跳出整体循环

```js
 for(var i=0;i<10;i++){
        if(i%2!=0){ // 奇数就直接跳过
            continue;  //跳过当前循环
          //  break;  // 终止
        }
        console.log(i);
    }  
```

### day04=====================================

#### 函数/方法 初始

##### 1.定义:   

​	封装一段功能  提前写好  谁想用 什么时候用 可以随时操作。

   (菜谱,葵花宝典..)

​       ex:  alert()  console.log    parseInt()    Number() ... js自带的

##### 2.语法1

​      声明: function 函数名(){方法的功能}  

​      执行:  函数名();   

##### 2.语法2

​       声明变量接收  var  变量名=function (){功能}   

​       执行:  变量名()    

​       解决函数声明提前的办法

**注意:** 得调用才执行 不调用 不执行

```js
// 封装好了一个 炖菜 菜谱 取名 dun
    function dun() {
        console.log("臭豆腐炖榴莲");
        console.log("1.切开榴莲");
        console.log("2.炸豆腐");
        console.log("3.小火慢炖3小时");
        console.log("出锅");
    }
//  得调用才执行 不调用 不执行
    //dun();

    var  cai=function () {
        console.log("臭豆腐炖榴莲");
        console.log("1.切开榴莲");
        console.log("2.炸豆腐");
        console.log("3.小火慢炖3小时");
        console.log("出锅");
    }
    // 菜谱
    console.log(cai);
    //想要吃  得执行
     cai();
```

3. ##### 带 参数的函数

     **1.定义:**function 函数名(形参,形参,...){  //未知的具体的参数  先用变量装着

   ​	具体功能

   }

    **2.执行** 函数名(实参,实参....)  //实际的参数

   注意: 

   ​     形参: 声明功能时   空的变量 用来装用户调用时传入的 实际的  数据

   ​     实参:  用户调用时 传入的数据

   ​     形参 和实参的关系      **赋值关系**     实参赋值给形参  形参进行计算

```js
 var x=Number(prompt("请输入值1"))
    var y=Number(prompt("请输入值2"))
    //2个数的和

 //  形参 :  不是固定值 但是是函数功能的一部分的
 // 封装功能的时候 我不知道调用者传入的参数是多少先拿一个盒子装着
 //  调用的时候 会把具体的值 传给add函数
    function add(a,b) {
        alert("和是"+(a+b));
        console.log(a,b); //如果没有传参 不会报错 报undefined
    }
    // 函数是可以反复的被执行
    add(12,22);
    add(55,77);
    add();//NaN

    // 将两个变量 传给函数add();
    //  形参的取名 和实参没有半毛钱关系
    add(x,y)
```

#####   3.带返回值的函数

​    1.声明:  function 函数名(){

​      函数体;

​     return   内容;    //一旦用了return 函数就结束了

}  

   返回的内容为空 则接收的变量报undefiend

   2.调用   

​      var  变量=函数名()

 注意:   1.return 之后 后面的代码不再执行

​            2.函数中的变量  外面是无法使用的

```js
  // 2个数的和
    function add(a,b) {
        var c =a+b;
         // console.log(c);
        //通过关键字return  返回函数的结果
       return c;
        //一旦 return  后面代码不再执行
         console.log(c);
    }
    //
    var result=add(12,22)
```

##### 作用域

​    定义:   变量或者是函数内   可以访问的空间范围

​    js中  

​       1.局部作用域 : 在函数中{}的访问权限   只能在函数内部使用 外面无法调用

​        2.全局作用域:   任何地方 都可以使用  修改  在script标签中 

​    特点:   函数中的变量 是 **局部变量**  外面无法使用

​	        外面的变量 **全局变量**  函数内部可以使用

```js
var a=9;
   function fn() {
        var a =5; // 局部变量
       console.log(a);//5    如果说局部作用域中值 那么就不会去全局中使用全局变量
   }
   fn();// a作为变量传入
   console.log(a); //9

/*   var a=9; //全局变量   走廊上的水
   function fn() { //207
       a=--a;  // 当前局部没有变量  则会去全局中找
       console.log(a);//8
   }
   fn();
   console.log(a); // 8*/
```

   特点:    js中 小括号中声明的变量也是全局的 外面都可以使用

​		{} 中  只有 function中的 才是局部的变量。

```js
for(var i=10;i<20;i++){
    console.log(i)
    var c=123;
}
function fn(){
    var num=12;
}
 console.log(i);//20  小括号里面的值 是全局变量
 console.log(c); // 只有在函数中的{} 包裹的才是局部变量
 console.log(num);//报错
```

> 变量名相同的情况下   如果函数内部有可用的变量 则会优先使用内部的，如果没有 会去全局找
>
> 就近原则。

##### 声明提前

  在js中  默认情况下 会进行预加载  将var声明的**变量**或者是**函数** 提前到当前的作用域的最顶部，

​               只是会把变量名提前 ，**值**会留在原地

```js
//声明提前的特点:

    console.log(a);// undefined
    var a=10;
    console.log(a);//10

    //原理是 相当于:
    var a;  //将变量名提前   提到当前文件的最上面
    console.log(a);// undefined
      a=10; //值保留在原地不动
    console.log(a);//10


    //函数 f()  其实也是一个变量  只不过变量装的是一个模块功能
    // 也会被声明提前到 最起始的位置
    f();//? 2
    function f() {
        console.log(1)
    }
    f() //2 ?
    function f() {
        console.log(2)
    }
    f()//2
```

  解决办法:

1. es5中 可以使用严格模式 "use strict"     es6之后可以使用 let 代替var

      声明一个变量 这样就不会提前

  2.针对函数  可以通过使用变量接收函数整体的形式 避免提前

​       var  变量名 =function (){}

##### 值传递问题

​     原始类型:   复制一份值给别人    原有的变量值不会改变

​     ex:  密码本 谍报人员把密码赋值给你  但是原有的本本不会变的。

​     值传递和函数参数问题:

​            函数中但凡没有声明的变量 就会去全局找 就会修改全局的值 

 	    如果找不到 就报错

```js
// 原始类型的值传递问题 :
// 复制一份值给比人 原有的变量值不会改变
var  a=5;// 5赋值给a
var b=a; //a只会把值是5复制一份先 然后将复制的值5赋值给b
 b++;    // b的操作 不会影响 a
console.log(a,b); // 5  6

var m=5;//密码本
function f(n) {
    
     console.log(m,n);//5,5
    m=n+5;  //没有接收传递过来的参数 自己直接去全局拿
    console.log(m);//10
}
f(m); //拿的是一个副本
console.log(m) //还是 10
```

#####    函数的作用域问题

```js
  // 函数也会存在作用域问题
    //  全局和局部
    // 在全局中
    function out() {
        console.log("我是公共的函数")
        //局部作用域中
        function inner() {
            console.log("我是内部函数")
        }
        inner();  //  可以被执行
    }

    out();
   //    inner();   会报错
```

##### 补充

```js
 function f(a,b) {
     console.log(b)
     console.log(a+b)
 }
 //f(1);// NaN   undefiend+1 =NaN
// f(2,3)  5
 f(1,2,3)  //  前面2个值会赋给形参  后面的忽略
```

###  day05====================================

####   数组

#####   1.定义:  

​         声明一个变量名，可以用来存储多个数据(之前的是一个变量只能存一个数据)

#####   2.声明

​      (索引数组)    有数字下标

######        1.var  数组名=[];  

​            // 表明声明了一个空数组  

```js
//1.声明
     var arr=[];  // 空数组
    //赋值
    //  注意  数组中 排位置 从下标从0开始
    arr[0]='张胜男';
    arr[1]="李思狗";
    arr[2]="王安顺";
    console.log(arr[1]);  //李思狗
    console.log(arr); //数组 ["张","李","王"]
    console.log(arr.length) ;// 数组中数据的个数 从1开始计算  3
    
    arr[4]='嘛子';  //  下标越界 不会报错
    console.log(arr);//   ["张","李","王",empty,'麻子'];
```

######      2.直接声明赋值   

```js
var  arr2=[1,3,4,56,7];
console.log(arr2[5]);// 下标越界输出 报undefined  不会报错
console.log(arr2.length);//5
```

        3. 通过new 的形式实现

```js
  var arr3=new Array(5); //声明一个长度为5的数据
    arr3[3]="隔壁老徐";
    arr3[4]="隔壁老张";
    arr3[5]="隔壁老王";  // 下标越界添加数据 则会追加
    console.log(arr3);  //  [empty × 3, "隔壁老徐", "隔壁老张", "隔壁老王"]
    //将数组转为字符串
    console.log(arr3.toString());
    console.log(String(arr3));
    console.log(arr3.length);  //哪怕前面是空的 也算长度
```

###### 4.通过new 声明赋值

```js

var arr4=new Array(12,3,4,54,65);
console.log(arr4[1]);//3
arr4[1]=33;   //修改数组中的值
console.log(arr4[1]);
```

###### 5.js同一个数组中 可以存放不同类型的数据  

```js
var  arr5=['hello',520,null,undefined,true]
console.log(arr5);//可以
```

###### 6.数组中的值的打印 使用for  方式1

```js
//打印数组中所以的元素
    for (var i=0;i<arr5.length;i++){
        console.log(arr5[i]);
    }
```

总结: 

​      1.下标永远比数组的数据的个数少1

​	 下边=>座位:可以从0开始计算

​          个数=>人数:人头 从1开始数         

​      常见写法

```js
var arr=[1,22,3,44,34];
// 数组末尾追加
arr[arr.length]="我是新来的";
console.log(arr);

// 获取数组中最后一个元素
console.log(arr[arr.length-1]); //我是新来的

//删除最后一个元素
arr.length-=2; // 同时删除2个
console.log(arr); //从右边砍掉
```

![1594956002453](assets/1594956002453.png)

##### 7.数组的值传递问题

   因为数据太大

​    结论太大 口袋放不下 直接将存到仓库=>口袋里装仓库的编号

![1594965926354](assets/1594965926354.png)

####  关联数组

  特点: 以字符串为下标，每个需要单独的添加元素，下标一般替换为了有意义的名称

   1.声明使用

```js
var lzl=[];
lzl["name"]="黑泽志玲";

lzl["语文"]=80;
lzl["数学"]=70;
lzl["日语"]=90;
console.log(lzl)
// 关联数组中  没有.length;
console.log(lzl.length)
console.log(lzl["日语"]);//

```

​    2.遍历写法

```js
//遍历  for循环
for(var key in lzl){ //key指的是下标
    //          下标    下标对应的值
    console.log(key+":"+lzl[key]);

}
```

##### 小结

```js
 //检测索引数组是否支持  for  in  循环
    var arr=["张飞","张无忌",'隔壁张',"张伟"];
    for (var key in arr){
        console.log(key+arr[key]); //支持
    }
    // 混合写  索引数组中 写入关联数组
    arr['中兴一哥']="隔壁老徐";
    console.log(arr);  //可以混着写
    console.log(arr.length); // 关联数组不会被算入 长度
```

#####  eval()   

​    直接执行js语句

```js
var str=prompt("请测试一段js代码");
// 假如用户输入  console.log("hello ");
eval(str); //去执行代码
```

##### es6字符串拼接

```js
 d1.style.background="rgb("+arr[0]+","+arr[1]+","+arr[2]+")";
  //es6的字符串 拼接  通过``引起所有的字符串
  //通过 ${变量} 书写变量  其他的字符串不变
d1.style.background=`rgb(${arr[0]},${arr[1]},${arr[2]})`;
```

### day06=======================================================

#### 数组API

##### 	1.String()/toString() 

​	       将数组转为字符串

#####  	2.arr.concat(值1,值2,...) ;  拼接

​		将多个数组组合为一个新的数组  不会改变原数组  

​	        参数可以是**数组**也可以是  **变量**

```js
    var arr=[0];
    var arr1=[11,22];
    var arr2=[33,44];
    //  生成一个全新的数组
    var newArr= arr.concat(arr1,arr2);
    console.log(newArr);//[0, 11, 22, 33, 44]
    // 原数组不会改变
    console.log(arr1);   //[11,22]
    console.log(arr2);  // [33,44]
 // 参数 可以是数组 也可以是变量
    var newArr2=arr.concat(1,2,3);
    console.log(newArr2); // [0, 1, 2, 3]
```

#####  3.arr.join("连接的字符")  

​		数组中的每个元素 通过  **字符** 拼接

​		返回的是一个**字符串**  原数组不会改变

```js
var arr=['h','e','l','l','o'];
var newStr=arr.join('-');
console.log(newStr, typeof  newStr);// h-e-l-l-o  string类型

var newStr2=arr.join("");
console.log(newStr2);  // hello
console.log(arr);//  原数组不会改变
```

#####  4.arr.slice( )  用于选取数组中的 元素(含头不含尾)

   特点:    复制出原数组 i 开始位置  一直到end +1表示结束位置  之间的元素

​          1.不会改变原数组

​	  2.省略2个参数  直接截取全部的元素

​              哪怕值全部一样 也不相等 (地址不一样)

​	  3.支持负数参数，从末尾开始数 

​           4.可以给一个参数  ，一个参数表示起始位置

```js
var arr=[12,34,54,56,73,23]
    //  0可以取得的  3位置取不到
    var newArr=arr.slice(0,3);
    console.log(newArr); // [12,34,54]
    console.log(arr); //  [12,34,54,56,73,23]  说明原数组不会改变

    // 如果不给参数  则 复制一份数据
    var newArr1=arr.slice();
    console.log(newArr1); //   [12,34,54,56,73,23]

    // 支持负数   含头不含尾
    var newArr2=arr.slice(1,-1);
    console.log(newArr2);  // [34,54,56,73]
   //表示 从-2位置 截取到 -1位置
    var newArr3=arr.slice(-2,-1);
    console.log(newArr3);  // 23

    // 一个参数 表示 起始参数  一直取到最后一个数字
    var newArr4=arr.slice(1);
    console.log(newArr4); // [34,54,56,73,23]
```

##### 5.splice() 可以  插入  删除等操作

​    1. 直接修改原数组

​    2.也支持负数 

 具体实现:

######    1.删除情况分析

​       arr.splice(i,n)  i:起始位置  n表示个数

​		如果n不给  则删除从i开始的全部元素

​                 i可以给负数 n不可以给

```js
// 1.删除  arr.splice(i,n)  i:起始位置  n表示个数
    var arr=[1,2,3,4,5,6,7,8]
    arr.splice(2,3);// [1,2,6,7,8]
    console.log(arr);
   // 2. 删除   1一个参数
    var arr2=[1,2,3,4,5,6,7,8]
    arr2.splice(3);//从3位置开始 删除全部
    console.log(arr2);// [1,2,3]
   //3 没有参
    var arr3=[1,2,3,4,5,6,7,8]
    arr3.splice(); //不写参 则不会修改原数组
    console.log(arr3);
   // 4 一个参 负数
    var arr4=[1,2,3,4,5,6,7,8]
    arr4.splice(-4); //  从-4的位置 开始删除
    console.log(arr4); //[1,2,3,4]
   //5. 2个参数 都是负数情况
    var arr5=[1,2,3,4,5,6,7,8]
    arr5.splice(-2,-4); //  个数不支持负数  但是不会报错 返回原数组
    console.log(arr5);
    //6. 2个参数 负数情况
    var arr6=[1,2,3,4,5,6,7,8]
    arr6.splice(-2,4); //  从-2位置开始删除4个
    console.log(arr6); //1,2,3,4,5,6
```

###### 	2.插入

​    	arr.splice(i:起始位置,0:不删除, 具体插入的值)

```js
// 插入
    var arr=[1,2,3,4,5];
    // 3: 起始位置   0不删除  12 23 34 插入的数据
    arr.splice(3,0,12,23,34);
    console.log(arr); //[1, 2, 3, 12, 23, 34, 4, 5]

    var arr1=[1,2,3,4,5];
    var arr2=[12,23,34]
    arr1.splice(1,0,arr2);
    console.log(arr1); //  整体的数组插入  不会打散
```

######   3.删除的同时 插入数据

​     arr.splice(i:下标,n:删除的个数,插入的具体的值)

```js
//3.删除同时插入
var arr3=[1,2,3,4,5];
//      1:起始下标  2:删除个数  13,14,15,16插入的数据
arr3.splice(1,2,13,14,15,16);
console.log(arr3); //[1, 13, 14, 15, 16, 4, 5]
```

######    4.新变量接收 发现

```js
 //接收  ==删除的内容 组成的新 数组
    var arr4=[1,2,3,4,5];

    var newArr=arr4.splice(1,2,3);
    console.log(arr4); // 1345
    console.log(newArr); // 2 3   删除的内容 组成的新 数组
```

###### 6.reverse()反转

​	 直接改变原数组

```js
var arr=[1,2,3,4,5];
// 直接可以使用的方法
var newArr=arr.reverse()  
console.log(newArr);    // [5, 4, 3, 2, 1]
//会直接改变原数组
console.log(arr);   // [5, 4, 3, 2, 1]  
```

###### 7.arr.sort() 排序

   	功能鸡肋:  1.只能升序   2.按照unicode编码比较 出问题

​            解决办法如下:

​	          参数进行 减法  自动转为number计算 

```js
//排序
var arr=[34,76,87,12,45];
var newArr=arr.sort();
console.log(newArr);  //[12, 34, 45, 76, 87]
// 会改变原数组
console.log(arr);    //[12, 34, 45, 76, 87]

var arr2=[12,1,11,111]
console.log(arr2.sort());  //[1, 11, 111, 12]
/*
* 原因:  字符串之间的比较  比的是unicode编码
* */
//解决办法
function f(a,b) {
   //   return a-b; //升序
    return b-a; //降序
}
//将整个函数座位参数 传给sort方法
console.log(arr2.sort(f));  //[1, 11, 12, 111]
// 或者是

arr.sort(function  (a,b) {
        return a-b;
    })
```

### day07============================================

#### 手写排序

 ![](assets/冒泡排序分析.png)

```js
//  排序
 var arr=[5,3,1,4,0];
function sort_new() {
    // 外围循环控制  轮数
    for (var i=1;i<arr.length;i++){
        // 每一轮比较的次数
         for(var j=0;j<arr.length-i;j++){
             //如果当前的下标对应的值大
             if(arr[j]>arr[j+1]){
                 //声明一个变量  用于接收最大值
                 // 将两个 数据进行互调
                 var big=arr[j]; 
                 arr[j]=arr[j+1];
                 arr[j+1]=big;
             }
         }
    }

}
 sort_new()
```

#### 手写去重  

![1595298550280](assets/1595298550280.png)

```js
var arr=[1,2,1,3,1,3,4,5,55,5];
    function qu() {
        //外围循环控制轮数
        var newArr=[arr[0]];//存放 不重复的数据  [1,2,3]
        for (var i=1;i<arr.length;i++){
            //里面挨个遍历 判断当前下标元素
            for(var j=0;j<newArr.length;j++){
                if(newArr[j]==arr[i]){
                    break;
                }
            }
            // 什么情况下  才追加到新数组中???
            //  arr[i] 当前值  把 newArr[]中 所有的值全部都比了一遍 才追加
           // 如果j==长度
          if( j==newArr.length ) (newArr[newArr.length] =arr[i]);
        }
        console.log(newArr)
    }
```

#### 数组的出入栈问题

#####    1.先进后出的问题

   ![1595298941365](assets/1595298941365.png)

   进栈:  arr.push();

   出栈(后出)  : arr.pop();

```js
<input type="button" value="加弹" onclick="bullet_p()">
<input type="button" value="射击" onclick="fire()">
<script>
    //  先进后出的  情况  push()进    pop()出
    var arr=[]
// 插入数据
    // 之前的写法
    arr[arr.length]="我是插入的";
    //现在的写法
      arr.push("我是新来的2")

//删除数据  之前的写法
   // arr.length--;
    // 删除数据
   arr.pop()  //删除数据   从末尾删除

    console.log(arr);

 //一口气压入8颗子弹
    var bullet=[];//存放子弹
  function bullet_p() {

      for (var i=1;i<9;i++){
          // 压入数据
          bullet.push("子弹"+i);
      }
      console.log( bullet )
  }
 //发射  移出数组元素
    //  ["子弹1", "子弹2", "子弹3", "子弹4",
    // "子弹5", "子弹6", "子弹7","子弹8"]
 function fire() {
     if(bullet.length>0){
         //  pop() 用变量接收 得到的是 删除的元素
         var b=bullet.pop(); // "子弹8"
         console.log(b+"射出");
     }
     //一口气子弹打光
 }  
```

##### 2.后进先出（vip）

![1595302537247](assets/1595302537247.png)

​      进(后面插入到最开头)    arr.unshift()

​      出(从最开头出)		arr.shift()

```js
   // vip 服务 特征
    //后进(起始位置插入) 先出(起始位置出)
    var arr=[12,4,45,2,321];
    //进 从开头进
    arr.unshift("我的新来的");
    console.log(arr);

    // 出 从开头出
    arr.shift()
    arr.shift()
    console.log(arr);
```

##### 3.先进先出

​    ![1595302823804](assets/1595302823804.png)

```js
var arr =[12,23,34,45];
// 进:  追加
arr.push(56);  // 56 进
console.log(arr);  // [12,23,34,45,56];

// 出:  开头端先出
arr.shift()   //12 移出
console.log(arr); //[23,34,45,56];
```

#### 二维数组

​    1.定义 : 数组中每个子元素都是数组

​     2.拿取数组:  

```
arr[i][j]  ； i:第几个元素  j:当前元素下 对应数组的下标
```

​    3.定义；	

```js
 //1.定义
    var arr=[];
    arr[0]=[1,2,3,4,5];
    arr[1]=[11,22,33,44,55];
    arr[2]=[111,222,333,444,555];
    console.log(arr);//二维数组
    console.log(arr[1][1]);//22
    console.log(arr[1][6]);//拿子元素中的数组下标越界 报 undefined
    // 二维数组中 不允许当前数组下标越界
    //console.log(arr[3][1]);//拿arr数组中的下标越界   直接报错

//2.  声明同时赋值
    var arr1=[
        [1,2,3,4],
        [2,3,4,5],
        [3,4,5,6，5]
    ]
    //6
    console.log(arr1[2][3]); // 6
    //遍历输出每一个值
    for (var i=0;i<arr1.length;i++){
        for(var j=0; j<arr1[i].length;j++){
          document.writeln(arr1[i][j])
        }
        document.writeln('<br>')
    }
```

#### 内置对象

​    js自带的方法 封装好了的   可以直接用 

 定义:  将原始类型的值封装好 赋予了一些操作的API方法 和功能

​           都是引用类型(数组也是)

​    语法:  String()  Nember()  Boolean()...

##### 1.区别

 	原始类型的值    : 存放在栈中     

​		也是数据 都是死值 没有没和功能(自己写着100块的小纸条)

​	 引用类型的值的区别 :    堆中  

​                 对象 可以使用属性和方法 (100人民币)

```js
    // 原始类型的值 做不到
    var str="喜欢你";                  // 纸条
    console.log(str.length); //3
    str.yy="我希望所有人都崇拜我";
    console.log(str.yy); //undefined

    //引用类型  原理上还是字符串  人民币 原理也是值
    // 特征 :   首字符大写  需要new 实现
    var str2=new String("隔壁老张");
    str2.yy="中年油腻大叔";
    // 自定义属性  后面对象见
    console.log(str2.yy); //中年油腻大叔
```

##### 1.String()对象

######   1.常见的方法

​	1.大小写转换

​	 str.toLocaleLowerCase()    转小写

​         str.toLocaleUpperCase()     转大写

```js
 var str="abcDEF";
    //转小写
    console.log(str.toLocaleLowerCase());
    //转大写
    console.log(str.toLocaleUpperCase());

    //验证码案例  模拟用户输入 不区分大小写
    do{
        var user=prompt("请输入验证码"+str);
        //验证码是否正确
        if(user.toLocaleLowerCase()==str.toLocaleLowerCase()){
            alert("验证通过");
            break;
        }else {
            alert("请重新输入");
        }
    }while (true)
```

   2.unicode编码

​      str.charCodeAt(2)

​      String.fromCharCode(编码）

```js
// 字符转 unicode编码   默认是10进制的数
var str="锄禾日当晚";
// 默认是 第一个字符
console.log(str.charCodeAt(2)); //26085 日

//编码 转字符串
console.log(String.fromCharCode(26085)); //日
```

### day08==============================================

#####   3.获取子字符串

​	str.substring(起始下标,结束下标);

​        str.substring(起始下标) ;  // 一直截到末尾
​        特点:负数无效

```js
var str="床前明月光";
 var newStr=str.slice(1,-3);
 console.log(newStr);// 前
 console.log(str);  // 不会改变原数组

   //            不支持负数
 var newStr1=str.substring(1,3);
 console.log(newStr1); //床
 // 不会改变原字符串
 console.log(str);
//  一个参数对应的是 下标
 var newStr2=str.substring(2)
 console.log(newStr2); //明月光
 // 不区分参数的大小   下标从小 到大 截取
 var newStr3=str.substring(2,1)
 console.log(newStr3); //明月光

 var newStr4=str.substring(-1,-3)
 console.log(newStr4); // 空

 // 第二个参数为负数  ->0  
    var newStr5=str.substring(3,-2);  //相当于从0-3 
    console.log(newStr5);
```

#####   2.str.substr(a，b)     字符串截取  

  	 a: 下标 可以为负数

 	   b: 个数	

```js
var str="锄禾日当午";
// substr
var newStr=str.substr(1,3);// 下标  个数
console.log(newStr); //禾日当

var newStr=str.substr(-1,3);// 下标  个数
console.log(newStr); //午
```

##### 3.查关键词下标

​	str.indexOf("xx")   返回关键词下标 如果没有返回**-1**

​        str.indexOf('xx',index)  : index 表示从下标index位置开始查找

```js
var  str ="u can u up , no can no  bibi";
//通过indexOf 查看关键词下标
var i=str.indexOf("can"); //
console.log(i); //2  默认返回第一个关键词位置

var j=str.indexOf("sb");
console.log(j);//-1   如果找不到 返回-1   

var x=str.indexOf("u",5);// 从下标5开始往后找 u
    console.log(x); // 6
```

#####  4. str.lastIndexOf() 

​       查找最后一个关键词下标

```js
var str="hello world";
// 从后往前找  关键词的下标
var i=str.lastIndexOf("o");
console.log(i);  //7

 var url="https://www.baidu.com/img/dong.gif";
     //   str 输出  .gif 后缀
    var index=url.lastIndexOf(".");
    console.log(url.substring(index))
    //    /dong.gif    文件名     不需要 / 所以 +1
    console.log(url.substring(url.lastIndexOf("/")+1));
```

##### 5.str.search(/正则/) ;

​	定义：查找符合条件的敏感词的位置   如果没有则返回-1;

​        特点: **只找一个**  从起始下标开始找

​        /正则/i  i: 不区分大小写.

```js
 var str="n玛,刚把裤子脱了，你妈就喊你回家吃饭？真你妈的扫兴，下次再也不叫你一起游泳了!";
 // 返回 下标   默认也是从下标0开始 查找
var i= str.search("尼玛");
 console.log(i);//0
 //可以匹配正则(稍后再说)   默认只能匹配一个
 var j=str.search(/[尼你][码吗妈玛]/);
 console.log(j);//10
var str1="U can u up , no can no  bibi";
     x=str1.search(/[u]/i);  // i表示不区分大小写
    console.log(x);// 6
```

##### 6.str.match(/正则/)

​     查找关键词  返回一个数组  可以查多个

​      默认还是找一个 找多个需要在正则后面加g 

​        如果只要一个关键字 会返回一个数组  可以拿去下标index

​      /正则/ig    g=>global:匹配全部

​    注意: 如果匹配多个 只能匹配关键词 无法获取关键词的下标

```js
var str="dao produce one,one produce two,two produce three,three produce all things";
//  查找关键词   默认也是找一个   需要加g  找多个
// 返回一个数组   接收的是 所以的关键词
var arr=str.match(/one/ig);  // g ：全部
console.log(arr); //["one", "one"]
```

##### 7.str.replace(/正则/,"替换的内容" )

```js
  var str=prompt("请输入评论")
    //  内容的替换
     var newStr= str.replace(/[日操草曹艹c大爷]/ig,"*")
     alert(newStr);
```

#### 正则表达式

#####    定义: 

​	    正义的法则  用来规定字符串的书写规范  

​            常见于 表单中  或者手动查询页面内容(筛选)

​            一个独立的模块 无论做什么开发 规则是固定的

#####    语法:

   1. 字符集

        规定一个字符的集合   

       语法:  []

        ex:    [操曹艹] ：表示的是 中括号中的字符串 只要出了了其中之一 就会被匹配到

        特点:只能[]中的匹配一个字符

      常见写法:

        [0-9]  ：匹配一个数字

        [a-zA-Z]： 匹配一个大小写字母

        [\u4e00-\u9fa5]  匹配一个汉字

      ```js
      var str="Hello 隔壁的老张 88";
      // var k=str.replace(/[123456789]/ig,"*");
      //   0-9 对应的数字
      //   a-z
      var k=str.replace(/[0-9]/ig,"*");
      console.log(k);
      //字母
      var k1=str.replace(/[a-zA-Z]/g,"*");
      console.log(k1);
      
      var k2=str.replace(/[a-zA-Z0-9]/g,"*");
      console.log(k2);
      // 匹配汉字   unicode编码 \u4e00-\u9fa5
      var k3=str.replace(/[\u4e00-\u9fa5]/g,"*");
      console.log(k3);
      ```

2.预定义字符集

​      \d   表示一位数字  

​		[0-9]

​      \w  表示一个有数字 字母+下划线组成的 字符

​		[0-9a-zA-z_]

​       \s  表示一个空字符 

​         .   任意的字符

```js
   var str="hello_ 隔壁老张 中年老帅哥 886";
    //  \d 数字
    console.log(str.match(/\d/ig)); // 886
    console.log(str.match(/\w/ig)); // hello_ 886
    console.log(str.match(/\s/ig)); // 空字符串
    console.log(str.match(/./ig)); //  匹配任意的字符
```

```js
[^xxx]  : 除了xxx
^[a-z0-9] ：以xxx开头  
\b        :边界
\D        :除了数字
\W		  : 除了 数字 字母 下划线
\S        :除了 空格
```

```js
console.log(str.match(/[^\d]/ig)); //  除了xxx  除了数字
console.log(str.match(/^[a-z0-9]/ig)); //  以xxx开头
console.log(str.match(/\b[a-z][a-z]\b/ig)); //  以xxx为边界  xu
console.log(str.match(/\D/ig)); // 除了数字 == [^\d]
console.log(str.match(/\W/ig)); // 除了数字字母下划线 == [^\d]
```

##### 2.数量词

​    限制个数

 {n}  具体个数 不能多也不能少

```js
var str="12a321 412heoas";
    //连续的6个数字
    console.log(str.match(/[\d][\d][\d][\d][\d][\d]/ig)); //321412
    //  数量词  通过{n}  n表示的具体的个数
    console.log(str.match(/[\d]{6}/ig)); // 321412
    console.log(str.match(/[\w]{6}/ig)); // 12a321  412heo
```

  {n,m}

```js
//{n,m}  表示 最小是n个 最大是m个 可以是 6 7 8 都要
console.log(str.match(/[\w]{6,8}/ig)); //12a321  412heoa
```

{n,}

```js
// {n,}  表示 最少n个 多了 不限制
console.log(str.match(/[\w]{6,}/ig));
```

##### 3.不限制的数量词

```
1.?  :  可有可无 最多只能出现一次  
        ex:  长途加0   或者 86  0086  可有可无
2. * ：  可有可无  可有出现多次
3. + :   必须出现一次 多了不会限制

```

```js
 var str="01aadaasd53汉子";

  // 最少出现一次    多了不限制
  console.log(str.match(/\d+[a-z]/ig)); //01a
// 可以有  可以无    只能出现一次
  console.log(str.match(/\d?[a-z]/ig)); //
  //  ["1a", "a", "d", "a", "a", "s", "d"]
// * 可以有可以无   可以出现多次
  console.log(str.match(/\d*[a-z]/ig)); //
  // ["01a", "a", "d", "a", "a", "s", "d"]

//模拟用户输入 11位手机号码   0可以加可不加只能出现一次
```

4.特殊字符

​    ^xxx  以xxx开头  

​               在[^]中的  表示 除了

​    $xxx  以xxx结尾

​    ()        可有把字符括起来

​     |        或者 

   \ .    => .

### day09=============================================

#### 1.高级替换.

​	str.replace(/正则/,function(e){return xxx;})

```js
     var str="one word go jia jia jia";// 让首字母大写
     //替换 为 大写
    //var newStr=str.replace(/\b[a-z]/ig,"*");
   // 除了可以跟 字符串 还可以跟一个callback回到函数
     var newStr=str.replace(/\b[a-z]/ig,function (e) {
         //e 就是正则匹配到的子元素
         // console.log(e);
         return  e.toLocaleUpperCase();
     });
     console.log(newStr);  //One Word Go Jia Jia Jia

```

##### 2.手动去除两边的 **空格**

```
 // 去除左边的 空格   /^\s*/ig
     console.log(str2);
     console.log(str2.replace(/^\s*/ig,""));
     //去除右边的空格
     console.log(str2.replace(/\s*$/ig,""));
     //2边都去 别忘了加 g
     console.log(str2.replace(/(^\s*)|(\s*$)/ig,""));
```

##### 3.trim()  去除空格

```js
   var str="   hello world    ";
    console.log(str);
    //  trim()  去除 2边的空格
    console.log(str.trim());
    //去除左边的
    console.log(str.trimLeft());
    // 去除右边的
    console.log(str.trimRight());
    //  ==左边的
    console.log(str.trimStart());
    // ==右边的
    console.log(str.trimEnd());
```

##### 4.str.split(/正则/)切割字符串

```js
var str="hello";
var code=str.split("");
// 不改变原字符串
console.log(str);
// 结论  切割位单个的数组元素  返回的是整体一个数组
console.log(code); //["h", "e", "l", "l", "o"]
//拼接回去
console.log(code.join(""));
var str2="  hello world  ";
// 链式编程
var code2=str2.trim().split(" ");
console.log(code2);
```

#### RegExp()     内置对象

​	1.简述 js本身提供了关于正则的内置对象 .可以用来提供验证和声明正则

​	 2.创建:

​		  1 var reg= /正则表达式/ig;	

​		   2 var reg= new RegExp('正则表达式',"后缀:i,g")		  

​        3.test()  用来检测 字符串 是否匹配成功正则 

​              reg.test(str)

1. ##### 直接创建

```js
 while (true){
       // 只能输入6位密码
       var str=prompt("请输入6位数字密码 ");
       var reg=/^\d{6}$/ig;
       //test() 用来测试字符串 是否符合正则标准
       //返回bool
       //console.log(reg.test(str));
       if(reg.test(str)){
           console.log("验证通过");
           break;
       }else{
           alert("密码输入不合格 重新输入")
       }
   }
```

##### 2.通过new创建

​	 可以实现动态的正则声明。

```js
//6位密码  //      \ 需要转移
    var reg =new RegExp("^\\d{6}$",'ig');
    console.log(reg); //   /^\d{6}$/gi
    console.log(reg.test("123456")); //true

    //正则可以 动态的生成
    var shi ="锄禾日当午,床前明月光,离离原上草";
    // 模拟动态的数据
    var arr=["日","光","草"];
    //  arr.join("|")  日|光
    var reg1=new RegExp(arr.join("|"),'ig'); // ==  /日|光|草/ig
    shi.replace(reg1,"*");
    console.log(shi.replace(reg1,"*"));// 锄禾*当午,床前明月*
```

##### 3.exec()  

​      即可以查找关键词的位置  也可以查找下标

​      注意: 默认也是找一个   如果想要找所有的 则需要循环遍历

​                获取关联数组中 属性名    需要加 " "

```js
 var str="one word go jia jia jia";
    var  reg=/jia/ig;
    // 默认也是找第一个
   var code=reg.exec(str);
   console.log(code); // jia

  /*  var reg1=/jiaa/ig;
    console.log(reg1.exec(str));*/ //找不到返回null;
    //? 拿到所有数据
    while (true){
        var kw= reg.exec(str);
        //如果kw是null 则终止循环
        if(kw!=null){
            //  关联数组中的 属性 需要加 ""
        //   console.log("在"+kw["index"]+"位置拿到数据"+kw[0]);
           console.log("在"+kw.index+"位置拿到数据"+kw[0]);
        }else
            break;
    }
```

### day10=====================================================================

#### Math (内置对象)

​     处理 数学计算的

```js
var num=123.01;

    // 取整
    console.log(parseInt(num));//123
    //上取整 不是四舍五入  只要小数点后面不是0都是+1
    console.log(Math.ceil(num)); //124
    // 下取整
    console.log(Math.floor(num)); //123
    // 四舍五入
    var num=12.56;
    console.log(Math.round(num)); //13
    // 幂运算
    console.log(Math.pow(5, 3));   // 5:底数   3:指数   5的3之方 5*5*5=125
    // 开根号
    console.log(Math.sqrt(81));//9
    var num1=12.3456536363;
    // 保留2位小数   返回的数据是string 类型如果计算则需要重新转为number
    var num2=num1.toFixed(2)+12;
    console.log(num1.toFixed(2)); //12.35
    console.log(num2); //字符串拼接的数据  12.3412  string
```

 Math 求最大最小值 去过数据存放在数组中 需要拆分掉挨个传入 

​     ...arr拆分

```js
//  15 20 14  56;  求最大值
 console.log(Math.max(12, 23, 34, 456, 5));
 //最小值
 console.log(Math.min(12, 23, 34, 456, 5));

 var arr=[12,34,45,76,78,34];
 console.log(Math.min(arr));// NaN
// 解决办法  拆掉数组装进去就可以
 // 通过  参数前面加...
 console.log(Math.min(...arr)); //12

  // 生一个随机数 0-1 取不到1
     console.log(Math.random());
    // 取绝对值
     console.log(Math.abs(-123));
```

#### Date  (内置对象)

​     定义: 和 时间有关的 方法

​     注意:    月份 是  0-11  

​                 星期:  从星期天开始算 0   一直到星期6 

```js 
 // 获取当前时间
  var now=new Date();
  console.log(now); //Fri Jul 24 2020 11:03:31 GMT+0800 (中国标准时间)
  // 指定时间和 格式
  //var now1=new Date("2020-07-24 11:05:23");
//  console.log(now1);

  // 获取当前的 毫秒数    从计算机元年到目前的时间的毫秒数
  console.log( new Date().getTime());// 1970.01.01 -目前的毫秒数
  //转为字符串
  console.log(new Date().toString());// Fri Jul 24 2020 11:10:27 GMT+0800 (中国标准时间)
  console.log(new Date().toDateString()); //Fri Jul 24 2020
  // 当前日期
  console.log(new Date().toLocaleDateString());//2020/7/24
  // 转了格式的  时间
  console.log(new Date().toLocaleString());//2020/7/24 上午11:11:38
  // 当前时间
  console.log(new Date().toLocaleTimeString()); //上午11:12:28

  //当前的年份
  console.log(new Date().getFullYear()) ;//2020
  console.log(new Date().getMonth()) ;// 6   默认是 0-11  正常月份+1
  console.log(new Date().getDay()) ;//  5     星期五
  console.log(new Date("2020-07-26").getDay()) ;//  0  星期日
  console.log(new Date().getDate()) ;// 24    日
// 时  分  秒
 console.log(new Date().getHours()) ;//  时间: 0-23  小时
    console.log(new Date().getMinutes()) ;//  分钟:  0-59分
    console.log(new Date().getSeconds()) ;//  秒钟 : 0-59
```

### day11======================================

#### 错误处理

##### 1. 常见类型

  **ReferenceError** ：引用错误    如果使用了未声明的变量 会报错

  **SyntaxError**         ：语法错误     使用了中文字符 或者是缺少括号

  **TypeError**              : 类型错误       错误的使用了数据类型或者是属性方法等

  **RangeError**            :范围错误         错误的使用了数据的使用范围

##### 2.自定义错误处理

​	可以自己指定错误  通过错误处理 防止影响程序的执行 或者给与友好的提示

 try{

​     // 可能产生错误的代码

}catch(err){

​    //err  通过try捕获的错误对象  

​    throw new Error("自定义抛出异常") 

} finally{   // 可选项  可以不写

   不管程序是否有错无错  最终都会执行

}

```js
 //错误处理

    //console.log(a); //ReferenceError 引用错误
  //  console.log(13)，  //SyntaxError    语法错误

   /* var arr=[];
    console.log(arr.length())*/  //TypeError  类型错误

    //var  arr= new Array(-2);  //RangeError   :范围错误
    var age=8;
    try {
        if(age>65||age<18){
            //错误提示
            throw  '年龄错误'
        }
    }catch (err) {
        console.log(err);
        //自定义抛出异常
        alert("只能是18-65之间的年龄")
    }
    console.log("执行了")

    // 通过错误处理     可以让程序正常执行
     try {
         console.aaa("123");
     }catch (e) {
         console.log(e); //  TypeError: console.aaa is not a function
         throw new Error("孙子，js语法会吗?") //自定义成自己想要提示的内容
     }finally {//  不管错对 都会执行的代码
         document.writeln("不管程序是否有错  我们照走不误")
     }
//如果不通过 错误处理  一旦错误 后面代码不再执行
    //  console.aaa("123");
     document.writeln("123")   //  不再执行
```

#### DOM(document Object Model) 操作

 作用: 通过API  操作页面的元素  ，w3c统一制定，几乎兼容所以的浏览器.

 浏览器遍历元素的模拟图

![1595830508922](C:/Users/HP/Desktop/%E7%AC%94%E8%AE%B0%20js/%E7%AC%94%E8%AE%B0/assets/1595830508922.png)

 网页中一切的内容都是以数形结构存储的，每一个元素(包括空格)都是一个节点对象

 树的根节点 叫做document. 包含了网页中所有的内容

##### 1.节点

​    元素 或者是空格 注释 都属于节点

​      1.nodeType 属性 	     判断节点的类型

​            element任何元素  返回的是   1

​            text         空格         返回的是    3

​            document               返回的是   9

​           attributes(属性值)是                  返回的是2

```js
var  str=""
    var arr=document.body.childNodes; // 拿取整个页面中所有的子节点
   console.log(arr); // 结论: 包含空格 text

    // 判断节点类型
    for(var i=0;i<arr.length;i++){
        console.log(arr[i].nodeType);// 3是空格 1元素
    }
    //拿取div title节点类型值       属性值 是  2
   console.log(arr[1].attributes.title.nodeType);  //2
```

​      2 **nodeName** 节点名称   判断元素的标签名 

  	  对应的是大写的标签名 

​            div		DIV

​            span	     SPAN 

​            空格              #text  ...

```js
// 拿到 节点 的名称
for(var i=0;i<arr.length;i++){
    console.log(arr[i].nodeName);//
    //节点名称是元素  大写标签名 比如 div :DIV
    // 空格的节点名称是  #text
}
```

​     3.nodeValue  节点的值     判断元素的值 比如属性值 文本的内容。

​		 ele 元素的 nodeValue    返回的是null

   	       document			返回也是null

​                 attributes                       返回属性的值

   		元素中的文本                返回的是具体的文本值

```js
//节点的值
   console.log(arr[1].attributes.title.nodeValue);//元素的属性的值
   console.log(arr[1].nodeValue) ; //null
   //  如果拿取的节点是text文本  则返回的是文本具体的值
    console.log(arr[1].childNodes[0].nodeValue);//我是div
```

#### 2.查找元素

##### 1.通过节点的形式查找(包含空格) (了解)

​       父子类 节点

​	 ele.childNodes     拿取子节点

​         ele.parentNode    拿取父节点   

```js
// 父子节点   子节点
      console.log(document.body.childNodes);//body元素下所有的子节点  9个
      //如果 没有加onload 则 .length:8  后面的空格拿不到
      console.log(document.body.childNodes.length);//body元素下所有的子节点  9个
      console.log(document.body.childNodes[1].childNodes[1].childNodes[1])//a连接
      //  父节点的使用
      console.log(document.body.childNodes[1].childNodes[1].parentNode)//a连接
```

​	兄弟类   (包含空格)

​	nextSibling下一个兄弟

​        previousSibling  上一个兄弟

```js
 //兄弟类  nextSibling下一个兄弟  
console.log(document.body.childNodes[1].nextSibling.nextSibling) //span
// 上一个兄弟   perviousSibling上一个兄弟 
console.log(document.body.childNodes[1].nextSibling.previousSibling)//div
```

##### 2.元素类型查找

​     相比于节点好处是 直接忽略空格

​      ele.firstElementChild  //第一个子元素

​      ele.lastElementChild    最后一个子元素

​      ele.children[n]		拿具体某个

​      ele.parentElement        父元素

```js
 //  不需要管空格
    //最大的div    firstElementChild 第一个子元素
    console.log(document.body.firstElementChild) //body下第一个元素
    //  lastElementChild 最后一个子元素
    console.log(document.body.firstElementChild.lastElementChild) //son2
    //拿具体某个
    console.log(document.body.firstElementChild.children[1]);// h1
    //拿取 父元素
    console.log(document.body.firstElementChild.parentElement);// body
```

##### 3.html查找

​     可以通过  id名   class名  标签名 name名

```js
   //1. 通过id去找   可以省略
    var span=document.getElementById("sp1");
    console.log(span);
    //2.按照标签的名称查找                  标签名
    var spans=document.getElementsByTagName("span");
    console.log(spans); //返回的一个数组
    //3.通过class类名查找
    var d2=document.getElementsByClassName("d2");
    console.log(d2);// 返回还是一个数组
    //4.还可以通过name属性查找
    var input=document.getElementsByName("txt");
    console.log(input); //返回的还是数组
    
    // 注意数组 如果要拿取具体的元素 需要通过具体下标拿取
```

注意:

   如果遍历的元素层级或者个数过多 可以先声明一个变量接收长度 

​      循环变量和声明变量做比较

```js
  // 直接写的情况
    //开始的时候 计时
    var now =new Date();
    for(var i=0,num=d1.getElementsByTagName("div").length;i<num;i++){
        console.log(d1.getElementsByTagName("div")[i]);
    }
    //计时
    var end=new Date();
    console.log(end-now);
```

##### 后面补充 根据选择器查找元素

​     document.querySelector("选择器")  ;      找一个   如果有多个默认会找第一个

​     document.querySelectorAll("选择器");   找所有

​      注意: 比如类名 要加.  id要 加#

```js
// 选择器查找
//1.  找第一个      如果有多个 默认只找第一个
var li=document.querySelector("#d1 li");
//  找第二个
var li=document.querySelector("#d1 li:nth-child(2)");
console.log(li);

//3.找所有的  
var lis=document.querySelectorAll("#d1 li");
console.log(lis);  //返回的是一个数组
```

##### 4.修改

```
d1.innerHTML="<h1>hello</h1>";// 支持html标记语言
d1.textContent="<h1>hello</h1>" //只能是纯文本
ipt.value="12345"  ;// 修改表单中的input的值
```

```js
<button id="btn" onclick="add()">0</button>
<input type="text" id="ipt" value="123456">
<div id="d1">hello</div>
<script>
    function add() {
        //拿取页面元素的值
       var txt= btn.innerHTML
        txt++;
       //修改值
        btn.innerHTML=txt;
    }
    //区别:  都是修改页面元素的值
    d1.innerHTML="<h1>hello</h1>";// 支持html标记语言
    d1.textContent="<h1>hello</h1>" //只能是纯文本
    // 拿取表单中的数据
    console.log(ipt.value);  //123456
 // js中的绑定事件
    d1.onclick=function () {
        console.log(d1.innerHTML) 
    }
</script>
```

### day12=========================================

#### 标准属性

##### 1.核心dom属性

​        xxx.attributes       获取所有的元素的属性  返回的是一个数组

​       xxx.getattribute("属性名")    获取属性名对应的值

​       xxx.setattribute('属性名','值')   修改属性的值  如果没有则自动添加属性名

​	xxx.hasattribute('属性名' )        判断是否存在对应的属性名

​       xxx.removeattribute('属性名')    删除对应的属性

 注意:  还可以设置或者是 获取自定义的属性和值

```
// 自定义获取或者 设置属性
d1.setAttribute("data-xu",'1');
```

```html
   <style>
        /* */
        .bgc{
            background: red;
        }
        .bgc_new{
            background: yellow;
        }
    </style>
</head>
<body>
<div class="bgc" title="这是个啥" style="background:blue;">点我变</div>

<script>
    // 先找人
    var d1=document.getElementsByTagName("div")[0];
     d1.onclick=function () {
         console.log(d1);
         //修改属性
         console.log(d1.attributes); //返回的是一个数组
         //1.获取某一个属性  title
         console.log(d1.getAttribute("title")); //这是个啥

         //2.修改 class的值
        // d1.setAttribute('class','bgc_new');
            // 修改style属性的值
          d1.setAttribute('style','background-color:black');

        //3. 判断有没有
         console.log(d1.hasAttribute("id")); // false

        // 添加属性  如果当前元素中没有id属性则 会自动添加
         d1.setAttribute('id','btn');
        //删除
        d1.removeAttribute('title');// 删除title属性
          // 自定义获取或者 设置属性
         d1.setAttribute("data-xu",'1');
     }
</script>
```

##### 2.html dom 操作属性     

​	非常的简便 如果有一天通过html dom拿不到对应的属性名 请记住还有一个哥们叫核心dom

​     xxx.属性名              获取一个属性   

​     xxx.属性名="值"     修改属性值

​     xxx.属性名==='值'   判断是否有对应的属性名

​    xxx.属性名=''             删除属性值

​    **特点**:   没有判断是否有对应的属性名方法  

​              不能直接拿取 自定义的属性  只能通过dataset拿取data-开头的属性的值

```js
<div id="d1" class="" title="123" score="98" data-xu="隔壁老徐">变</div>
<button>开/关</button>
<script>
    var d1=document.getElementById("d1");
    d1.onclick=function () {
        console.log(this.id); // 获取id属性的值
        //设置 修改属性
        this.className="bgc";

        console.log(this.title==="123") //判断属性的值是否是 xxx

        this.title="";

        // html dom 不能获取自定义的属性值
        console.log(this.score); //undefined
        // 核心 dom 可以直接拿到
        console.log(this.getAttribute("score")); // 98

        //html 只能拿到 data-开头的 自定义的属性  通过dataset属性拿到
        console.log(this.dataset.xu); // 隔壁老徐
    }
```

##### html dom 修改样式

   	xxx.style.样式属性

​	  注意:  样式属性如果是xxx-xxx  需要去掉-	改为驼峰命名

​        // ex: font-size  => fontSize 

```js
<button id="btn">变</button>
<div id="d1">我会改变</div>
<script>
    btn.onclick=function () {
        // html  dom  修改 添加样式
        //  属性是-系列  需要去掉- 改为驼峰命名
        // ex: font-size  => fontSize
        // 样式 都是 直接改在内联样式表中  元素中
        d1.style.fontSize="26px";
        d1.style.backgroundColor="yellow";
        d1.style.width="300px";
    }
</script>
```

##### 创建元素和删除元素

   1.创建   var div=document.createElement("标签名")

​    2.添加: 

​     d1: 父元素

​	1.末尾添加:     d1.appendChild(div);

​	2.任意位置插入 :d1.insertBefore(div,插入的位置元素); //在开头插入

​    3.删除:   d1.removeChild(xxx)  删除孩子

​	   d1.remove()   删除自己

​    4.替换: d1.replaceChild(div,旧元素)  新元素 替换为 旧元素	

 

```js
<button id="btn">添加</button>
<button id="btn1">删除</button>
<button id="btn2">替换</button>
<div id="d1">
    <div>老大</div>
    <div>老二</div>
</div>

<script>
    //1.创建元素
    var div=document.createElement("div")
    //2.添加文本信息
    div.innerText="我是后来的";
    div.style.backgroundColor="red";

    btn.onclick=function () {


        //3. 将创建好的元素 添加到页面中
         //d1.appendChild(div);  //末尾追加
        // 在开头插入   新元素     插入的位置元素
         d1.insertBefore(div,d1.firstElementChild); //在开头插入

    }
    //删除
    btn1.onclick=function () {
        //  删除  孩子
        //d1.removeChild(d1.lastElementChild)
        // 删除自己
        d1.remove()  //
    }

    //替换
    btn2.onclick=function () {
        //将新创建的元素  替换为 第一个孩子
        d1.replaceChild(div,d1.firstElementChild)
    }
</script>
```

```js
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <!--视口-->
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0">
    <style>
        /* */

    </style>
</head>
<body>
<h1>管理员列表</h1>
<table id="table" border="1" cellspacing="0" width="600">
    <thead>
    <tr>
        <th><input type="checkbox">全选</th>
        <th>管理员ID</th>
        <th>姓名</th>
        <th>操作</th>
    </tr>
    </thead>
    <tbody>
        <tr>
            <td>
                <input type="checkbox">

            </td>
            <td>1</td>
            <td>老徐</td>
            <td><button>删除</button></td>
        </tr>
        <tr>
            <td><input type="checkbox"></td>
            <td>2</td>
            <td>老张</td>
            <td><button>删除</button></td>
        </tr>
        <tr>
            <td><input type="checkbox"></td>
            <td>3</td>
            <td>老蔡</td>
            <td><button>删除</button></td>
        </tr>
        <tr>
            <td><input type="checkbox"></td>
            <td>4</td>
            <td>老王</td>
            <td><button>删除</button></td>
        </tr>
    </tbody>
</table>
<button id="clear">删除选定</button>
<script>
    //1.找到全选按钮
    var chbAll=document.querySelector("#table thead input[type='checkbox']");
    console.log(chbAll);
    //2. 找到所有的复选框
    var chbs=document.querySelectorAll("#table tbody input[type='checkbox']");
    //3.给全选按钮绑定事件 单击
    chbAll.onclick=function () {
        //      遍历所有的复选框 让全选按钮的checked和每一个复选框一致
        for (var i=0;i<chbs.length;i++){
            chbs[i].checked=this.checked;
        }
    }
    //4.给每个复选框绑定单击事件
    for (var i=0;i<chbs.length;i++){
       chbs[i].onclick=function () {
           //    如果当前复选框为false
           if(!this.checked){
               //           则all全选为false
               chbAll.checked=false;
           }else{ //否则
               //   如果所有的复选框都为checked
               //  找 所有的复选框中 没有被勾选的元素
               // 查找 被勾选的 复选框的个数 和复选框的个数是一致 则全选
              /* var box=document.querySelectorAll("#table tbody input:checked");
               console.log(box.length);
               if(box.length==chbs.length){
                   chbAll.checked=true
               }*/
               //     all就为true

               // 找没有被勾选的 如果为null   则全选
               var box=document.querySelectorAll("#table tbody input:not(:checked)");
               console.log(box);
               if(box.length==0){   //如果是空则所有全都被选中了
                   chbAll.checked=true;
               }

           }




       }
    }

    //5.添加删除功能
    //  1.找到所有的 删除按钮
    var btns=document.querySelectorAll("#table tbody button");
     //  遍历每个按钮 绑定单击事件
    for(var i=0;i<btns.length;i++){
        btns[i].onclick=function () {
            //     找到当前点击按钮的上一级的上一级 也就是tr 删除掉
            this.parentNode.parentNode.remove();
        }
    }
    //删除选定
    clear.onclick=function () {
        //找到所以勾选的 复选框
        var alls =document.querySelectorAll("#table tbody input:checked");
        // 遍历所有的被勾选的 复选框  把它的爷爷 tr  删掉
        for(var i=0;i<alls.length;i++){
            alls[i].parentNode.parentNode.remove();
        }
    }

</script>
</body>
</html>
```

#### 修改内部 或者外部样式表

​     1.进入样式表
  	  **var sheet=document.styleSheets[0];**
​      2.进入第一个 选择器 {}
​           **var sel=sheet.cssRules[0];**

​          注意: 一个sel 对应 一个{}  如果有多个{}  需要多个sle接收

​    3.修改样式
​            **sel.style.backgroundColor="yellow";**

```js
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <!--视口-->
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0">
    <!--样式表1的样式-->
    <style>
        .d1{
            width: 200px;
            height: 200px;
            border:10px solid #ccc;
        }
        #d2{
            text-align: center;
            background-color: #0AB5F3;
        }
    </style>
    <style>

    </style>
</head>
<body>
<div id="d1" class="d1">老大 </div>
<div class="d1" id="d2">我是老二</div>
<button id="btn">修改样式表中的样式</button>
<script>
    //  默认 直接修改元素的 属性 或者是样式 是直接在元素中的style样式中修改
    // 如果修改的是样式表中的样式  存在污染问题(是公用的)
    //  不推荐修改 样式表中的样式
    d1.style.background="red";
    d1.style.width="300px";
    //修改样式表中的样式
    btn.onclick=function () {
        //1.需要获得样式表1的对象
        var sheet=document.styleSheets[0]; //获取具体的style样式表

        //2 拿取.d1中的选择器中
        // 每进入一个cssRules 对应是一个{}
        var sel=sheet.cssRules[0];
        //3.修改样式
        console.log(sel)
          sel.style.borderColor="yellow";

        //拿取 #d2选择器
        var sel1=sheet.cssRules[1];
        //修改样式
        sel1.style.backgroundColor="yellow";
    }
</script>
</body>
</html>
```

### day14==============================================

#### BOM(browser object model ) 

   用处: 操作 浏览器窗口有关的API

  ex:  alert()   属于window下面的一个方法

​        window.alert("xxx")

​    js中默认的window可以省略

1. ##### 测试window 下的一些属性方法

```js
<div id="t1">
    <a href="">返回</a>
</div>
<script>
// 给window 绑定单击事件
    window.onclick=function () {
        console.log(this);// windows对象
        //   close()   关闭当前页面

    }
    //绑定 滚动事件
    window.onscroll=function () {
        //获取页面的滚动的高度
       var top=document.documentElement.scrollTop||window.screenTop;
        console.log(top);
        if(top>50){
            t1.style.display="block";
        }else{
            t1.style.display="none";
        }
    }
</script>
```

##### js可以通过open()    location 操作页面的跳转

```js
a href="http://www.baidu.com">在当前页面打开  可以返回</a><br>
<a href="javascript:open1()">通过js实现 在新页面打开 </a><br>
<a href="javascript:open2()">通过js实现  替换为当前的页面  不能返回 </a> <br>

<a href="javascript:open3()">通过js实现 只能打开一个新页面 </a>
<a href="http://www.baidu.com" target="dumon">通过a实现 只能打开一个新页面 </a>

<br>
<a href="javascript:open4()">通过js实现 可以打开多个新页面 </a>
<a href="http://www.baidu.com" target="_blank">通过a实现 </a> <br>
<script>
    //js打开 页面  可以后退
    function open1() {
        open("http://www.baidu.com");
    }
    function open2() {
        // 将url地址 替换为当前的页面  不能返回
        location.replace("http://www.baidu.com")
    }
    // open() 添加 第二个参数 dumon  可以实现用户只能打开一个新页面
    function open3() {
        open("http://www.baidu.com","dumon");
    }
    //可以打开多个
    function open4() {
        open("http://www.baidu.com","_blank");
    }
</script>
```

#### 定时器

​    定义: 让程序按照指定的步骤 按照指定的周期时间 走

​	 1.周期性定时器(反复的执行)

​    	  步骤1: 定义一个 函数      描述功能  需要干嘛

​                 function  test(){xxxx}

​     	 步骤2:  声明 启动定时器

​                  var timer=setInterval(函数名,执行的时间周期毫秒数)

​           	 注意: 函数名 不是调用 所以说没有()     毫秒数

​     	步骤3:(可以不加 尽量加)  停止定时器

​             clearInterval(timer)  ;

​             timer=null;  清空   定时器非常的消耗内存

```js
 // 只有页面完全加载完成 才执行
   window.onload=function () {
       //1.定义函数
       var btn=document.getElementById("btn")
       function test() {
           var txt=btn.innerHTML;
           txt++;
           btn.innerHTML=txt;
           console.log("hello")

           if(txt>10){// 
               //3.清除定时器
               clearInterval(timer);
               timer=null;
           }
       }
       //2.启动定时器
       var timer=setInterval(test,1000);
   }
```

​     2.一次性定时器

​        作用:  让程序 等待一段时间执行某个函数功能    只执行一次

​        语法:  

   		1任务函数 function test(){}

​		    2 启动  var timer= setTimeout(任务函数,时间)

​		          注意:  **时间指的是  等待的时间 不是执行的时间**

​		    3. 停止   clearTimeout(timer)	 	       

```js
window.onload=function () {
        alert("我来了");
        //隔了5秒之后再提醒一次
        // 1.函数
        function test() {
            alert("我又来了");
        }
        //2.启动       5000指的是  等待的时间
        var timer=setTimeout(test,5000);

        btn.onclick=function () {
            clearTimeout(timer);
            timer=null;
        }
    }
```

### day15===========================================

#### 1.history对象

​     作用:  记录 当前浏览器访问成功的网页的情况

​        前进一页:     history.go(1)    ===history.forward();

​        后退一页:     history.go(-1)   ===history.back();

​        刷新        :     history.go(0)  

#### 2.location

​      作用:保存url地址有关的信息

​        详情看下面的案例 测试

```js
    console.log(location)//  可以在控制台 输出  查看信息
    // 服务器端的主机名和端口号
    console.log(location.host);  //localhost:63342
    console.log(location.hostname);//主机名
    console.log(location.port);//端口号  63342

    console.log(location.href); //网页的完整的地址
    // url 地址 除了 主机和端口 的 剩余部分
    console.log(location.pathname);///web/web/02jsBase/day15/04_location.html
    console.log(location.protocol); //协议的名称   http /https

btn.onclick=function () {
        //  刷新
        //location.reload()
        //替换为新的地址网页
        location.replace("http://www.4399.com")
		
    }
```

#### 3.navigator对象

   作用：获取浏览器有关的信息

| 属性                                                         | 描述                                           |
| ------------------------------------------------------------ | ---------------------------------------------- |
| [appCodeName](https://www.w3school.com.cn/jsref/prop_nav_appcodename.asp) | 返回浏览器的代码名。                           |
| [appMinorVersion](https://www.w3school.com.cn/jsref/prop_nav_appminorversion.asp) | 返回浏览器的次级版本。                         |
| [appName](https://www.w3school.com.cn/jsref/prop_nav_appname.asp) | 返回浏览器的名称。                             |
| [appVersion](https://www.w3school.com.cn/jsref/prop_nav_appversion.asp) | 返回浏览器的平台和版本信息。                   |
| [browserLanguage](https://www.w3school.com.cn/jsref/prop_nav_browserlanguage.asp) | 返回当前浏览器的语言。                         |
| [cookieEnabled](https://www.w3school.com.cn/jsref/prop_nav_cookieenabled.asp) | 返回指明浏览器中是否启用 cookie 的布尔值。     |
| [cpuClass](https://www.w3school.com.cn/jsref/prop_nav_cpuclass.asp) | 返回浏览器系统的 CPU 等级。                    |
| [onLine](https://www.w3school.com.cn/jsref/prop_nav_online.asp) | 返回指明系统是否处于脱机模式的布尔值。         |
| [platform](https://www.w3school.com.cn/jsref/prop_nav_platform.asp) | 返回运行浏览器的操作系统平台。                 |
| [systemLanguage](https://www.w3school.com.cn/jsref/prop_nav_systemlanguage.asp) | 返回 OS 使用的默认语言。                       |
| [userAgent](https://www.w3school.com.cn/jsref/prop_nav_useragent.asp) | 返回由客户机发送服务器的 user-agent 头部的值。 |
| [userLanguage](https://www.w3school.com.cn/jsref/prop_nav_userlanguage.asp) | 返回 OS 的自然语言设置。                       |

```js
    console.log(navigator);//浏览器有关的数据
    console.log(navigator.appCodeName);// Mozilla  处于兼容性考虑
    var txt=navigator.connection.effectiveType; //返回的是网络的连接 g数
alert("您当前使用的是"+txt+"网络");
```

#### 4.事件绑定  重点

##### 1.html元素中绑定

```html
<div onclick="方法()" > </div>
```

##### 2.js中绑定事件

```
div.onclick=function(){
    
   this-> 当前点击的元素
}
```

  3.如果想要解除绑定则可以通过

​       div.onclick=null;  //解除绑定

```js
<button id="btn">发射</button>
<button id="btn_clear">解除</button>
<script>
    //绑定
    btn.onclick=function () {
        alert("发射一枚导弹")
    }
    //解除绑定
    btn_clear.onclick=function () {
        btn.onclick=null;
    }
</script>
```

  问题:    上面的方式没有方法 让一个元素绑定多个事件

##### 解决  

  **通过 xxx.addEventListenter("事件名","处理函数")**

  特点: 可以绑定多个事件

​    可以移除 

​    语法:  btn.removeEventListener("事件名",移除的事件方法)

```js
<button id="btn">发射</button>
<button id="dazhao">学习大招</button>
<button id="fei">自废武功</button>
<script>
   //测试 一个元素 绑定 多个单击事件
   //  onclick=xxx
   //没有办法做到 一个元素绑定多个事件
/*    btn.onclick=function () {
        alert("发射一枚导弹")
    }
    btn.onclick=function () {
        console.log("发射一枚导弹")
    }*/
// 下面这种方式 就可以实现
    btn.addEventListener("click",function () {
        alert("发射一枚导弹")
    })
   btn.addEventListener("click",function () {
       console.log("发射一枚导弹")
   })
    // 螺旋丸  多重影分身
   function lxw(){
        console.log("螺旋丸 很厉害")
   }
   function dcyfz(){
        console.log("可以分出很多人")
   }
   //添加单击事件
   //点击 dazhao 一口气给btn添加了2个方法  不要加()
   dazhao.addEventListener("click",function () {
        //同时绑定多个事件
        btn.addEventListener("click",lxw)
        btn.addEventListener("click",dcyfz)
    })

   //移出绑定的单击事件
   fei.addEventListener("click",function () {
       //移出 多重影分身的方法
       btn.removeEventListener("click",dcyfz)
   })
```

​           

##### 事件的三个阶段

```js
*   1.捕获阶段:  Js引擎会从外往里 挨个找 事件处理函数  并 记录下来
*   2.触发执行:
*      ex: 单击事件 则是 点击触发 直接执行目标元素对应的事件处理函数
*   3. 冒泡:  紧接着 挨个的从当前触发对应的函数开始往 外 执行元素对应的事件处理函数。
```

  案例测试 结论:

​    和用什么方式绑定事件无关      是js事件本质

```js
//特点  如果点击子元素  则父元素也会被跟着点击到
/*d1.onclick=function () {
    console.log(this.id);
}
d2.onclick=function () {
    console.log(this.id);
}
d3.onclick=function () {
    console.log(this.id);
}*/
/*
*   以上的情况  学名叫    冒泡
*   事件的三个阶段
*   1.捕获阶段:  Js引擎会从外往里 挨个找 事件处理函数  并 记录下来
*   2.触发执行:
*      ex: 单击事件 则是 点击触发 直接执行目标元素对应的事件处理函数
*   3. 冒泡:  紧接着 挨个的从当前触发对应的函数开始往 外 执行元素对应的事件处理函数。
*
* */
// 和 上面的onclick 无关   是js事件本质
function log(){
    console.log(this.id);
}
d1.addEventListener("click",log);
d2.addEventListener("click",log);
d3.addEventListener("click",log);
```

好处:  

![](assets/1596176167397.png)

##### 阻止冒泡

​     e.stopPropagation();

​     事件处理函数中 默认都有事件对象:e   (需要手动传入 )
​     特点:  

​              1. 一定要放在第一个参数

​	      2.事件一旦触发 自动创建  

```js
  
    function log(e){
        // 阻止事件冒泡
        e.stopPropagation();
        console.log(this.id);
    }
    d1.addEventListener("click",log);
    d2.addEventListener("click",log);
    d3.addEventListener("click",log);
```

**冒泡的好处**
     减少事件监听的个数    事件绑定越多 越卡

​      今后 如果希望每个子元素都处理相同的事情  可以直接给父元素绑定一次事件

​               子元素可以通过 冒泡的机制 实现公用

​                获取子元素 不再使用**this**  =>  **e.target** 

```js
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <!--视口-->
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0">
    <style>
        /* */
        #parent div{
            border:1px solid red;
            margin: 10px;
        }
    </style>
</head>
<body>
<div id="parent">
    <div>60</div>
    <div>78</div>
    <div>56</div>
    <div>37</div>
    <div>89</div>
    <div>77</div>
    <div>65</div>
</div>

<script>
    //之前的写法
    var divs=document.querySelectorAll("#parent div");
    var parent=document.getElementById("parent");
    // 遍历 所有的 div 给每个div都绑定一个事件监听 有多少个div绑定多少个
    //  餐厅每个用户 都绑定一个服务员  随时听后差遣
   /* for (var i=0;i<divs.length;i++){
        divs[i].onclick=function () {
            console.log(this.innerHTML);
        }
    }*/
    //  如果事件监听 太多 非常的影响性能
    parent.addEventListener("click",function (e) {
        console.log(this); // 此时的this 执行的是父元素

        // 用t.target 替换掉this

        // 此时的 e.target  对应的就是那个触发的元素
        console.log(e.target.innerHTML);
    })
</script>
</body>
</html>
```

### day16=====================

#### 1.a的默认事件

​      默认情况下  点击a 自动的跳转href页面    要么就刷新了， 没有办法停留

​    可以通过事件绑定addEventListener 阻止默认的a的跳转

​     **e.preventDefault() ;**      阻止默认a跳转

<a href:'javascript:;'></a>

```js
d1.addEventListener("click",function (e) {

    //阻止冒泡
     //e.stopPropagation()
    //阻止默认的a的跳转
    e.preventDefault() ;
    d1.className="red";
})
```

#### 2.offset系列 

​     获取当前元素的 高度 宽度  以及 元素距离页面左边 顶部等距离

​     特点:  

​	获取的宽度: **包含 内边距和边框**

​        

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <!--视口-->
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0">
    <style>
        /* */
        *{
            margin: 0;padding: 0;
        }
        body{
            padding: 50px;
        }
        div{
            width: 200px;
            height: 100px;
            margin: 20px;
            background-color: #a17768;
            border:5px solid #2aaad1;
            padding: 13px;
        }
    </style>
</head>
<body>
<div id="d1">
    hello
</div>
<button id="btn">获取div信息</button>
<script>
    btn.onclick=function () {
        // 包含 边框+内边距+width
        console.log(d1.offsetWidth)// 宽  236
        //同上
        console.log(d1.offsetHeight) //高  136

        // 当前元素到 页面的左上角(0,0)的距离
        console.log(d1.offsetLeft); //20
        console.log(d1.offsetTop);  //20
    }
</script>
</body>
</html>
```

#### 3.滚动有关scroll系列

   定义: 获取滚动条的距离 (必须有滚动条才有效)

​     scrollLeft:  向左滚出去的距离

​     scrollTop:  向上滚动的距离

​     scrollWidth:  元素的宽 (包含滚出去的值)

​     scrollHeight:元素的高 (包含滚出去的值) 

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <!--视口-->
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0">
    <style>
        /* */
        *{
            margin: 0;padding: 0;
        }
        #d1{
            width: 200px;
            height: 200px;
            border: 1px solid #ccc;
            overflow: auto;
        }
        #p{
            width: 500px;
            height: 500px;
            border: 1px solid #ccc;
        }

    </style>
</head>
<body>
<div id="d1">
    <p id="p">
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Accusamus aliquid amet consectetur in possimus quam. Aperiam, assumenda autem dignissimos eius eligendi odit quas quisquam repellendus repudiandae sapiente tempora vitae voluptatem.
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Aliquid, at debitis delectus deleniti dicta eaque eligendi eum facilis impedit incidunt ipsum laborum libero nisi nobis quam quis reprehenderit rerum saepe?
    </p>
</div>

<script>
    var d=document.getElementById("d1")
    d1.onscroll=function () {
        // 测试和滚轮 有关的
       // console.log(d1.scrollTop);// 滚动往上的距离
      //  console.log(d1.scrollLeft);//滚动往左的距离
        console.log(d1.scrollWidth);  // 502 里面大盒子的宽度 包含边框
       console.log(d1.scrollHeight); //534   32是p上下默认的外边距
    }
</script>
</body>
</html>
```

#### 4.client系列

​        元素的可视区域:

​       clientWidth:元素的宽度  (不包含边框 )  实际的宽度

​       clientHeight:元素的高度(不包含边框)  实际的高度

​       clientLeft:   元素的左边宽 宽度

​       clientTop:  元素 上边框的宽度

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <!--视口-->
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0">
    <style>
        /* */
        *{
            margin: 0;padding: 0;
        }
        body{
            padding: 50px;
        }
        div{
            width: 200px;
            height: 100px;
            margin: 20px;
            background-color: #a17768;
            border:5px solid #2aaad1;
            padding: 13px;
        }
    </style>
</head>
<body>
<div id="d1">
    hello
</div>
<button id="btn">获取div信息</button>
<script>
    btn.onclick=function () {
        // clientWidth  整体宽度 = width+内边距  不包括边框
        console.log(d1.clientWidth); //226
        console.log(d1.clientHeight); //126
        console.log(d1.clientLeft); //5  元素左边边框的宽度
        console.log(d1.clientTop); //5   元素上边框的高度
    }
</script>
</body>
</html>
```

#### 5.鼠标的三对儿

   1.当前点击的元素位置距离屏幕的距离  ：  e.screenX /e.screenY

   2 当前点击的元素位置距离 网页的左上角的距离:    e.clientX/e.clientY

3. 当前点击的元素位置距离 元素的左上角的距离  :  e.offsetX/e.offsetY

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <!--视口-->
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0">
    <style>
        /* */
        *{
            margin: 0;
            padding: 0;
        }
        div{
            width: 200px;
            height: 200px;
            margin: 200px;
            background-color: #a17768;
            /*border:5px solid #2aaad1;*/
            /*padding: 13px;*/
        }
    </style>
</head>
<body>
<div id="d1">

</div>

<script>
    d1.onclick=function (e) {
        //当前点击的位置到 屏幕左边的距离  (和浏览器无关)
        //console.log(e.screenX);
        //当前点击的位置到 屏幕顶部的距离   (和浏览器无关)
       // console.log(e.screenY);

        //分别到网页 左边 顶部的距离
      //  console.log(e.clientX);
       // console.log(e.clientY);

        // 当前点击的.到 当前元素的左上角的距离
        console.log(e.offsetX);
        console.log(e.offsetY);
    }
</script>
</body>
</html>
```

#### 鼠标移入移出区别

   一组是:   **onmouseenter /onmouseleave**

  二组是:     **onmouseover/onmouseout**     

   区别:    如果有子元素的情况下    一组移入子元素 不会触发事件

​                    					二组移入子元素中 则会触发事件

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <!--视口-->
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0">
    <style>
        /* */
        #parent{
            width: 500px;
            height: 500px;
            background-color: aqua;
            /*display: inline-block;*/
        }
        #son{
            background-color: antiquewhite;
            width: 100px;
            height: 100px;
        }
    </style>
</head>
<body>
<div id="parent">
    <div id="son"></div>
</div>

<script>
    var parent=document.getElementById("parent");
   window.onload=function () {
    /*   //鼠标移出 移出
   //  如果  父元素中有子元素 下面的方法 进入子元素 不会触发
       parent.onmouseenter=function () {
           console.log("onmouseenter  进入执行了")
       }
       //出
       parent.onmouseleave=function () {
           console.log("onmouseleave  出执行了")
       }*/

    // 如果  父元素中有子元素 下面的方法 进入子元素 也会触发事件
         parent.onmouseover=function () {
             console.log("onmouseover  执行了")

         }
       parent.onmouseout=function () {
           console.log("onmouseovout  执行了")

       }
   }
</script>
</body>
</html>
```

## jsCore

### day01

内置对象:Function

创建函数:

1. function  函数名(参数列表){

    函数体

   return xxx;// 不是所以的函数都有

   }

2.var 函数名=function(xx){xxx}

//  不会被声明提前

3. 通过new创建

4.var 函数名=new Function("参数","参数2"，"函数体");

```js
<script>

    function fun() {
        console.log(1111)
    }
    fun() //2222
    function fun() {
        console.log(2222)
    }
    fun() //22222
 var   fun=100;  // fun改为一个普通的变量 用于接收一个简单数据
   // fun(); //报错

  // 解决办法  通过
  var  fun1=function () {
      console.log(1)
  }
    fun1();//
  var  fun1=function () {
        console.log(2)
    }
    fun1();//

// 3. new   了解  
    var fun2= new Function('a','b',"return a-b");
    console.log(fun2(12,2))//10
</script>
```

#### 重载:overload

 定义:  相同的函数名，根据参数的个数不同，在调用执行参数不同的同时，对应的执行的函数体也不相同。

 目的: 减少API的名字，减少开发调用者的负担

 原理: 任意的函数中 自带的一个arguments属性 可以用来判断参数的不同从而实现不同的功能。

  arguments:  每个函数都会自动创建    是一个对象

   相对于数组来说   也有下标也有.length长度  可以遍历

  应用: arr.splice() arr.replace()..都是通过实现

```js
<script>
    function add(a,b) {

        console.log(a+b);
        console.log(arguments)// 对象
        console.log(arguments.length);//2
        console.log(typeof arguments);// object 不是数组
    }
    add(12,22);

    //不管多少个参数 都进行累加
    function add1() {

        for (var i=0,sum=0;i<arguments.length;i++){
                sum+=arguments[i];
        }
        return sum
    }

    console.log(add1(12, 23, 34, 45));
    console.log(add1(12, 23, ));
</script>
```

// 自己实现 通过判断不同的参数进来 是现金 还是刷卡还是 扫码

#### 回调函数

 将函数整体作为一个参数 传入另一个函数中去使用

```js
<script>
    //回调函数
    function callback() {
        console.log("我是回调函数 被调用。")
    }
    //调用函数
    function f(fn) {
        fn();// 函数里面再去调用
    }
    // 不要加()  作为参数传入
    f(callback)

    // 排序  应用
    var arr=[12,23,4,5,33,6]

   /*   拆分写法
    function call(a,b) {
        return  a-b;
    }
    arr.sort(call)*/
   //一步到位
    arr.sort(function (a,b) {
        return  a-b;
    })
    console.log(arr)
</script>
```

#### 匿名自调函数

  定义: 定义函数时 不需要给函数名，如果只要这个函数执行一次就永远不再使用了。 如果说用变量声明的话 还会存在内存中占据内存空间、匿名自调用于解决这个问题

  优点: 使用完立马释放  节约内存

语法:

```js
<script>
    // 方式1
    (function () {
        console.log("匿名自调执行了") //执行了
    })();
    //方式2
    +function() {
        console.log("匿名自调执行了2222") //执行了
    }()
    // 延伸  传参数
    +function (a,b){
         console.log(a+b)
     }(1,2)  //传参数
</script>
```

  优化:  js代码最外围写一个匿名自调所有的功能执行完之后就释放 了内存

​		尽量的不在全局中 声明全部的变量。

#### 作用域

#####   1.范围

​	全局作用域:   所有都可以用  容易造成数据的污染。 

​				除了在函数内，其他的区间都是全局作用域

​        局部作用域:   在特定的区域(函数中) 才可以被使用

​					用完之后就会被内存清空，就不会占空间

​					不能被再次使用

​	全局变量:

​		在全局作用域中使用var声明的变量  哪里都可以用，函数中也可以用

​		只要页面不关闭 那么全局变量就会一直存在。用于占据内存

​	局部变量: 

​		只是在函数内声明的变量，只能在函数中使用 全局是不可用。

​		用完之后随着局部作用域对象一并释放。

#### 作用域链

​    由多个层级作用域组成的一个链式调用

```js
<script>
    var money=12345;  //你太爷爷
    function f1() {  //你爷爷
       //  var money=8000;
        function f2() {  //你爸
          //  var money=5000;
            function f3() {  //你自己
              //  var money=5;
                console.log(money)
            }
            f3()
        }
        f2()
    }
    f1() //iphone12
    //   你=> 你爸 =>你爷爷=>你太爷爷  这一整条线就是    作用域链
</script>
```

#### 闭包

#####   定义:  

​	当我希望使用一个变量，即会被污染。又能够重用 ，就可以通过闭包机制实现。

#####   组成:

​	1外层函数
​	2受保护的变量
​	3返回到外部的内存函数(操作受保护的变量)

#####    注意:

​	弊端  只要程序不结束 则变量a一直存在内存中无法释放
​		  闭包使用完之后 一定手动清除闭包

 		将接收内层函数变量设为null

```js
  // 普通的函数
 //  var a=10   放在外面 可以重用  但是容易污染
/*  var outer=function () {
      var a=10; // 放在里面 不会污染 但是每次都会刷新
      console.log(++a)
  }
  outer() //11
  outer() //11
  outer() //11
  outer() //11*/

// 闭包   三要素
  // 1外层函数
  // 2受保护的变量
  // 3返回到外部的内存函数(操作受保护的变量)

  function outer() {  //1外层函数
      var a=10; //2受保护的变量
      return function () { //3.返回到外部的内存函数(操作受保护的变量)
          console.log(++a)
      }
  }
 //  outer();//没有意义 带返回值的函数需要接收
  var num=outer();
  console.log(num); // function(){ console.log(++a)}
   //调用
  num()//11
  num()//12
  a=18// 使劲污染   结果发现 无效
  num()//13

  //弊端  只要程序不结束 则变量a一直存在内存中无法释放
  // 闭包使用完之后 一定手动清除闭包
  num=null// 不再有接收内存函数的变量了。
```

//至于为什么可以去看一下闭包图解

作业:

```
<ul>
    <li>张三丰</li>
    <li>李思峰</li>
    <li>汪五峰</li>
</ul>
控制台等待5秒后打印出所有的li的内容
```

### day02

### 面向对象

####    1.对象:

​	具体到真实属性行为的实时存在的事物

​        属性:  对象的一些特征 一些状态  

​	行为: =>通过函数或者是方法实现

​	ex: 教室的格力空调:多高 多中 风俗 ...

面向过程:

​	所有的事物都要亲历亲为，注重过程。

​	优点是: 性能高，比如单片机就是面向过程开发的。

​	缺点:  不易维护 不能复用，不易拓展。

面向对象:

​	提出需求，通过需求找对应的对象解决，不需要注重过程，通过封装好的对象实现就可以了。

​	优点:容易维护，复用，拓展。因为具备封装、继承、多态的特性。

​	 缺点: 相对来说 性能有所将低的。

面向对象的三大特征

​	封装  继承 多态

##### 1.封装:

​	可以将一些可能会重用的内容，进行打包 在需要的时候直接拿来用。

​	ex: 可以将一个值存放在变量中 把一些重复的代码放在function中

​	可以把很多相同的功能的函数 放在一个对象中。从而实现了对象的多个属性和方法。

​	总结:  创建一个对象是保存的事物的属性和功能。	

​	目的: 便于大量的数据的管理和维护。

#####   2.继承

​	类和类之间的关系，此时的js没有类的概念、通过构造函数的概念实现的等价继承

​	 基于 原型。

​	 父类有的属性和方法、如果是子类则可以直接使用不需要再去创建。

​       目的:   代码的重用。

#####  3.多态

​	子类也具有自己的特性。不同的子类产生的属性 效果 功能不同 从而达到一个多样性	

##### 4.对象的创建

​	1.字面量对象的创建

​		属性:  保存在对象中的变量

​		方法: 保存在对象中的函数function

​	 注意: 访问对象中的属性和方法的时候 需要加前缀 this. 表示的是当前的这个对象

​	var obj={

​		属性名1：值1,

​		属性名2:  值2，

​		方法名:  function(){xxx}

​	}

```js
<script>

    var obj={
        uname:"莉莉",
        age:"18",
        height:"178cm",
        sayHi:function () {
            console.log("亲爱的")
        } ,
        eat:function () {
            console.log("每天红烧肉2斤")
        },
        iner:function () {
            alert(`大家好,我叫${this.uname},我今年${this.age},我身高${this.height}`)
        }
    }
    console.log(obj);
    //调用没有声明的属性
    console.log(obj.weight);// 没有的属性 报undefined
    obj.sayHi()
     // eat()//报错
</script>
```

##### 对比对象和关联数组的特征

```js
<script>
    // 关联数组
    var xu=[];
    xu["math"]=89;
    xu["chinese"]=88;
    xu["eng"]=18;
    // 对象
    var zhang={
        math:88,
        chinese:56,
        eng:68
    }
    console.log(xu) //  [xxx]   Array()
    console.log(zhang) //  {xxx}  Object()
    //访问属性   对象也好 数组也好 都可以采用2种方式访问属性
    console.log(xu["math"],xu.eng);
    console.log(zhang["math"],zhang.eng);

    //访问不存在的属性
    console.log(xu.music,zhang.music) //undefined undefined

    // 给不存在的属性赋值   直接创建到对象/数组中
    xu.music=99;
    zhang.music=19;
    console.log(xu,zhang)
    //遍历数组 和对象
    for (var key in xu){
       //  console.log(key)
        console.log(`${key} : ${xu[key]}`)
    }
    for (var key in zhang){
        //  console.log(key)
        console.log(`${key} : ${zhang[key]}`)
    }
    //删除对象中的某个属性
    delete xu.music
    delete zhang.music

    console.log(xu,zhang)
</script>
```

##### 结论:  

 1. js中的对象可以在任何时候添加新是属性和方法

 2. 如果赋值的属性不存在 不会报错 直接在对象中添加新的属性

       可以 通过 obj.xxx===undefined 如果等于意味着当前属性不再对象中

 3. js中对象的本质是关联数组

      可以通过关联数组的形式 对象['属性名']去访问对象的属性

4. 变量对象中的属性和方法 可以通过  

   ​	 for (var key in obj){}

##### 2.new创建

```js
   var obj=new Object()
 //添加属性
     obj.uname="隔壁老张";
    obj.age=48;
    obj.sayHi=function () {
        console.log(`大家好我叫${this.uname},我今年${this.age}`)
    }

    obj.sayHi()//调用
    console.log(obj.uname,obj["uname"]);
    //遍历
    for (var key in obj) {
        console.log(obj[key])
    }
```

前面的 一次只能创建一个对象 反复创建多个相同结构的对象所对应的效率低 重用差

##### 3.工厂模式创建

​	结合函数和对象的特征

```js
<script>
    // 字面量对象  重用性差

    // 函数是可以重复的被调用的
   /* function add(a,b) {
        console.log(a+b)
    }
    add(12,23)
    add(2323,2323)*/
    // 工厂模式    函数和对象结合
     function createObj(name,age) {
         var obj=new Object()
         obj.name=name;
         obj.age=age;
         obj.sayHi=function () {
             console.log(`大家好我叫${this.name},我今年${this.age}`)
         }
         return obj;
     }
     //创建一个 张三
    var zhangsan=createObj("张三",20)
    console.log(zhangsan);
     zhangsan.sayHi()
    var lisi=createObj("李四",21)
    lisi.sayHi()
    lisi.height="178"//自己添加的  
</script>
```

实际上 上面的这种结构 就类似于      构造函数(杯子的模子) 

 可以通过构造函数 反复的创建对象(绝大部分的数据和方法是相同的)

 目的是提高代码的重用性和效率

##### 构造函数

​	 要求构造函数的**首字母大写** 目的是为了区分普通函数

1.创建

​	this指的是创建的当前的对象  

​	值 一般是传过来的参数把列表中的实参。

```
function  函数名(参数列表){
    this.属性1=值1;
    this.属性2=值2;
    this.方法名=function(){xxx}    
}
```

其实我们之前学的  new的  Object   Array Function...都是js已经封装好的构造函数

##### 自定义构造函数

```js
<script>
    //  首字母大写
    function Person(name,age) {
        // this.name: 当前实例化对象的属性名
        //  name : 构造函数传进来的实参
        this.name=name;
        this.age=age;
        this.sayHi=function () {
            console.log(`大家好我叫${this.name},我今年${this.age}`)
        }
    }
    // 实例化对象
    var  ming=new Person("小明",18);
    console.log(ming);//{xxx}
    ming.sayHi() //打印了

    function Dog(name,age) {
        this.name=name;
        this.age=age;
        this.eat=function () {
            console.log("都21世纪了 我不再吃屎了")
        }
        this.sayHi=function () {
            console.log("汪汪汪")
        }

    }
    //实例化 狗的对象
    var dahuang=new Dog("大黄",2);
    dahuang.eat()
    console.log(typeof dahuang); // 判断数据类型
  //判断构造函数是哪一个    是不是属于这一类
    console.log(dahuang instanceof Dog)// true
    console.log(dahuang instanceof Person)// false


    console.log(dahuang instanceof Object)// true
    console.log(ming instanceof Object)// true
    
</script>
```

##### 继承

​	父对象的成员属性或者是方法 ，子类无需创建，可以直接使用。

​	目的就是为了代码重用，提高效率，节约内存。

ex: 杯子 想要在底部加一个底座记号， 如果每生产一个再叫显然效率低了，

​	 思路: 直接给杯子的模具去修改添加底座记号。

原型对象: 在父对象中 用来 集中保存子类共有的成员属性和方法

 		注意:不需要手动创建，定义构造函数时 自动就有了。 

在使用构造函数创建子对象时，自动的设置子对象继承构造函数中的 原型对象。

直接放在原型对象中的属性和方法  子类就可以通过.(继承)访问构造函数的原型对象。

##### 实现方式

​	定义原型对象中公共的属性和方法的实现

​        通过**构造函数.prototype.成员属性/方法=值/function(){}**

​	只有希望所有的子类都公用的方法和属性就会方法构造函数的原型对象中。		

```js
<script>
    function Person(name,age) {
        // this.name: 当前实例化对象的属性名
        //  name : 构造函数传进来的实参
        this.name=name;
        this.age=age;
    }
    //定义 子类的公共的方法 通过原型对象去实现
    // 构造函数.prototype.成员属性/方法=值/function(){}
    Person.prototype.eat=function () {
        console.log("喜欢吃大米饭")
    }
    var ming=new Person("小明",18)
    var ak=new Person("阿珂",18)
    console.dir(ming)
    console.dir(ak)
    console.log(ming.eat==ak.eat)//true

    console.dir(Person)
    //  在 ak对象的 __proto__下 有eat方法 不是直接挂载在ak的
    ak.eat()//ok
    ak.__proto__.eat();
    //是同一个人
    console.log(ak.eat == ak.__proto__.eat);//true
    console.log(ak.__proto__.eat==Person.prototype.eat)//true

</script>

```

 通过分析发现如下的结构

 	构造函数中的原型对象定义的方法==实例化对象._proto_的方法	

​	 实例化对象._proto_中的方法  可以直接省略_proto_       

![1599550443933](assets/1599550443933.png)

##### constructor构造属性

​	1.任何函数 都有一个prototype属性 该属性是一个对象

​	2.构造函数中的prototype对象默认都有一个constructor构造属性指向了对象的构造函数

​	3.通过构造函数创建对象 内部包含了一个指向构造函数的prototype原型对象的"指针",

​		"__proto_ _"

​	4.每一个实例化对象中的proto中同时都有一个constructor构造函数

​            同时都是指向的是当前实例化对象的构造函数



```js
<script>
    // 构造函数  Pseson
    function Person(name,age) {
        // this.name: 当前实例化对象的属性名
        //  name : 构造函数传进来的实参
        this.name=name;
        this.age=age;
    }
    // 原型的方法
    Person.prototype.hello=function () {
        console.log("hello")
    }
    var ming=new Person("小明",18)
    var ak=new Person("阿珂",18)
    //普通的函数
    function f() {
        console.log("我是一个普通的函数")
    }
    //1.控制台查看 无论是普通函数还是构造函数 都有一个prototype对象
    console.dir(f); //普通
    console.dir(Person); //构造函数


    //2.构造属性 指向的是当前对象的构造函数
    console.dir(ming.constructor); // 输出的是Person构造函数
    // 实例化对象的构造属性是同一个人=》 当前对象的构造函数
    console.log(ming.constructor==ak.constructor); // true
    //当前对象的构造属性    它就是构造函数
    console.log(ming.constructor==Person)// true
    console.log(ak.constructor==Person)// true

    //构造函数Person本身是没有constructor  原型(prototype对象)中才有
    console.dir(ming)
    console.log(ming.constructor==Person.constructor)//false
    //自己没有 原型才有
    console.log(ming.constructor==Person.prototype.constructor)//true
    //当前对象可以省略__proto__
    console.log(ming.__proto__.constructor==ming.constructor)//true

</script>
```

##### 原型链

​	定义:由多级对象逐级继承的关系的链式结构

​		 保留了所有层级中对象的属性和方法。

​	规则:  指定了属性和方法的调用顺序(从当前对象触发出发挨个往构造函数级原型中找)

​	  vs作用域链的原理是一致的	

```js
<script>
    // 构造函数  Pseson
    function Person(name,age,sex) {
        // this.name: 当前实例化对象的属性名
        //  name : 构造函数传进来的实参
        this.name=name;
        this.age=age;
       // this.sex=sex;
        this.eat=function () {
            console.log("我要减肥，不吃饭 只喝水")
        }
    }
    // 原型中 设置了和构造函数中一样的方法/属性
    Person.prototype.sex="人妖";
    Person.prototype.eat=function () {
        console.log("我喜欢吃大米饭")
    }
    var ming=new Person("小明",18,"男")
    console.log(ming);
    ming.eat()
    //如果构造中没有声明则去构造的原型中找调用可以直接调用__proto__省略可以
    console.log(ming.sex); 
    /*   原型链
    *  总结:  实力对象中的属性和方法的使用 优先级问题
    *    首先在构造函数中寻找，如果构造中没有 则去原型中找
    *    和作用域链很相似
    *
    * */
</script>
```

作业:

// indexOOf(a) 查下标 如果没有返回-1   

​     只有一个a默认从下标0开始查 indexOf(a,b) b:从b下标开始查



### day03

#### 原型的简写及注意事项

  需要手动添加constructor属性
   constructor:构造函数, 

```js
<script>
    //构造函数
   function Person(name,age) {
       this.name=name;
       this.age=age;     
   }
   // 默认是在__proto__自动有一个constructor属性指向的是当前实例化对象的构造方法
 /*  Person.prototype.eat=function () {
       console.log("喜欢吃红烧肉");
   }*/
   //通过字面量对象的形式添加 原型的属性和方法(因为prototype是一个对象)
   // console.dir(Person);
    Person.prototype={
       //需要手动添加constructor属性
       constructor:Person, //
       sex:"男",
       eat:function () {
           console.log("喜欢吃红烧肉");
       },
       sayHi:function () {
           console.log("hello");
       }
    }
    var ming=new Person("小明",12);
    console.dir(ming);
  ming.eat()
</script>
```

#####  特点: 

   原型中的方法 是可以相互被调用的。

```js
<script>
    //构造函数
    function Person(name,age) {
        this.name=name;
        this.age=age;
        this.eat=function () {
            console.log("红烧肉")
        }
    }
    var ming=new Person("小明",12)
    ming.eat()
    // 添加原型中  2个方法
    Person.prototype.sayHi=function () {
        console.log("hello")
        this.iner();
    }
    Person.prototype.iner=function () {
        console.log("大家好")
    }
    var hua=new Person("小花",13);
    hua.sayHi()//

    //结论:   原型中的方法 是可以相互被调用的。
</script>
```

#### 自有属性和共有属性

  自有属性:  实例化对象自己保存的属性

​			1.构造函数中生成的属性 2.后面通过.添加的属性

  共有属性: 直接添加在原型中的属性，所有的子类都可以直接使用的属性

​	xxx.属性 去获取

  结论: 修改自有属性只会影响当前的对象，而修改共有属性则会影响所有的对象

```js
<script>
    //学生类的构造函数
    function Student(name,age) {
        this.name=name;
        this.age=age;
    }
    Student.prototype.study=function () {
        console.log("热爱学习 天天向上");
    }
    Student.prototype.className="高一一班";
    var ming=new Student("小明",16)
    var hua=new Student("小花",16)
    console.dir(ming)
    console.dir(hua)
    // 过了一年   修改年纪
    ming.age++; // 修改的是ming对象的私有的属性
    console.log(ming.age);//17
    console.log(hua.age); //16
       //在当前的对象 中直接添加了一个className属性
    ming.className="高三一班";
    console.log(ming); // 有className属性
    console.log(hua);  // 没有className属性的

    // 修改公用的属性  所有的对象都会都会变
    Student.prototype.className="高二一班";
    console.log(hua.className) //  高二一班
    console.log(ming.className) //  高二一班


</script>
```

#### 修改原型的指向问题

​       原型的指向是可以被修改的   可以换爹

​	通过构造函数的prototype对象指向新的 构造函数_proto__指向也会跟着改变

​        实例化对象的__proto__指向的是该对象所在的构造函数的原型对象

```js
<script>
    //构造函数1
    function Person(name) {
        this.name=name;
    }
    Person.prototype.money=function () {
        console.log("打工赚点辛苦钱");
    }
    //2  构造函数
    function Kuang() {
        this.car=function () {
            console.log("家里有兰博基尼18辆")
        }
    }
    Kuang.prototype.money=function () {
        console.log("家里有矿,躺着就好")
    }
    // 实例化对象
    var ming = new Person("小明");
    ming.money()// 辛苦钱
    console.log(ming);
    // 修改原型的指向问题
    Person.prototype=new Kuang();//构造函数的原型指向了Kuang的构造函数
    console.dir(Person)
    var  hua=new Person("小花");
    hua.money()  //家里有矿,躺着就好
    hua.car()  // 兰博基尼随便开
    console.log(hua) // __proto__ 指向也会修改为 Kuang
  /*
  *  结论:  原型的指向是可以被修改的   可以换爹
  *       通过构造函数的prototype对象指向新的 构造函数
  *        __proto__指向也会跟着改变
  *      实例化对象的__proto__指向的是该对象所在的构造函数的原型对象
  * */

</script>
```

![1599621473507](assets/1599621473507.png)

#### 寻找根源

​	结论: 万物皆对象

```js
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<div id="d1"></div>
<script>
    var d1=document.getElementById("d1");
    console.dir(d1);

    /*  一级一级的往上找 
    *  d1.__proto__=>HTMLDivElement=> HTMLElement=>Element
    *  =>Node =>EventTarget=>Object(最终的)
    *
    *  万物皆对象。
    *
    * */
</script>
</body>

</html>
```

### day04=============================================

#### 2.借用构造函数继承 	 

​     为了实现数据的共享  代码的重用 才去使用的继承 通过改变原型的指向的方法实现的继承
   1、**缺点**:

​	 因为修改了原型的指向实现的继承时 直接初始化了 属性
​         导致继承过来的属性都是一样的("小明",88)。 要想使用新的值还得
​         重新去定义
   2、**解决**:
​        继承的时候 不再直接改变原型的指向，直接调用父类的构造函数
​           通过父类去实现->借助构造函数
  3、**语法**:   构造函数.call(当前对象,属性1,属性2,属...)
​          这样就可以解决属性的继承问题

  4、**但是**:  直接解决属性的继承和构造函数中方法的继承 

​	    构造函数中的原型中的属性和方法是无法使用的

​             (.call只是临时借调。原型中的方法必须是亲生的才可以使用)

```js
<script>
   /* // 人的构造
    function Person(name,age) {
        this.name=name;
        this.age=age;
    }
    // 人的构造原型
    Person.prototype.sayHi=function () {
        console.log("大家好");
    }
    // 学生类的构造
    function Student(score) {
        this.score=score
    }
    Student.prototype=new Person("小明",18)
    var ming= new Student(88);//实例化对象
    console.log(ming.name,ming.age,ming.score); //小明 18 88
    var ak=new Student(68);
    // 问题: name 和age还是  小明 还是 18
    console.log(ak.name,ak.age,ak.score); //小明 18 68
     ak.name="阿珂";
    ak.age=17;
    console.log(ak)*/
   /*
   *   为了实现数据的共享  代码的重用 才去使用的继承 通过改变原型的执向
   *       的方法实现的继承
   *   缺点: 因为修改了原型的指向实现的继承时 直接初始化了 属性
   *         导致继承过来的属性都是一样的("小明",88)。 要想使用新的值还得
   *         重新去定义
   *   解决:
   *        继承的时候 不再直接改变原型的指向，直接调用父类的构造函数
   *           通过父类去实现->借助构造函数
   *   语法:   构造函数.call(当前对象,属性1,属性2,属...)
   *          这样就可以解决属性的继承问题

   * */
   // 人的构造
   function Person(name,age,money) {
       this.name=name;
       this.age=age;
       this.money=money;
       this.car=function () {
           console.log("有一辆法拉利")
       }
   }
   // 构造的原型
   Person.prototype.house=function () {
       console.log("有500亩的大别墅")
   }
   //学生的构造
    function  Student(name,age,score,money) {
        //在构造函数中 借用父类的属性
        Person.call(this,name,age,money); // 认个干爹

        // 学生类自己的
        this.score=score;
    }
    // 实例化的是学生类的构造
    var ming=new Student("小明",16,80,2000);
   console.log(ming);
   var  ak=new Student("阿珂",15,88,1500);
   console.log(ak);
   ak.car();// ok  可以直接借用 临时的爹的构造中的方法

   ak.house();// 报错      不可以使用临时的爹的构造中 原型的方法
             // .call只是临时借用 不是永久的 无法直接使用
</script>
```

#### 3.组合继承

​      1.、借用构造函数(重用构造函数的属性和方法)

​	2、通当前构造函数的原型的指向修改，指向的是构造函数的实例化对象，不需要在家属性了

​		就可以使用构造函数的原型中的属性和方法了。

```js
<script>
    // 实现通过 原型继承+借用构造函数
    /* 原因:
    *       原型继承  可以直接使用父类的 属性(实例化对象就写死了) 和方法
    *                   可以使用父类的构造函数中的原型的属性和方法
    *
    *       借用构造:  可以使用借调的构造函数中的属性不再写死，
    *                  但是没有办法使用构造函数原型中的 属性和方法
    *
    * */
    // 人的构造
    function Person(name,age,money) {
        this.name=name;
        this.age=age;
        this.money=money;
        this.car=function () {
            console.log("有一辆法拉利")
        }
    }
    // 构造的原型
    Person.prototype.house=function () {
        console.log("有500亩的大别墅")
    }
    // 步骤1
    //  还是可以先 借用构造
    function Student(name,age,score,money) {
        Person.call(this,name,age,money);

        //自己的属性
        this.score=score
    }
    //步骤2   还是指定 原型的指向来继承
    Student.prototype=new Person();// 不需要传参数,已经被.call借去了.
    Student.prototype.eat=function () {
        console.log("喜欢吃西红柿鸡蛋面");
    }
    var ming=new Student("小明",18,68,2000);
    console.log(ming);
    ming.car();// ok
    ming.house(); // ok  __proto-> Person   => _proto__ Person的原型
    ming.eat() //ok


    var ak=new Student("阿珂",15,87,5000)
    console.log(ak);
</script>
```

#### 自定义继承

 用处: 如果说现有的实例化对象中的原型不好用， 可以通过直接更改一个"_proto___"指向(亲爹不好用，直接换)

 语法:

​	1.直接换一个对象的爹

​	  因为每个对象的proto指向的是自己的上一级(生自己的构造函数),只需要修改proto的指向就可以让新的对象成为自己的上一级。

```js
 对象.__proto__=新的对象(上一级)
 会存在兼容问题
 可以使用
 Object.setPrototypeOf(子对象,父对象);
```

```js
<script>
    // 学生的构造
    function Student(name,age) {
        this.name=name;
        this.age=age;
    }
    var ming=new Student("小明",18)
    var ak=new Student("阿珂",18)
    var laoma={  //一个对象
        money:"10000个亿",
        car:"18辆宝马"
    }
    // 自定义继承
    // ak.__proto__=laoma;   考虑兼容性
      Object.setPrototypeOf(ak,laoma); // 兼容的写法
   console.log(ak)
    console.log(ak.car);
    // 这里 ming是对象
   // 这里错误的  原型只能给构造加。
  /*     ming.prototype.money=laoma;
      console.log(ming.money,ming.car)*/
</script>
```

   2.让所有的实例化对象都修改

​	原理: 原型修改

​		 原型继承得在实例化对象之前换，如果已经创建了对象了 再去修改执向是无效的。

```js
<script>
    // 学生的构造
    function Student(name,age) {
        this.name=name;
        this.age=age;
    }
    var laoma={  //一个对象
        money:"10000个亿",
        car:"18辆宝马"
    }
    //直接修改 原型的指向   让所有的Student构造的实例化对象都具备
     //  对象中的属性
    Student.prototype=laoma;

    var ming=new Student("小明",18);
    var ak=new Student("阿珂",18);
    console.log(ming);
</script>
```

```
  prototype和__proto__的区别
  向原型对象中添加共有属性和方法时的操作用 构造函数.prototype.xxx
  子对象去查看或者使用父类的属性和方法时的一个指向问题 子对象.__proto__.父类
  __proto__使用的时候是可以省略的。		
  
```

#### 多态

  父类的方法和属性不好用，或者是压根就没有， 自己去写。

  重写(override)是多态的表现之一。

  自定义方法也是多态的表现之一。

 **重写**: 只要子对象中觉得父对象中的继承的属性不好用，可以自己内部再创建一个相同的名字的成员。用来覆盖父类的成员。

 使用:  去定义个父类中不适合自己的 相同名的方法。 

```js
<script>
     function Person(name,age) {
         this.name=name;
         this.age=age;

     }
     Person.prototype.house="500亩豪宅";
     Person.prototype.sayHi=function () {
         console.log("人可以说话")
     }

     var ming =new Person("小明",18);
    console.dir(ming);
    console.dir(Person)
     // 默认的 toString()没有 办法转对象的
    console.log(ming.toString()); // [object Object]
     // {name:"小明",age:"18"}  只要属性
     // 重写一个 toString()
    Person.prototype.toString=function () {
        var str="{";
        for (var key  in this) {
             //判断如果是function 忽略
            if(typeof (this[key])!="function"){
                str+=key+":"+this[key]+",";
            }
        }
        str+="}";
        return  str;
    }
     console.log(ming.toString());
</script>
```

### ES5

  ECMAScript第五个版本

#### 1.严格模式 "use strict"

#####  	1、 禁止给未声明的变量赋值

​		旧的js中 没有声明直接赋值  自动创建--全局的污染

​		严格模式中:  会报错  xxx is not defined

##### 	2.执行不成功 区别

​	    严格模式下，如果执行不成功(静默)就会直接升级为报错。

#####         3.普通的函数的调用中，默认的this

​		旧的:  this指的是window 

​		严格下: undefined 

```js
<script>
  // "use strict"

  /*a=12; //没有声明直接使用
     console.log(a);  // 报错*/
  
    function  Student(name,age) {
        console.log(this);//默认这里的this是window 严格模式下是undefined
        this.name=name;
        this.age=age;
    }
    var ming=new Student("小明",16)
    console.log(ming)
    var ak=Student("阿珂",18)

     // 严格模式下直接报错
   //转换为  this=>undefined

     // undefined.name="阿珂";  直接报错的
   //console.log(ak);
</script>
```

#### 保护对象

​	原因:  旧的js中 对象没有保护能力的。可以随意的改变属性和方法。

​	新的: 防止对 对象中的属性进行违规操作，污染修改，恶意的破坏。

保护:

##### 	1.保护对象的属性分类

​		a数据属性: 属性值直接保存在属性中

​		b访问器属性:  不实际的存储属性值， 只提供对其他数据属性的保护(保镖)

##### 	2.属性属性的保护

​	    原理: 每个属性都提供了 4个内部特性，可以通过这4个内部特性用来操作是否可以修改当前对象的属性。

   通过这个方法获取4个内部特性

Object.getOwnPropertyDescriptor(obj,"uname"); //获取一个属性的
Object.getOwnPropertyDescriptors(obj,"uname"); //加s获取一个对象所有的属性的
四个特性分别是:

​     **configurable**: true   //设置是否可以被删除 一旦为false 不可逆
​     **enumerable**: true     //设置是否可以被 for in遍历 可以通过.形式访问
​     **value**: "隔壁老徐"   //属性的值
​     **writable**: true     //设置是否可以被修改

​	注意: 修改这些特性需要用指定的方法修改不能直接使用.的形式进行操作。否则无效。

​	Object.defineProperty（obj,"属性",{特性的设置}）

```js
<script>
    var obj={
        uname:"隔壁老徐",
        sex:"男",
        salary:"2500",

    }
    console.log(obj)
    //查看 默认的4个特性(还是属性 开关属性)
    var uname=Object.getOwnPropertyDescriptors(obj,"uname");
    console.dir(uname);
    /*
    *    configurable: true   //设置是否可以被删除 一旦为false 不可逆
         enumerable: true     //设置是否可以被 for in遍历 可以通过.形式访问
         value: "隔壁老徐"   //属性的值
         writable: true     //设置是否可以被修改
    *
    * */
    // 设置完之后  数据还是可以修改的
     // uname.uname.writable=false;
    // 可以通过 这个方法去设置 属性的特性
    Object.defineProperty(obj,"uname",{
        writable:false, // 不可以被修改
        configurable:false,
    })
    obj.uname="隔壁老王";
    console.log(obj);
</script>
```

测试多个属性的不同的4个特性

```js
<script>
    "use strict"
    var obj={
        eid:"01",
        ename:"隔壁老王",
        salary:"2500",
    }
    console.log(obj)
    //查看 默认的4个特性(还是属性 开关属性)
    var uname=Object.getOwnPropertyDescriptors(obj,"eid");
    console.dir(uname);
    /*
    *    configurable: true   //设置是否可以被删除 一旦为false 不可逆
         enumerable: true     //设置是否可以被 for in遍历 可以通过.形式访问
         value: "隔壁老徐"   //属性的值
         writable: true     //设置是否可以被修改
    *
    * */
    //eid  编号  设置只读
    Object.defineProperty(obj,"eid",{
        writable:false,//不能修改
        configurable:false, //不能删除
    })
    // ename 设置 进制删除
    Object.defineProperty(obj,"ename",{
        configurable:false, //不能删除
    })
    // salary 禁止遍历
    Object.defineProperty(obj,"salary",{
        enumerable: false,//不能遍历
    })
    //测试 eid 的 删除特性重新去打开
/*    Object.defineProperty(obj,"eid",{
        writable:true,//不能修改
        configurable:true, //不能删除
    })
    // 会报错  Uncaught TypeError: Cannot redefine property: eid
   // at Function.defineProperty*/
    //测试修改
    obj.eid="02";   // 加了 "use strict"  才会报错 
    console.log(obj);
    //测试删除
    delete obj.ename;
    console.log(obj);

    //测试遍历  salary 属性遍历不出来
    for (var key in obj){
        console.log(`${key}:${obj[key]}`)
    }
    // 虽然不能通过for in遍历得到
    console.log(obj.salary); //是可以通过.属性名获取的。


</script>
```

简写 核心部分  

  方法名多一个s  采取的是对象的形式作为参数传递

```js
//  多个属性中 特性的设置 简写
Object.defineProperties(obj,{
    //设置不同的属性中 不同的特性
    eid:{
        writable:false,
        configurable:false,
    },
    ename:{
        configurable:false,
    },
    salary:{
        enumerable:false,
        configurable:false,
    },
})
```

####   通过访问器属性来进行保护数据属性	

​	属性的值进行自定义的规则设置: 

​	 ex: 设置属性值的取值范围，年龄大小  工资多少

​	特点: 自己不会报存数据，作为对数据的保护的中间人。

​	 步骤1: 找替身(子弹飞)

​		   ex:  eage  -> _eage(真实的身份  隐藏起来 躲在暗处)

​			 调用者去修改eage如果数据符合要求 才把eage中的数据传给_eage

​		 注意: eage只是我们用于测试的属性名  可以是任何的名 	



```js
<script>
    var obj={
        ename:"隔壁老王",
    }
    Object.defineProperties(obj,{
        //自定义一个属性 真身 是你需要保护的属性
        _eage:{  //年龄   保护年龄的取值范围
            value:25,
            writable:true,
            enumerable:false,// 半隐藏状态 不被遍历
            configurable:false, //不能删除
        },
        eage:{// 替身
            //自带2个方法 一个是get()  一个是set()
            //获取 真身是值
            get:function () {
                console.log(`自动调用 eage的get方法 去到_eage中 返回${this._eage}`)
                return this._eage; //返回真身的值
            },
            //修改真身的值
            set:function (newValue) {
                console.log(`自动调用 eage的set方法 把新接收的newValue设置回${this._eage}中`)
                //写逻辑
                if(newValue<65&&newValue>18){ //条件满足
                    console.log("符合要求 传给真身")
                    this._eage=newValue
                }else{
                    console.log("不满足条件");
                    throw Error("年龄必须在18-65之间")
                }
            }

        }
    })
    obj.eage=35;
    console.log(obj)
</script>
```

####  对象的结构的保护

#####    1、防拓展

​     Object.preventExtensions(obj)  

​	不能够增加新的属性和方法

 

```js
<script>
    "use strict"
    var obj={
        ename:"隔壁老徐"
    }
    //  禁止拓展   不允许添加新的属性和方法
    Object.preventExtensions(obj)
    obj.eid="12";
    console.log(obj)
</script>
```

#####  2.密封性

​	 Object.seal(obj);  // 禁止拓展的同时 也不能删除

  注意: 是可以修改属性的值的

```js
<script>
    "use strict"
    var obj={
        ename:"隔壁老徐"
    }
    //   禁止删除 现有的属性 并且 也禁止拓展
     Object.seal(obj);

  //  obj.age=12
 //   delete  obj.ename;

    console.log(obj)
</script>
```

##### 3.冻结

Object.freeze(obj);

   在兼具 密封 不能拓展 不能删除的基础上  禁止修改

```
<script>
    "use strict"
    var obj={
        ename:"隔壁老徐"
    }
    // 在兼具 密封 不能拓展 不能删除的基础上  禁止修改
  Object.freeze(obj);
    obj.ename="隔壁老王";//不能修改

</script>
```

### day05==========================================

#### Object.create()

   定义: 创建一个子对象  继承指定的父对象

   用处: 如果说没有构造函数的时候,也想创建子对象则可以使用Object.create()

   语法:   创建一个空的新的子对象 用于继承父对象

​		var  子对象= Object.create(父对象)

​	子对象是一个空的   但是父对象的成员属性和方法都可以用了

```js
<script>
    var father={
        car:"18辆法拉第",
        money:"1000亿",
        eat:function () {
            console.log("西红柿鸡蛋面")
        }
    }
    //通过 创建   自己是空的
   /* var gblx=Object.create(father);
    console.log(gblx);// 父对象中的属性和方法 就可以使用了
    console.log(gblx.car);
    gblx.eat()*/

   //创建的同时 自定义自己的属性
    var gblw=Object.create(father,{
        phone:{
            value:"iphone12Pro",
            writable:true,  //能修改
            enumerable:true, //能遍历
            configurable:false, //不能删除
        },
        house:{
            value:"500亩的豪宅",
            writable:true,  //能修改
            enumerable:true, //能遍历
            configurable:false, //不能删除
        }
    })

    console.log(gblw);
    gblw.eat()
    console.log(gblw.house);

    //获取 属性四大特性
    var tes=Object.getOwnPropertyDescriptors(gblw)
    console.log(tes);
</script>
```

#### this的默认指向问题

##### 1.问题:  开发中 我们认为的this 不是自己想要的那个this

```js
<div id="d1">小明</div>
<script>
    function money(base,bonus) {
        var money=base+bonus;
        console.log(this);//
        //下面结果出不来 ！！！  默认指向的this是window
        console.log(this.innerHTML+"一个月的工资总和是"+money);
    }
    d1.onclick=function () {
        console.log(this); //div
        money(2500,25000)
    }
</script>
```

#####  2.分析不同情况下的指向

```js
		普通函数中的   this    =>window
        对象中的      this    =>当前对象(.前的对象)
        定时器的函数   this    => window
        回调函数      this        =>window
        构造函数      this       =>当前对象(.前的对象)  
        构造原型      this       =>当前对象(.前的对象)
```

```js
<script>
    /*
    *    普通函数中的   this    =>window
    *    对象中的       this    =>当前对象(.前的对象)
    *    定时器的函数       this    => window
    *    回调函数      this        =>window
    *    构造函数      this       =>当前对象(.前的对象)
    *    构造原型      this       =>当前对象(.前的对象)
    *
    *
    * */
    //1. 普通函数
    function f() {
        console.log(this);// window
    }
    f()
    //2对象中的this
    var obj={
        name:"小明",
        eat:function () {
            console.log(this) //obj
        }
    }
    obj.eat();//
    // 3定时器中的回调函数 this
    setInterval(function () {
        console.log(this); //window
    },1000)

    // 4构造函数 中的this
    function Person(name) {
        this.name=name;
        this.eat=function () {
            console.log(this);//
        }
    }
    Person.prototype.sayHi=function () {
        console.log(this)
    }
    var ming=new Person("小明");
    ming.eat()// ming 对象
    ming.sayHi()// ming对象
</script>
```

##### 3修改this的指向

​	借助于 .call/.apply 去改变this的指向

​	语法:

​	      .call(指定的对象,参数1,参数2，参数3...)

​	      .apply(指定的对象,[参数1,参数2,参数3...])	

​          解释:  指定的对象 其实就是希望的那个this, 

​                      如果设置为null/undefined则表示不修改this的指向

​           区别:   xxx .call 参数必须是一个个的参数列表

​			xxx.apply 参数必须是数组

​	 下面案例总结: 

​	**.call /.apply 调用方法 只是借调(认干爹)  不会永久性的绑定this** 

```js
<script>
    function f(x,y) {
        console.log(x+y);
        console.log(this);//this
        return this.name;
    }
    //直接调用
   //  var f1=f(1,2) // this指的是window
    //通过.call调用
    //var  f1=f.call(null,1,2) // 表示不会指定this  默认情况
    // 修改this
      var obj={
        name:"小明",
      }
     var f1=f.call(obj,1,2) // this=> 当前的obj对象
     console.log(f1); // 小明
        // 参数必须是 数组
      var f2=f.apply(obj,[1,2]);
    console.log(f2);


    // 测试  this是谁
    var f3=f(1,2)  //此时 this=> window
    console.log(f3);
 
    //结论:   .call /.apply 调用方法 只是借调(认干爹)
    
</script>
```

  需求:  永久性的绑定this指定的对象??

#### .bind

   一旦通过.bind绑定了this  就无法再改变了，并且无法再被.call和.apply去借调修改了。

  一般来说 .call/.apply是通过借调实现  会恢复

 .bind是通过生成一个新的函数(必须要有接管)才能使用

语法:

​      var  新的函数名=xxx.bind(指定的this对象,参数,参数)

原理: 

​	 创建一个和原函数一模一样的新的函数的副本，将新的函数中的this永久性的绑定为指定的对象。  所有调用新的函数时， 不会再重复的传入替换this的对象。 this会自动就是提前绑定好的指定的对象。

应用: 如果 回调函数中this不是自己想要的  则可以通过.bind去永久绑定指定的对象。

​	  	  

```js
<script>
    function f(x,y) {
        console.log(x+y)
        console.log("我今年"+this.age);// 默认是window
    }
    function Person(age) {
        this.age=age;
    }
    Person.prototype.eat=function () {
        console.log("我喜欢吃西红柿")
    }

    var ming=new Person(18)
    var hua=new Person(12)
    // .call是临时的
/*    f.call(hua,1,2);
    f(1,2)//又回去了*/
  // 使用.bind 永久绑定
    var ff=f.bind(ming,10,20)
/*    通过bind 绑定了ming对象 为this  生成一个新的函数
*
*
* */
    // console.log(typeof  ff); //function

    ff();// 18
    ff();// 18  还是不会变
    ff.call(hua,15,20); // 无效 直接相当于 ff()
    ff.apply(hua,[15,20]); // 无效 直接相当于 ff()
</script>
```

问题:

​        不应该每次调用ff() 方法时  数据 都是 30 所有应该如下 

​	 先绑定永久的this  再去调用ff()方法分时候传参过去 

```js
<script>
    function f(x,y) {
        console.log(x+y)
        console.log("我今年"+this.age);// 默认是window
    }
    function Person(age) {
        this.age=age;
    }
    Person.prototype.eat=function () {
        console.log("我喜欢吃西红柿")
    }

    var ming=new Person(18)
    var hua=new Person(12)
    // .call是临时的
/*    f.call(hua,1,2);
    f(1,2)//又回去了*/


   // 先永久绑定 ming
    var ff=f.bind(ming)
   //再调用的时候 再传参
    ff(1,2)
    ff(12,22)
    
    

</script>
```

### 数组新的API

##### 1、 arr.every（）

​	用于判断数组中所有的元素是否都符合条件

  var bool= arr.every(function (ele,i,arr) {

 	 return    判断条件

 })

原理:   自带遍历 for循环

​	     遍历每一个元素 就会自动的调用回调函数  并且每次都会传入3个参数

​		ele:  当前正在遍历的数组的子元素值

​	            i:    当前遍历数组子元素对应的下标

​		arr: 当前的数组对象

​	    返回一个判断结果

​	只要一个元素判断为false 整个就退出循环，直接返回false  只有所有的元素头符合条件才为true

```js
<script>
    var arr=[1,4,6,8];
    //需要接收
   var bool= arr.every(function (ele,i,arr) {
        console.log(this);//  window
        console.log(
            ele, // 2    数组子元素
            i,    //0     下标
            arr   //[2,4,6,8]  整个数组
        )

        return  arr[i]%2==0?true:false;
    })
    console.log(bool); //false 第一个为false 后面就不执行了。
    // 判断数组是不是 都是数字
    var arr1=["hello",true,123];
    var arr2=[1,2,23,4];
    
    
</script>
```

##### 2、forEach遍历

###### **直接修改原数组 没有返回值**

arr.forEach(function(ele,i,arr){

​	自动遍历了 无需手动遍历

})

​	forEach回调函数**没有返回值** return,可以直接修改原数组。

​	注意: 在进行子元素数据修改的时候  要通过arr[i]修改 

​		ele参数只是arr[i]赋值的一个副本 修改ele是**无效的**。

```js
  var arr=["吃","喝","玩","乐"];
   /* for (var i=0;i<arr.length;i++){
        console.log("我喜欢"+arr[i]);
    }*/
 /*  for (var key in arr){
       console.log("我喜欢"+arr[key]);
   }*/

    arr.forEach(function (ele,i,arr) {
        // 不用你写 自动写好的
        // for (var i=0;i<arr.length;i++){  // 可以省略了
           console.log("我喜欢"+ele)
       //  console.log("我喜欢"+arr[i])
        //}
    })
    // 测试有没有返回值
    var arr1=[1,2,3,4,5]
    var as=arr1.forEach(function (ele,i,arr) {
            var all=ele*ele;
            return all;
    })
    console.log(as)// undefined  结论没有返回值

    var arr2=[1,2,3,4,5]
    var as=arr2.forEach(function (ele,i,arr) {
          // ele*=ele;  无效     ele=arr[i]  ele是原数组中修改的副本
           arr[i]*=arr[i] //这才是真身
    })
    console.log(arr2); //[1,4,9,16,25]
```

for   vs    forEach

|         | 数组 | 类数组 | 字符串 | 对象/关联数组 |
| ------- | ---- | ------ | ------ | ------------- |
| for     | ok   | ok     | ok     | no            |
| for in  | ok   | ok     | ok     | ok            |
| forEach | ok   | ok     | no     | no            |

##### 3、arr.map()

 遍历数组 生成新的数组

 如果不希望修改原数组，而是修改完生成新的数组时使用

语法:  

​	var newArr=arr.map(function(ele,i,arr){

​		return   新的元素值

})

原理 和之前的回调函数类似:

​	A:自带for循环、每遍历到一个元素就调用一次回调函数。

​	B:传入的3个参数和上面一致

​	C:在回调函数内修改的数据会按原有的顺序保存到新的数组相同的位置中。

​	D:返回新数组，原数组不变。

```js
<ul id="ul">
  <!--  <li>12</li>
    <li>23</li>-->
</ul>
<script>
    var arr=[12,23,34,45,56]
    var newArr=arr.map(function (ele,i,arr) {
        //return  ele*=2  // 2种方式 都可以
        // 原理 依然是for循环
        return  arr[i]*=2
    })
    console.log(newArr);

    var newArr1=arr.map(function (ele,i,arr) {
        // 返回带标签的 li
        return  `<li>${ele}</li>`;
    })
    console.log(newArr1);//数组

    var html=newArr1.join("");
    console.log(html);
    ul.innerHTML=html;

</script>
```

##### filter()  过滤

​	复制一份新的数组 包含原数组中符合条件的值	

​	语法:

​	var newArr=arr.filter(function(ele,i,arr){

​	// 返回的是一个bool值  如果是true则会自动push到newArr数组中

​	 return   判断条件

})

```js
<script>
    // 将数组按照指定的条件 继续筛选过滤
    var arr=[1,2,3,4,5]
    var newArr=arr.filter(function (ele,i,arr) {
        
        return  ele%2==0; //如果为true就会push到newArr中
    })
    console.log(newArr);//新数组
    console.log(arr) //原数组
</script>
```

##### reduce统计

​	对数组中所有的元素的内容进行一个统计 返回一个最终的结果var

var newArr=arr.reduce(function(ele,next){

​	return   计算

}，起始值)  //可以不给默认是0		

```js
<script>
    // 统计
    var arr=[1,2,3,4,5];
    var sum=arr.reduce(function (ele,next) {
        // ele :默认从下标0开始计数  每次计算之后都会进行覆盖
        // next: 下一个要计算的数组元素的值。
        console.log(ele,next)//当前元素和下一个元素。

        return  ele+next;
    })
    console.log(sum); //15

    var arr2=[6,7,8,9,10]
    sum=arr2.reduce(function (ele,next) {
        return ele+next;
    },sum);// 起始的值不给默认是0  此时从 sum=15开始统计。
    console.log(sum);// 55
</script>
```

### ES6

​    在原有的功能上 重点简化语法，并且减少了 原有的坑。

#### 1.声明变量   let

​	专门用来 声明变量的关键词 

​         原因:  var声明的变量 有缺陷  所以用let代替var

   1.声明提前    程序执行顺序很混乱

2. 没有**块级作用域**,导致块内的变量和块级之外的变量的相互干扰。

   ​    块级作用域:   除了function和对象中 意外其他的{} 都算一个模块

   ​      比如 if(){}   for(){}  while(){}... 都算跨级作用域

   ​    在旧的js中 以上这些都不是块级作用域

   ​	最开始设计 目的:  里面的内容 外面也可以使用	

   ​	 弊端:  没有块级的概念，因为随意的更改 。容易影响到其他人

  let声明 

​        1、 阻止了 声明提前

​	2、 让除了function和{}之外的所有的{} 中 都变成 了块级作用域

​	3、相同作用域内，禁止反复的使用let声明同名的变量 

​               相同作用域内，在let之前 禁止提前使用该变量。

```js
<script>
    //console.log(a);//undefined  而使用let声明 会直接报错
    //var a=10;
      let a=10;

      for (let i=0,sum=0;i<10;i++){
          let num=10;
          sum+=i;
      }
     // console.log(sum) //报错
      //console.log(num) // 报错

     /* let b=10;
      let b=20;
      console.log(b) //还是报错*/
     let c=10; //全局变量
     function f() {
         let c=12
         c+=1;  //可以使用
      console.log(c)
     }
     f()
    console.log(c);
    
</script>
```

### day06

#### 箭头函数

   定义: 除了对象中的方法之外(对象直接定义的方法是不能用的否则this指向 了window)，

​              其他都可以用箭头函数来简化。

   语法:

​	1、 去掉function  在()和{}加=>        ()=>{}	

​	2、 如果只有一个形参，可以省略() 如果没有形参 则必须要加()

​        3、如果函数体只有一句话如果省略了{} 需要删除结尾的分号。 如果只有一句话

​			return xxxx;   则需要删除 return 关键词

```js
<script>
    //
    var arr=[11,2,13,4,15]
    //排序
    // 去掉 function 添加=>
    arr.sort((a,b)=> a-b)
    console.log(arr);

    // 定时器的写法
    setInterval( ()=> {
        console.log(123)
        console.log(456)
    },1000)

    //带参数
    arr.forEach( (ele,i,arr)=> {
        arr[i]=ele*2;
    })
    console.log(arr);
</script>
```

##### 2.有关this执向问题

​	   旧的: function(){}.bind(this)

​	   es6:  ()=>{}    箭头函数里面的this和外面的this是一致的 不需要做任何的操作

​	  注意: 今后如果想要内外一致就直接使用箭头函数 不需要bind 如果不需要一致则不要用箭头函数

  注意:  对象中方法也是可以省略:function的（省略function不代表就是箭头函数）

```js
<script>
    //this => 全局的this 是window
    var xu={
        name:"隔壁老徐",
        like:["吃","喝","玩","乐"],
        // es6中 可以省略 function
        sayHi() {
            // this =>xu
           this.like.forEach(
               function (ele) {
               //console.log(ele)
               // 默认的this 指的是window
               console.log(this.name+"喜欢"+ele)
  // 把外围的this=>实例化对象xu 绑定给回调函数中的this(window)
            }.bind(this)
           )
        }
    }
    xu.sayHi()
 // es6中  箭头函数的作用
    var xu1={
        name:"隔壁老徐",
        like:["吃","喝","玩","乐"],
        // es6中 可以省略 function
        sayHi() {
            // this =>xu
            this.like.forEach(
               ele =>{
                    //console.log(ele)
                    // 默认的this 指的是window
                    console.log(this.name+"喜欢"+ele)
                    // 把外围的this=>实例化对象xu 绑定给回调函数中的this(window)
                }
            )
        }
    }
    xu1.sayHi()
</script>
```

##### for of

 遍历:   简化for循环  如果只要值 不要下标的情况下 可以直接使用for fo简化

 特点: 除了对象和关联数组 其他都可以遍历

​	下面测试了 4种遍历 

```js
<script>
    var arr=["张三","张思","张武"];
    //基本的 for   i是下标
    for (var i=0;i<arr.length;i++){
        console.log(arr[i]);
    }
    // for in   key就是下标
    for (var key in arr){
        console.log(arr[key]);
    }
    //forEach  可以有下标
    arr.forEach((ele)=>console.log(ele))
    // for of    没有下标  只要值不要下标可以使用
    for (var val of arr){
        console.log(val);//val当前遍历的值 
    }
var obj={
        name:"隔壁老王",
        age:"45"
    }
    for (var val of obj){
        console.log(val); //obj is not iterable  不可遍历
    }
</script>
```

### 函数中的参数增强

#####   1.参数的默认值

​		特点: 调用方法是 如果没有传实参 也会有默认的实参的数据

​	        在定义函数的形参时  赋予默认值

​		function(形参1,形参2="默认值"){}

```js
<script>
    function sayHi(name="小王",text="啥也没说") {
        console.log(name+":"+text)
    }
    sayHi("隔壁老王","我招谁惹谁了") //隔壁老王:我招谁惹谁了
    sayHi("隔壁老徐")// 隔壁老徐:啥也没说
    sayHi()// 小王:啥也没说
</script>
```

##### 2.不确定参数

​	作用: 因为在es中arguments不受箭头函数支持，通过不确定参数实现获取实参列表

​		arguments:  是一个对象，操作没有数组方便 所以就被替代了

​       语法:

 	   function  fn(...arr){}

​                 ...arr:不确定的参数列表:原理是默认会生成一个数组接收

​	优点: 因为是一个数组 可以使用数组所有的API。支持箭头函数。

```js
<script>
    // 如果一个变量值不会发生改变 则 我们推荐使用const声明  =>常量
    const f=function (a,b) {
         console.log(a+b);
         console.log(arguments)//
        console.log(typeof  arguments)// object
    }
    f(1,2)
    //  es中的箭头函数 不支持 arguments对象
 /*   const f1=(a,b)=>{
        console.log(a+b)
        console.log(arguments)
    }
    f1(1,2)  // arguments is not defined*/
    // 不确定参数
    function salary(name,...arr) {
        // 除了第一个参数name之外 传进来的n个参数都会默认用数组接收
        console.log(arr);// [1000, 2000, 5000, 600]
        console.log(arr.length);
        let sum=arr.reduce((ele,next)=>{
             return  ele+next
        })
        console.log(name+"薪资总共是"+sum)
    }
    salary("隔壁老徐",1000,2000,5000,600);
    salary("隔壁老王",1000,2000,5000);

</script>
```

##### 打散参数

​      定义:

​	  传入的数据中如果是一个整体的数组或者是对象 可以进行自动的拆分为每个子元素进行传递

​      语法:    在调用时  函数(...arr)

​                    自动的拆分每个子元素 进行传递

​      固定套路:

​		复制 数组、合并数组、复制对象、合并对象  如下案例

```js 
<script>
    function salary(name,...arr) {
        // 除了第一个参数name之外 传进来的n个参数都会默认用数组接收
        console.log(arr);// [1000, 2000, 5000, 600]

        console.log(arr.length);
        let sum=arr.reduce((ele,next)=>{
             return  ele+next
        })
        console.log(name+"薪资总共是"+sum)
    }
    salary("隔壁老徐",1000,2000,5000,600);
   var arr=[2000,3000,5000];
   //将数组打散 挨个的进行插入
   salary("隔壁老陈",...arr)


    var arr1=[1,3,4,6];
   console.log(Math.max(...arr1)) //最大值
   console.log(Math.min(...arr1)) //最小值

    //复制一份数组
    var arr2=[...arr1];
    console.log(arr2);
    console.log(arr1 == arr2);// false  全新的数组
     //合并数组
    var arr3=[2,4,6,8]
    var arr4=[...arr1,...arr3]
    console.log(arr4);

    //对象 复制
    var obj1={
        name:"隔壁老徐",
        age:18,

    }
    var obj={...obj1}
    console.log(obj);
    console.log(obj == obj1); // false

    var obj3={
        salary:1800,
    }
    // 对象的合并。
    var obj2={...obj1,...obj3}
    console.log(obj2);
</script>
```

####  解构

​	定义: 将一个数组或者是对象中的成员 单独分别的提出使用。

​		   封装无处不在，一个对象中方法和属性是很多，如果我们只需要只用部分的属性功能，总是需要.xxx不方便， 可以单独提出出来

 分类: 数组解构、对象解构、参数解构。

#####  1、数组解构

​	在数组中 提取出部分的子元素。

​	操作:   1.先要保存元素到变量中  

​		     2.用等号将原数组赋值给变量 解构。

​     var arr =[值1 ,值2 ,值3]

​     var [变量1,变量2,变量3]=arr

​     结果就是:    变量1==值1  变量2==值2   变量3==值3

   应用: 没有第三人情况 交互2个变量的值

​	var x=5,y=10;

​        [x,y]=[y,x];

```js
<script>
    var arr=["隔壁","老徐","没有","老王"];
    var [a,b,c,d]=arr; // 默认是挨个顺序读取
    console.log(a,b,c,d)
    var [,a1]=arr;// 拿取第二个值
    console.log(a1);

    //套路  没有第三者的情况下  进行换位
     var x=5,y=10;

     [x,y]=[y,x];
     console.log(x,y)// 10,5
    var [c1,,,c2]=arr
    console.log(c1,c2) // 隔壁 老王

</script>
```

##### 对象解构

​    在一个对象中提出部分的属性

​     语法:  对象中的属性名 和定义的属性名 进行配对。

​	var obj={

​		属性1:值1,

​	        属性2:值2,..

}

var  {属性1:接收变量1,属性2:接收变量2,..}

 结果:   接收变量1=属性1的值 也就是值1      接收变量2=属性2的值 也就是值2...

 语法糖: 可以设置 属性名和接收的变量名一致 实现简写

​       var {id:id,title:title,price:price}=obj_puc

​	简写为:        var {id,title,price}=obj_puc

```js
<script>
    var obj={
        name:"隔壁老王",
        age:18,
        salary:1800,
        product:{id:1,title:"iphone",price:"8888"},
    }
    //   name:对象的属性名:    uname声明的变量用于匹配的
    var {name:uname,salary:usalary}=obj
    console.log(uname,usalary);//隔壁老王  1800

    // 只想要product
    var {product:obj_puc}=obj


    // var {id:id,title:title,price:price}=obj_puc
    // console.log(id,title,price)
    //直接省略   简化的写法   属性名和声明匹配的变量名一致就可以了。
    var {id,title,price}=obj_puc
    console.log(id,title,price)// 1 iphone 8888
</script>
```

##### 参数解构

​	参数可以进行拆分进行默认操作。 以对象的形式拆分	 	

```js
<script>
    //通过对象的形式 进行形参的定义
    // 定义形参的默认值。 是在函数体内定义
    function kft({
           zs,  // 主食
           xc,  // 小吃
           yl   //饮料
                 }) {
           //在函数体中  定义默认值
          zs=zs||"香辣鸡腿堡";
          xc=xc||"薯条";
          yl=yl||"中可";

        console.log(`
            主食:${zs},
            小吃:${xc},
            饮料:${yl},
        `);
    }
    kft({zs:"奥尔良鸡腿堡",xc:"烤翅",yl:"豆浆"});
    kft({zs:"奥尔良鸡腿堡",xc:"烤翅"});
    kft({});//默认值
   // kft({abc});// 输入一个没有定义的形参 会报错
</script>
```

#### class(类)

​	定义:  专门进行将一个类型的构造函数和原型对象进行整体的包裹.

​	出处: 旧的js中 构造函数和原型对象是分开的，正常一个面向对象语言是一个整体，写法也很繁琐。 今后 如果 只需要通过class代替原有的写法，大大的简化，也便于代码的阅读

​	语法:

​	    用class{} 包裹构造函数和原型对象

​		1.构造函数名字升级为class名 所有的构造函数名统称为 constructor

​	        2. 所有的原型对象的方法都 可以直接保存在class中 不再需要通过 xxx.prototype.xxx,

​		3 写法变了 但是原理是一样的  构造函数+原型的概念。语法上和之前学的一致的。

​    注意: 语法糖的写法 只能说定义原型的方法只能是es6的写法 不能出现function

​	  在class中定义原型属性 没有用直接定义在实例化的对象中。

​	   真的要去定义原型的属性 则还是可以使用之前es6之前的语法

​	        Student.prototype.house="500亩的豪宅"

```js
<script>
    //1.构造函数名升级为类名  es class语法糖
    class  Student{
       //2.原本的构造函数统一为
       constructor(sname,sage){
           this.sname=sname;
           this.sage=sage
       }
      //3.原型直接写在class中也不需要通过.prototype实现
      sayHi(){
          console.log("大家好我是"+this.sname+"我今年"+this.sage)
      }
      money=123 // 定义的属性 直接在实例化对象中去声明的 并没有在原型中

    }
    // 实例化对象
    var  xu=new Student("隔壁老徐",12)
    xu.sayHi()
    console.log(xu);
    // 如果真的要在原型中挂载属性 还是可以使用之前的写法
    Student.prototype.house="500亩的豪宅"
    console.log(xu);
    console.log(xu.house);
</script>
```

##### 继承

 	 多个class之间可以实现属性和方法的共有，可以通过

​	     1.在父类中保存相同的属性和方法

​	      2.子类通过关键词 extends 继承父类 

​	      3.子类在创建构造函数时  必须添加super()  执行父类中的构造函数

​		  也可以在自己的构造函数中   自定义属性和方法	

 **class  子类  extends  父类{**

​			**constructor(参数列表){**
​       		 **super(uname,uage) //  通过super 进行调用父类构造**
​        **this.score=score; //  定义当前构造Stu类的自己的属性**
​    **}**

**}**

```js
<script>
    class Person{
        constructor(uname,uage){
            this.uname=uname;
            this.uage=uage
        }
        sayHi(){
            console.log("大家好我是"+this.sname+"我今年"+this.uage)
        }
    }
    // 1.通过关键词 extends实现继承
    class Stu extends Person{
        constructor(uname,uage,score){
            //2.使用父类的属性  通过super 调用父类的构造属性
            super(uname,uage) // 不加直接报错
            this.score=score; //定义当前构造Stu类的自己的属性
        }
        //定义自己的方法
        getScore(){
            console.log("我考了"+this.score+"分")
        }
    }
    var ming=new Stu("小明",12,99);
    console.log(ming)
    ming.sayHi()// 爷爷辈的方法
    ming.getScore()//父辈的方法
</script>
```

##### symbol

   es6新增的一个原始数据类型。主要作用是作为一个类似于id属性目的是体现唯一性。

  声明:   

​    1.通过Symbol() 函数生成

```js
let s= Symbol();//
console.log( typeof  s);
let  s1=Symbol("foo");// 描述
```

2. Symbol() 可以设置字符串作为参数， 表示对当前Symbol实例的描述，目的是为了可以在控制台显示出来。 或者我们进行数据转换 比如转为字符串类型时 容易区分。 不是指 **具体的值**

   特点: 

    1. foo只是描述 不是值

    2. 可以转为其他类型数据

    3. 唯一性

    4. 不能计算(包括字符串拼接)

       sa.description  可以获取参数描述				

```js
<script>
    // 声明  新增的是原始类型是数据
    let s= Symbol();//
    console.log( typeof  s);
 //  symbol是 原始类型 不是引用类型。
    // let s= new Symbol()    //不能new
    console.log(typeof  s);// 报错
  //  foo 和aaa 不是值 只是用于识别的一个标记
    let  s1=Symbol("foo");
    let  s2=Symbol("aaa");
    // 转换为字符串类型
    console.log(s.toString())    // Symbol()
    console.log(s1.toString())  // Symbol(foo)
    console.log(s2.toString()) // Symbol(aaa)

    // 体现唯一性
    var a=10,b=10;
    console.log(a === b); //true
    let a1=Symbol()
    let a2=Symbol()
    console.log(a1 ===a2);  // false

    // 计算也会报错。
  //  console.log(a2+"这是一个Symbol类型的值");// Cannot convert a Symbol value to a string 
    // 可以转换   
    console.log(typeof  String(a2), String(a2)); //string    Symbol()
    console.log(typeof  Boolean(a2),Boolean(a2));//boolean   true

 // 输出当前的symbol的参数描述
    let  sa=Symbol("描述");
    console.log(sa.toString()) // Symbol(描述) => 描述
    console.log(sa.toString().slice(7,-1))// 描述
    // es9中直接就 提供了属性 获取参数
    console.log(sa.description); //  描述
</script>
```

#### 应用

​    对象中。    很多情况模块化开发中  很多属性会出现重名 数据相同。 Symbol 每个值都是不相等，就可以作为 标识符，用于对象的属性名中。 就可以保证对象中的属性名不会重复

```js
<script>
    var mySymbol=Symbol("name");
    var obj={}
        //方式1
    obj[mySymbol]="隔壁老徐";
    console.log(obj)
    var mySymbol2=Symbol("age")
    // 方式2
    var xu={
        [mySymbol]:"隔壁老王",
        [mySymbol2]:12
    }
    console.log(xu);
    //方式3
    var wang={}
    Object.defineProperty(wang,mySymbol,{
        value:"隔壁老陈"
    })
    console.log(wang);

    var  ming={}
    ming.mySymbol="隔壁老李"; //相当于自动创建一个普通的属性
    console.log(ming)// 不是symbol  类型的数据
    console.log( typeof  ming.mySymbol) //string类型
    // console.log( typeof  xu[mySymbol]) // string
</script>
```

### day07=======================================

##### 问题:  关于默认写法和箭头函数之间的this指向问题分析

​	 下面2个案例 分别测试对象的原型方法和对象中的方法 得出的结论是 不能直接在对象中使用箭头函数否则的话 this指向为window

```js
<script>
    function Student(sname,sage) {
        this.sname=sname;
        this.sage=sage;
    }
    //定义构造原型
    Student.prototype.sayHi=function () {// 默认之前的写法
        console.log(`大家好我叫${this.sname},我今年${this.sage}`);
    }
    Student.prototype.toString=()=>{
        console.log(this);
        console.log(`{sname:${this.sname},sage: ${this.sage}}`);
    }
    var xu=new Student("隔壁老徐",18);
    var wang=new Student("隔壁老王",17);
    console.log(xu);
    xu.sayHi(); // 正常输出
    xu.toString() //输出的this是window
    xu.toString.call(wang)//还是不行。 window

    var tt=xu.toString.bind(wang);
    tt() // 还是window
   // 总结:  对象中不能直接使用箭头函数的(一般使用在回调函数(没有名字的)中)
</script>
```

```js
<script>
  var obj={
      name:"隔壁老徐",
      sayHi:function () {
          console.log(this.name); // 指的当前的实例化的对象
      }
  }
  obj.sayHi();//  ok
  // 简化 :function  es写法
  var obj1={
      name:"隔壁老徐",
      sayHi() {
          console.log(this.name); // 指的当前的实例化的对象
      }
  }
  obj1.sayHi();//  ok

// 测试  使用箭头函数
  var obj3={
      name:"隔壁老徐",
       sayHi: ()=> {
           console.log(this); // 此时的this 指向的是window
           console.log(this.name); //
      }
  }
  obj3.sayHi();//  ok
</script>
```

##### 问题:探讨 symbol类型定义方式.和[]的区别

 结论:    

​		1、 .的形式命名只是普通的字符串 而[]命名则是可以实现设置symbol类型
​                2、 symbol 不支持遍历

```js
<script>
    // 接着头一天案例16 的问题
    //  不能直接在对象中.的形式去定义symbol类型  直接表示的字符串类型
    var mySymbol=Symbol("name");
    var obj={}
        //方式1
    obj[mySymbol]="隔壁老徐";
    console.log(obj)
    var mySymbol2=Symbol("age")
    // 方式2
    var xu={
        [mySymbol]:"隔壁老王",
        [mySymbol2]:12
    }
    console.log(xu);
    //方式3
    var wang={}
    Object.defineProperty(wang,mySymbol,{
        value:"隔壁老陈"
    })
    console.log(wang);




    // 测试   .的形式
    var  ming={}
    ming.mySymbol2="隔壁老李"; //相当于自动创建一个普通的属性
    console.log(ming)//
    console.log(ming.mySymbol2, typeof  ming.mySymbol2) // "隔壁老徐"  string类型
    for(let key in ming){
        console.log(key , typeof  key); //mySymbol2    string
        // 得出结论: 直接.的形式 mySymbol2就是普通的字符串。
    }

    // 测试  []的类型
    var li={}
    //方式1
    li[mySymbol]="隔壁老李";
    console.log(li[mySymbol], typeof  li[mySymbol]) //隔壁老李  string
    //  symbol 不支持遍历
   /* for (let key in li){
        console.log(123)
        console.log(key,typeof key);
    }*/
     //只能通过自己独有的方法获取属性
    var ss=Object.getOwnPropertySymbols(li);
    console.log(ss);// [Symbol("name")]; 返回的是一个对象
    //判断类型
    console.log(typeof ss[0])//  symbol类型

    // 结论:   .的形式命名只是普通的字符串 而[]命名则是可以实现设置symbol类型
    //         symbol 不支持遍历
</script>
```

#### 遍历

​    symbol不能被 for 循环直接遍历。

​    可以通过自己独有的属性

​	 Object.getOwnPropertySymbols(obj); 获取symbol 直接返回的是一个数组

​     正是因为这个特点,可以作为对象的key值 作为对象的一些私有的属性，只能内部自己去使用。

```js
<script>
    const  a=Symbol("a");
    const  b=Symbol("b");//
    let  stu={
        uname:"小明",
        age:15,
        sex:"男",
        [a]:"真名:王二狗",
        [b]:"口号:好好学习。",
        id:101,
    }
    console.log(stu);
    for (let key in stu){
        console.log(key,stu[key])//结论: symbol类型的属性无法直接获取
    }
    //只能通过 独有的方法获取
    var ss=Object.getOwnPropertySymbols(stu);
    console.log(ss)
    for (var key in ss){
      //  console.log(key);//ss数组的下标
        console.log(ss[key])//Symbol(a) Symbol(b)  对象的key值
        //对象的value值
        console.log(stu[ss[key]]) //value值   不能用. 
    }
</script>
```

##### 模拟对象的私有属性

 	就是因为symbol独有的特性。无法直接获取。只能特殊的处理 或者是自定义返回的方法。

```js
<script>
    function Student(name,sex) {
        this.name=name;
        this.sex=sex;
        //创建一个symbol类型是属性
        const  stuId=101;
        var  si=Symbol("stuId");
        this[si]=stuId; //相当于给si设置的是一个私有化的属性。直接访问无法访问
        this.getStuId=function () {
            return this[si];
        }
    }
    var  ming=new Student("小明","男");
    console.log(ming)
    console.log(ming["name"])
    console.log(ming[Symbol["stuId"]]);//undefined;
    console.log(ming.stuId);//undefined
    console.log(ming.si);  //undefined
    console.log(ming["si"])// undefined
    //通过独有的属性获取
    var ss=Object.getOwnPropertySymbols(ming);
    console.log(ming[ss[0]]);

    // 或者是再次手动的添加方法 返回
    console.log(ming.getStuId()) //101
</script>
```

#### 迭代器(iterator)

​	定义:    是一个类似接口，其实是对象。可以为不同的数据结构进行统一的访问的机制。任何数据类型只要部署了iterator接口，就可以完成遍历。 可以理解成"指针"(不是指针)

​       作用:   

​		1.提供了各种数据结构的统一的接口

​		2.使得数据结构中的成员按照某种特定的顺序排列

​		3.提供了 遍历 for...of  的接口实现

​      语法实现

```
1.创建一个类似的 指针对象，指向的是数据结构类型中起始位置 （）
2.第一次去调用指针对象的next()方法这样指向对象就会自动去找数据结构中第一个成员
3.再次调用next() 则会再找 下一个成员
4. 不断的去找下一个,知道数据结构的成员没有了 ， 到了结束的位置 
//结束了 还去调用 返回undefined 
```

   每次调用next()方法时  会返回当前数据结构中成员的信息。 

​	 包含 

​		1 value:当前成员的信息值    

​		2.done: 是一个bool值  是否遍历结束 true就结束了。

```js
<script>

    function makeIterator(array) {
        var nextIndex=0;
        return {
            // 其实 不需要手动去next() 迭代器自己会跳到下一个成员的位置
            next(){
                return  nextIndex<array.length?
                    //还没有结束
                    {value:array[nextIndex++],done:false}:
                    {value:undefined,done:true}
            }
        }
    }
    var arr=[12,23,34,45,22]; //5
    //     ↑           ↑
    var it=makeIterator(arr);
    //每次调用next() 自动跑到下一个成员位置
    console.log(it.next()) //{value: 12, done: false}
    console.log(it.next()) //{value: 23, done: false}
    console.log(it.next()) //{value: 34, done: false}
    console.log(it.next()) //{value: 45, done: false}
    console.log(it.next()) //{value: 22, done: false}
    //此时 已经到了最后一个位置了
    console.log(it.next()) //{value: undefined, done: true}
    for (var v of arr){
        console.log(v);
    }
</script>
```

遍历器对象中  done属性是false   或者value属性是undefined,是可以省略

```js
// 遍历器对象中  done属性是false   或者value属性是undefined,是可以省略
   function makeIterator1(array) {
       var nextIndex=0;
       return {
           // 其实 不需要手动去next() 迭代器自己会跳到下一个成员的位置
           next(){
               return  nextIndex<array.length?
                   // 省略 value和 done
                   {value:array[nextIndex++],}:
                   {done:true}
           }
       }
   }
   var arr1=["徐","张","陈","沈"];
    var itt=makeIterator1(arr1)
   console.log(itt.next()); // {value: "徐"}
   console.log(itt.next());
   console.log(itt.next());
   console.log(itt.next());
   console.log(itt.next());//  {done:true}  就结束了。
```

#### 注意:

​	其实 我们默认的  数组  string 等数据结构 能直接被 for of遍历 是因为

​       js底层原生就部署了Symbol.iterator

![1600327392694](assets/1600327392694.png)

测试了 数组  对象  字符串中是否默认就有迭代器属性

​        对象是没有的 所有 对象也不能够被for  of遍历

```js
<script>
    //  定义:  for of能够遍历的人  就自带了迭代器属性
    //   通过symbol定义的一个values方法
    //    可以直接用不需要自定义了  比如: array  string
    var arr=[12,23,34,56];
    console.log(arr);
    let it=arr[Symbol.iterator]();
    console.log(it.next());//  {value: 12, done: false}
    console.log(it.next());//  {value: 12, done: false}
    console.log(it.next());//  {value: 12, done: false}
    console.log(it.next());//  {value: 12, done: false}
    console.log(it.next());//  {value: undefined, done: true}

    //   测试字符串 是否有 迭代器属性
    var str="hello";
    for (var v of str){
        console.log(v);// 能够挨个输出
    }
    var its=str[Symbol.iterator]();
    console.log(its.next());
    console.log(its.next());
    console.log(its.next());
    console.log(its.next());
    console.log(its.next());
    console.log(its.next());
    console.log(its.next());
  // 测试 对象
    var obj={
        name:"隔壁老王",
        age:12
    }
     console.log(obj);
   // let itobj=obj[Symbol.iterator]();
   // console.log(itobj.next()); // 报错   obj[Symbol.iterator] is not a function
    for(var v of obj){
        console.log(v) //obj is not iterable  不能遍历
    }
</script>
```

默认 对象是不能被for of遍历 因为没有迭代器属性。

  可以自定义

​	  对象中还有对象的情况 this执向就不是同一个了。常见做法之一是，保存想要的那个this

​	 通过第三个人 接收当前想要保存的this。

```js
<script>
    var obj={
        data:["徐","张","陈","沈"], //4
        [Symbol.iterator](){
            let index=0;
            //借助中间人 保存此时的this(obj)
            let that=this; 
            console.log(this)//当前的对象 obj
            return {
                next(){
                   // console.log(this); // next(){}的对象
                    if (index<that.data.length){
                        return {
                            value: that.data[index++],
                            done:false,
                        }
                    } else{
                        return {value:undefined,done:true}
                    }
                }
            }
        }
    }
    console.log(obj)
    // 测试 能否被for of遍历
    for(let v of obj){
        console.log(v);
    }
</script>
```

延伸: 直接给类/构造函数添加迭代器属性 实例化对象都可以遍历了

​	因为是在class中生成的方法 就是挂载到原型中  所有不需要next方法不需要写在Symbol.iterator中

```js
<script>
    class CreateIterator{
        constructor(start,stop){
            this.start=start; //起始的值
            this.stop=stop;  //结束的值
        }
        [Symbol.iterator](){
            return  this;
        }
        //next() 添加在原型中
        next(){
            var value=this.start;
            if(value<this.stop){
                this.start++;
                return {value:value,done:false}
            }else{
                return {value:undefined,done:true}
            }
        }
    }
    let obj=new CreateIterator(1,6);
    console.log(obj);
    for (var v of obj){
        console.log(v)
    }
</script>
```

#####    类数组对象特殊性

​     总结:     如果是索引下标的对象是可以是可以直接使用数组的构造函数的原型中的
​                   Symbol.iterator属性
​                   如果不是索引下标 则就是普通的对象 是不支持的。

```js
<script>
    // 类数组的写法
    var arr=[12,23,34];
    console.log(arr);
    //  索引下标
    var obj={
        0:"徐",
        1:"张",
        2:"李",
        3:"王",
        length:4,
        //添加iterator接口
        //可以直接引入数组的接口
        //[Symbol.iterator]:Array.prototype[Symbol.iterator]
        // 可以简写    引入数组构造函数中原型中的属性
        [Symbol.iterator]:[][Symbol.iterator]
    }
    for (var v of obj){
        console.log(v);
    }
    //
    var obj1={
        name0:"徐",
        name1:"张",
        name2:"李",
        name3:"王",
        length:4,
        [Symbol.iterator]:Array.prototype[Symbol.iterator]
    }
    for (var v of obj1){
        console.log(v); //undefined
    }
    //结论: 如果对象中的下标是索引值 是可以直接使用数组的构造函数的原型中的
    // Symbol.iterator属性
    //  如果不是索引下标 则就是普通的对象 是不支持的。
</script>
```

##### 总结:

​	 for of  解构赋值 , yield*    promise.all()  promise.race()..底层的遍历都是通过迭代器实现的。

### Generator(生成器)

   定义:   状态机制， 封装了多个不同的状态。

​	         在执行Generator函数时返回一个遍历器的对象，  也就是说， generator函数除了状态机制之外 还是一个遍历器对象生成函数。 返回的遍历器对象 可以依次去遍历函数中的每一个状态

  特点:   首先来说是一个函数，   和普通的函数区别

​              1.function和函数名之间有一个* 号

​	    2.函数 体内使用yield()表达式  定义不同状态机制下的值	

```js
<script>
    // 特殊性  函数名和function有一个 *
     function*NewGenerator() {
         yield  "步骤1"; //yield 是一个不同状态下的 记号 等着被text()执行
         yield  "步骤2";
         yield  "步骤3";
     }
     var  g=NewGenerator();
       // 不会直接把函数内容全部执行  而是等着
    console.log(g.next()); //{value: "步骤1", done: false}
    console.log(g.next()); //{value: "步骤2", done: false}
    console.log(g.next()); //{value: "步骤3", done: false}
    //还是会返回  undefined   done是true的情况下
    console.log(g.next()); //{value: undefined, done: true}
</script>
```

 执行过程 如下图。

   注意:     *号的位置  js没有严格定义写在哪里  一般是贴着function				

![1600334179218](assets/1600334179218.png)

##### 执行过程

```
1.生成器函数中，上来一定是先找状态机制 yield,就不动了，把当前状态机制后面跟的值 返作为对象给调用者
2、下一次调用next()方法时， 继续执行找下一个yield状态机制，
3、 如果没有再遇到yield表达式  则运行到结束直到return语句结束，输出return 返回的内容。
4、 最后在调用next()  则会输出undefined
```

##### 特征

​     yield不能写在 除了生成器意外的函数中的

​	直接调用时不会立刻去执行函数体内容的。需要再次next调用。

```js
<script>
    // yield  只能写在 生成器中
   /* function f() {
        yield  "hello" //报错
    }
    f()*/
   function* f() {
       console.log("hello")
   }
   var str=f();
    console.log(str);//这里并不会输出内容
    //只有调用next 才执行
    //可以通过 暂缓执行
    setTimeout(function () {
        str.next();
    },3000)
</script>
```

##### 写法注意问题



```js
<script>
    function* demo() {
        //直接写是会报错的    需要加() 包裹yield
       // console.log("hello"+ yield );
        //console.log("hello"+ yield 123);
        // yield 只是状态机制 程序一旦看到yield就会立马停下来
        console.log("hello "+ (yield) );
        console.log("helloWorld "+ (yield 123) );
        //作为参数 去调用函数   是可以不加()的
        foo(yield  666);

        let abc=yield ;
    }
    function foo(a) {
        console.log("我执行了"+a)
    }
    var y=demo()
    // 挨个执行 查看执行过程  永远是先找yield
    console.log(y.next()); // {value: undefined, done: false}
    // 此时会打印之前状态的内容
    console.log(y.next()); // {value: 123, done: false}
    console.log(y.next()); // {value: 666, done: false}

    console.log(y.next()); //  {value: undefined, done: false}
    //结束了。
    console.log(y.next()); //  {value: undefined, done: true}



</script>
```