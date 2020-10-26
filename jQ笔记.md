### [jquery]()

####   1.简介:

​	jq是一个javascript类库，通过封装了元素的js函数 ，主要学习也就是这些方法

![1596595982180](assets/1596595982180.png)

####    2.作用	

​     1.轻量级  

​     **2.简化  dom 操作**

​     3.封装很多 事件操作

​     4.封装了很多动画

​     **5.封装了ajax异步**	

​     6.  老版本1.xx 都支持兼容 IE 6,7,8,9 。

​     7.扩展性好， 在Jq的基础上 实现第三方框架(bootstrap)

​    

####   3.理念:

​     写的少 做得多

####   4 版本:

​	 1.xxx 如果未来公司 还是处理老项目 还是要兼容一些老版本的浏览器 那么使用jq1.xxx

​          2.xx/3.xxx 版本都砍掉了兼容的代码 30%  运行效率就更快  不考虑兼容使用3版本

####    5.中文官网

```
https://www.jquery123.com/

下载有所有的版本 
https://www.bootcdn.cn/jquery/
下载 直接右键另存为即可
  xxx.min.js : 压缩文件 上线项目使用
  xxx.js     : 测试 开发阶段使用
```

####    6.引入

```
<!--引入-->
<script src="js/jquery3.3.1.js"></script>
https://cdn.bootcdn.net/ajax/libs/jquery/3.5.1/jquery.min.js
```

### 2.使用

####   1.选择器

##### 	1.基本选择器

```js
   //原生
    var d1=document.getElementById("d1");
    d1.style.color="red";

    // console.log(jQuery)
   //选择器 获取  //修改样式
    $("#d2").css('color','yellow');

    //支持所有的 css选择器
    $(".d3").css("color","blue");
     //群组选择器   属性名需要使用驼峰命名
    $("p,div").css("fontSize","26px");
```

#####      2.基本筛选

```js
<div class="parent">
    <div>1</div>
    <div>2</div>
    <div>3</div>
    <div>4</div>
    <div>5</div>
    <div>6</div>
</div>

<script src="js/jquery3.3.1.js"></script>
<script>
    //  第一个孩子
    $(".parent div:first").css("color","red");
    //除了第一个孩子
    $(".parent div:not(:first)").css('color','blue');
    //奇数行   even 从下标0开始计算  偶数下标行  0 2 4
    $(".parent div:even").css("border","1px solid #000");
    // 偶数行    奇数下标行 odd  拿取下标 1  3  5
    $(".parent div:odd").css("border","1px solid #0f0");
    //  :eq  下标从0开始数 第n个子元素
    $(".parent div:eq(0)").css("fontSize","30px")
    // 选择 下标大于n的  所有元素
    $(".parent div:gt(3)").css("backgroundColor","#ccc");//下标大于3的所有元素
    // 选择 下标 小于n的  所有的元素
    $(".parent div:lt(3)").css('backgroundColor',"#040");//下标小于3的所有的元素


</script>
```

##### 3.内容筛选

​      :contains('文本内容')     包含文本内容

​      :empty			空元素

​      :has(p)			判断子元素中有   p可以替换为任意元素

​      :parent			非空元素

```html
<div class="parent">
    <div>锄禾日当午</div>
    <div ad="a123">锄禾累了</div>
    <div ad="a">锄禾身体有问题了</div>
    <div ad="bbq">当午也病了</div>
    <div>当午回家了</div>
    <p>锄禾死囚了</p>
    <div></div>
</div>
<div class="parent">我啥也没有</div>
<script src="js/jquery3.3.1.js"></script>
<script>
   //通过指定的内容 找到元素
   // 找   div中 文本内容存在锄禾的元素
    $(".parent div:contains('锄禾')").css('color','yellow');
    // 匹配文本为空的元素
    $(".parent div:empty").css('border','10px solid #ccc');
    //3.给所有包含p的元素 添加样式  找的是父元素
    $(".parent:has(p) ").css('background','#aaa');
    //4.找到 有子元素/文本的     元素
   //         是个div并且里面有内容 非空
    $(".parent div:parent").css('fontSize','30px');
    
</script>
```

##### 4.属性选择器

```js
 [attr]     [attr=value]    [attr=^value]    [attr=$value]    [attr*=value]   
 [attr~=value]        查找值中 包含一个值的元素
 [attr !=value]       查找不等于值的元素
 [attr =value1][attr=value2] ：同时多个都必须满足
```

```js
 //属性选择器
  $('[ad]').css('border','3px solid #ccc');
  // 除了 属性值为a的元素的其他所有元素
  $('.parent div[ad!="a"]').css('borderRadius','12px')
  // [] []多个属性同时有
 $('.parent div[ad][title]').css('padding','20px')
//   ~=  支持 多个属性值中  查找只要存在一个值的元素
 $('.parent div[ad ~="a"]').css('fontWeight','bold')
```

##### 5.子元素选择器

```
:first-child  
:last-child
:nth-child(n)
...
```

##### 6.表单类

```
:input 找input元素
:password
:checkbox
:radio    ....
//状态类
:checked   已经被勾选
:disabled   已经被禁用
:selected    被选中
:focus     获取焦点
```

##### 7.JQ中的事件绑定问题

​	1.没有onclick这种写法

           2. this =>$(this) 

​        this==$(this)[0]

```js
<input type="text" class="d1" >
<input type="checkbox"  checked>勾选
<script src="js/jquery3.3.1.js"></script>
<script>
    //直接加载 肯定没有
     //$(".d1:focus").css('outline','none');
    $("input:checked").css('display','none');

    //通过事件才能完成
    // 在jq中 没有onclick  这种写法
  /*  $(".d1").onclick=function () {
        console.log("执行")
        $(".d1:focus").css('outline','none');
    }*/
    $(".d1").click(function () {

        $(".d1:focus").css('border','10px solid red');
        console.log(this);//当前的input
      //   this.css(' borderRadius','10px');//报错
        //在jq中this 不能直接这么写
        $(this).css('outline','none'); //ok
    })
</script>
```

##### 关于this的特征

   特点:  this ->没有办法直接在jq中使用  需要替换为$(this)

​         **原生的可以用原生的**   **jq的可以直接使用jq的**
​         原生的肯定不能使用jq中的方法  但是
​        如果想要在jq对象中使用原生属性方法 则可以通过 $(this)[0]去设置

```html
<ul>
    <li>张子龙</li>
    <li>张无忌</li>
    <li>张山峰</li>
    <li>张一山</li>
</ul>
<button id="btn">点我</button>
<script src="js/jquery3.3.1.js"></script>

<script>
    //    console.log(btn.html());  原生dom没有 html() 方法 
    //给按钮绑定事件
    $("button").on('click',function () {
         //alert("点了")
        //console.log(this.html()); //报错
        console.log($(this).html());//点我    jq封装好的写法
        //可以使用原生的dom 结合着中  但是不能直接使用 因为
        // $(this) 返回的起始是一个 数组  需要先拿到下标0 对应元素内容
        console.log($(this)[0].innerHTML);//ok
        
        console.log($(this).innerHTML);//  undefined
        
        console.log(this.innerHTML); //原生的操作    ok

        
    })
</script>
```

##### 8.遍历方法

​      1. each(function(i){})方法:   让每个元素 执行回调函数    

​		i对应每个元素的下标

​      2. index()  获取   下标 

​          index('选择器' )  获取指定选择器的下标

​     3.  .length 长度  个数 从1开始

​     4 . get(i)     获取指定的下标的元素   

```js
<ul>
    <li>张子龙</li>
    <li>张无忌</li>
    <li class="a">张山峰</li>
    <li class="a">张一山</li>
</ul>
<button id="btn">点我</button>
<script src="js/jquery3.3.1.js"></script>

<script>
    //点击 点我  实现 给每个li 添加 类名为 red
    $("#btn").click(function () {
        //遍历     每个li 都会执行function
        $("ul li").each(function (i) {
           // this.className="red";
           //  $(this)[0].className="red";
            // 可以直接使用jq添加类 后面讲

            this.title="red"+i;  //  i 对应的是当前元素li 的下标

        })
    })
  //每个li绑定事件
    $("ul li").click(function () {
        //获取当前元素的下标    index()
        console.log($(this).index());  //jq的方法
        //获取指定元素的下标 没有没有返回  -1
        //找 当前元素中 具有class类名值为a的元素的下标
        console.log($(this).index('.a'));

        //获取个数
        console.log($("ul li ").length); //4

        //  获取指定下标的元素
        console.log($("ul li").get(1)); //获取所有的li中的第2个元素
    })
</script>
```

##### 9.操作属性

######    attr() 方法 操作属性 可以实现	

​	  添加属性

​	  获取属性

​	  添加自定义的属性 

​           一口气添加多个属性 可以使用{xxx:"xxx",xxx1:"xxx1"...}

```html
 <style>
        /* */
      .red{
          color:red;

      }
    </style>
</head>
<body>
<div class="" id="d1">我是隔壁老徐</div>
<div class="" id="d2">我是隔壁老张</div>
<button class="btn">点我</button>
<script src="js/jquery3.3.1.js"></script>
<script>
    $(".btn").click(function () {
        //添加  类名
        // 链式编程     可以在一个元素中 操作多个方法
        // 一口气添加了 3个属性
        $("#d1").attr("class","red").attr("title",'年轻小伙').attr("aa","hello");

        //获取 属性
        console.log($(this).attr('class')) // btn

        // 通过 对象的形式添加属性
        $("#d2").attr({
            //key :value,
            class:"red",
            title:'中年油腻男',
            "aa":'hello' ,  //也是ok
            //   对象中的属性名 可以省略 ""   最后一个属性值可以省略 ,
        });
    })
</script>
```

######    删除属性

​     removeAttr("xxx") 删除属性

```html
 <style>
        /* */
        .d1{
            color:red;
            background-color: aqua;
        }
    </style>
</head>
<body>

<div >Lorem ipsum dolor sit amet, consectetur adipisicing elit. Consectetur dignissimos eligendi illum! Accusamus itaque nemo nesciunt praesentium, provident quaerat totam vitae. Delectus ea fugit in incidunt maxime, modi praesentium veritatis.</div>
<script src="js/jquery3.3.1.js"></script>
<script>
    //鼠标移入
    $("div").mouseover(function () {
        // 添加类名属性
         $(this).attr("class",'d1')
        
    })
    //鼠标移出
    $("div").mouseout(function () {
        // 删除 类名属性
        $(this).removeAttr("class");
    })
</script>
```

### day02===========================================、

#####  1.prop() 设置属性    

​    一般设置的是bool类型的属性   

```html
<body>
<div class="box">
    <input type="checkbox">吃
    <input type="checkbox">喝
    <input type="checkbox">玩
    <input type="checkbox">乐
</div>
<div class="box1">
    <textarea name="" id="" cols="30" rows="10">
        条款: 根据中华人民共和国相关法律， 本网站禁止18岁以上浏览
    </textarea> <br>
    <input type="checkbox"> 我同意
    <input type="submit" value="提交" disabled>
</div>
<script src="js/jquery3.3.1.js"></script>
<script>
    // 设置默认勾选一个
    $(".box input:first").prop('checked',true);
    // 除了第一个 其他禁止点击   disabled
    $(".box input:not(:first)").prop('disabled','true')

     // 点击我同意 实现  可以 提交
    $(".box1 input:first").click(function () {
        //判断
      /*  if($(this).prop("checked")){
            $(".box1 input:last").prop("disabled",false)
        }else{
            $(".box1 input:last").prop("disabled",true)
        }*/
        //  提交 按钮的 bool值和 点击按钮的bool值 相反的
      $(".box1 input:last").prop("disabled",!$(this).prop("checked"));
    })
</script>
```

#####    2.data（）

​         给元素 设置一个 隐私属性 这个属性和值 在dom里面是看不到的

​        在返回的元素的 jquery对象中.

```html
<div>你看不到的</div>
<button class="add"> 把数据 添加到 div元素中</button>
<button class="getDate">获取添加的div 元素中的数据</button>
<script src="js/jquery3.3.1.js"></script>
<script>
    // 等待页面加载完
    $(document).ready(function () {
         $(".add").click(function () {
             //添加 数据
             $("div").data("xu","年轻小伙");
         })

         $(".getDate").click(function () {
             //获取数据
              var txt= $("div").data("xu");
             console.log(txt);

             console.log($("div"))
         })

    }
    )
</script>
```



![1596680745855](assets/1596680745855.png)

##### 3.HTML的代码文本表单的值

1. ​     .html()     == xxx.innerHTML

2. ​     .text()      == xxx.innerText

3. ​     .val()        ==xxx.value  

   ```html
   <div id="d1">lorem</div>
   <div id="d2">lorem</div>
   <input type="text" value="">
   
   <script src="js/jquery3.3.1.js"></script>
   <script>
       // 获取html内容
       console.log($("#d1").html());
       //设置   支持html
       $("#d1").html("<h1>lorem</h1>")  // 直接解析为h1 加粗显示
       // 测试 .text()
       $("#d2").text("<h1>lorem</h1>")  //<h1>lorem</h1>
   
        $("input").blur(function () {  //失去焦点
            console.log($(this).val()); //  获取表单input的输入文本
        })
   
   </script>
   ```

##### 4.css类操作

​	.addClass("red")

​       .removeClass("red")

​       .toggleClass("red")  

```html
  <style>
        /* */
            .red{
                background-color: red;
            }
    </style>
</head>
<body>
<button >点我</button>
<div class="">
    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ad dolor hic mollitia natus totam, voluptatem! Beatae consequuntur dolor dolorem eligendi laboriosam nihil nostrum tempora velit! Harum modi nesciunt voluptas voluptatem!
</div>

<script src="js/jquery3.3.1.js"></script>
<script>
    //  移入  添加类
        $("div").mouseover(function () {
            $(this).addClass("red")
        })
    //移出    删除类
        $("div").mouseout(function () {
            $(this).removeClass("red")
        }) 
    //toggleClass  如果有则删除 如果没有则加上
       $("button").click(function () {
           $(this).toggleClass("red");
       })
</script>
```

#####    5.查找

​	.children()

​        .find()

​        .next()

​	.nextAll()

```html
<div class="parent">
    <ul>西游记
        <li title="">孙猴子</li>
        <li>天蓬元帅</li>
        <li class="bai">白龙马</li>
        <li>沙和尚</li>
        <div>我不是li</div>
    </ul>
    <div class="box">
        <div >三国志</div>
        <p class="p">三国杀</p>
        <div class="a">刘备</div>
        <div class="a" title="">刘能</div>
        <div class="a">刘一刀</div>
        <div title="" alt="1" class="p">刘罗锅</div>
         <h1>我是h1后来的</h1>
    </div>
</div>

<script src="js/jquery3.3.1.js"></script>
<script>
    //让所有的孩子 字体变红
    $(".parent ul").children().css("color",'red');//不包括文本
    //只想找  指定的元素     通过选择器查找
    $(".parent ul").children("li").css("color",'red');//找所有的li
    $(".parent ul").children("[title]").css("fontSize",'36px');//找所有的li

    //find()  找下一代 能找多个 支持选择器查找
    $(".parent div").find(".p").css("background",'red');
    // .p的下一个兄弟   支持 指定的元素
    $(".p").next("h1").css("color",'yellow');

    //nextAll() 找当前元素下 所有的同辈
    $(".bai").nextAll().css("border","3px solid #ccc");//所有的下一个兄弟
    $(".bai+li").css("borderRadius",'10px');//这个是选择器查找
    $(".bai").nextAll('li').css("border","3px solid #ccc");//匹配所有的兄弟

</script>
```

   .nextUntil("指定元素")   一直查找到指定元素结束

   .parent()    查找当前元素的父元素。

  .prevUntil( "指定元素")  从当前元素查找到指定元素

   **.siblings()**  获取当前元素的所有的兄弟元素  

```html
<div class="parent">
    <ul>西游记
        <li title="">孙猴子</li>
        <li>天蓬元帅</li>
        <li class="bai">白龙马</li>
        <li>沙和尚</li>
        <div>我不是li</div>
    </ul>
    <div class="box">
        <div >三国志</div>
        <p class="p">三国杀</p>
        <div class="a">刘备</div>
        <div class="a" title="">刘能</div>
        <div class="a">刘一刀</div>
        <div title="" alt="1" class="p1">刘罗锅</div>
        <div>刘一方</div>
        <h1>我是h1后来的</h1>
    </div>
</div>
<script src="js/jquery3.3.1.js"></script>
<script>
    // 表示 从当前元素下 开始 一直到 最末尾匹配的元素 的中间元素
    $(".box  .p").nextUntil("div[alt]").css("fontSize",'30px');

    // 匹配的是 当前元素的 父元素
    $(".p").parent().css("color",'red');
    //prev()  上一个兄弟
    $(".box").prev().css("padding",'10px')
    // prevAll() 上一个所有的兄弟
    //从.p1找到.p 的中间的元素
    $(".p1").prevUntil(".p").css("color",'yellow');

    // *****    自己的所有的兄弟 不论哥哥还是弟弟
    $(".bai").siblings().css("color",'red')
</script>
```

##### 6.过滤

​       .eq(1)  第几个

​      .hasClass("bgc"));  //判断是否有.bgc的类的元素  返回bool

​      .filter("选择器")   按照选择器找人

​       .is("选择器")      判断是否是某个元素 返回bool

​       .map（）      数组遍历

​        .has（“元素）   查找元素中有指定元素的 元素

​        slice(0, 1)     是一样的

```html
<ul class="list">
    <li>水壶</li>
    <li>三国
       <ul>
           <li>赵子龙</li>
           <li>阿飞</li>
            <li>小于</li>
            <li>老刘</li>
       </ul>
    </li>
    <li class="hong">红楼</li>
    <li>东游</li>
    <div>点不到我</div>
</ul>


<script src="js/jquery3.3.1.js"></script>
<script>
   //  筛选
    $(".list li").eq(1).css("color","red");
   console.log($(".list li").eq(1));
   $(".list li:eq(1)").css("fontSize","22px"); //也可以拿到同一个元素

   // 判断当前元素 是否有 指定的类名  返回bool值
   console.log($(".list li").hasClass("bgc"));//false

   // filter     按照指定要求找人
    $(".list li").filter('.hong').css('color','red');

  //is  返回 bool值
    $(".list ").children().click(function () {
        console.log($(this).is("li"));// 判断当前的元素 是否是li
    })

   //map    遍历每个子元素    操作数组
     $(".list li").map(function (i) {
         console.log(i); //下标
        // console.log($(this)); //每一个数组的子元素
         console.log($(this).html())
     })
    // has      参数是元素  查找有指定元素 的元素
    $(".list li").has("ul").css("background",'blue');
    //slice    截取数组中的 部分   和js中一样
   console.log($(".list li").slice(0, 1).html()); //水壶

</script>
```

#####   7.文档操作

   追加 操作

​    $(".parent").append(div);// 父元素中 追加子元素  末尾追加
​    $(".parent").prepend(div);    //在父元素中  追加  在开头追加

​     div.appendTo(".parent");   //子 追加到父元素  末尾追加
​     div.prependTo(".parent");         // 子元素追加到父元素中  在开头追加

```html
<style>
        /* */
        .parent div{
            display: inline-block;
            width: 100px;
            height: 100px;
            margin:10px;
            border:1px solid  red;
        }
    </style>
</head>
<body>
<button>添加</button>
<div class="parent">
        <div>0</div>
</div>
<script src="js/jquery3.3.1.js"></script>
<script>
    var i=0
 $("button").click(function () {
     //创建元素
     var div=$("<div class='son'></div>");
     i++;
     div.html(i)
     //2.追加
     // $(".parent").append(div);// 父元素中 追加子元素  末尾追加
     //$(".parent").prepend(div);    //在父元素中  追加  在开头追加

     //div.appendTo(".parent");   //子 追加到父元素  末尾追加
     div.prependTo(".parent");         // 子元素追加到父元素中  在开头追加

 })
</script>
```

### day03=============================================

####  1.文档插入之兄弟篇

```html
 <style>
        /* */
        .parent{
            border:1px solid #ccc;
            min-height: 400px;
            padding: 20px;
            margin: 10px;
            overflow: hidden;
        }
        .parent  div{
            width: 100px;height: 100px;
            background-color: aqua;
            margin: 10px;
            float: left;
        }
    </style>
</head>
<body>
<button>添加</button>
<div class="parent">
    <div class="box">我的之前就有的</div>
</div>
<script src="js/jquery3.3.1.js"></script>
<script>
    $("button").click(function () {
        var div=$("<div>我是新来的</div>")
        //$(".box").after(div);// 在当前元素 后面插入新元素
       // $(".box").before(div);  //在当前元素  前面插入元素

      //  div.insertBefore($(".box"));// 新元素插入到 老元素之前
        div.insertAfter($(".box")); //新元素插入到 老元素之后
    })
```

#### 2包裹系列

​      .wrap(parent) 给每个 元素 添加一个父元素

​      .wrapAll(parent)  给匹配的所有的元素 添加一个父元素

​      .unwrap(parent)  删除父元素

​      .wrapinner(元素)  给当前元素下的文本添加一个元素

```html
<div>hello</div>
<div>world</div>

<p>
    <span>1</span>
    <span>2</span>
    <span>3</span>
</p>
<script src="js/jquery3.3.1.js"></script>
<script>
    //  给匹配的每个div 每个都加上一个 父元素
   var parent=$("<div class='parent'></div>")
 //  $("div").wrap(parent)

    //将所有的匹配的元素 添加到一个父元素中
    $("div").wrapAll(parent);

   //移出父元素
    $("span").unwrap("p");
    //处理文本   里面的文本添加一个 元素
    $("span").wrapInner("<b></b>")
</script>
```

#### 3.替换

  $("xxx").replaceWith(div)   老替换新   div是新的元素  

   div .replaceAll($("xxx"))   新的替换老的   新找新的      

```html
 <style>
        /* */
        .parent{
            border:1px solid #ccc;
            min-height: 400px;
            padding: 20px;
            margin: 10px;
            overflow: hidden;
        }
        .parent  div{
            width: 100px;height: 100px;
            background-color: aqua;
            margin: 10px;
            float: left;
        }
    </style>
</head>
<body>
<button>添加</button>
<div class="parent">
    <div class="box">我的之前就有的</div>
</div>

<script src="js/jquery3.3.1.js"></script>
<script>
    $("button").click(function () {
        var div=$("<div>我是替换你的</div>")
            //找到原有的元素    替换新的元素
          //  $(".box").replaceWith(div) // 老替换新

        //先找到新的   去替换老的
             div.replaceAll($(".box"))  // 新替换老
    })
</script>
```

#### 4.删除

```js
//删除  在案例04中
$(".box").remove()
$(".box").remove("p");   //删除定义的元素
        // $(".box").detach("p");  会保留一些数据
```

#### 5.克隆

​	 .clone();// 浅克隆    只能复制元素 不能复制事件

​         .clone(true)  //深克隆   即复制元素    又复制事件

```html
 img{
      width: 200px;
      cursor: pointer;
  }
        .main{
            border:1px solid #ccc;
            min-height: 200px;
            margin: 10px;
        }
    </style>
</head>
<body>
<h1>选择结婚对象</h1>
<div class="main">
    <img src="" alt="">
</div>
<div class="parent">
    <img src="img/01.jpg" alt="" title="带你去美国拿绿卡">
    <img src="img/02.jpg" alt=""  title="感受不一样的人生">
    <img src="img/03.jpg" alt="" title="少活30年">
    <img src="img/04.jpg" alt="" title="家里有矿">
</div>

<script src="js/jquery3.3.1.js"></script>
<script>
   $(".parent img").click(function () {
       alert("恭喜 早生贵子");
            // 1浅克隆     只能复制元素 不能复制事件
       // var copy=$(this).clone();// 克隆一份自己出来
      //将原有的Img  替换为copy
       // $(".main img").replaceWith(copy);//当前这种克隆

       //  2深克隆  即复制元素    又复制事件
       var copy=$(this).clone(true);
       $(".main img").replaceWith(copy);
   })
```

#### 6.加载

​    window.onload()  vs $("document").ready()的区别

​       前者:  只能绑定一次    当网页的全部静态资源(html/css/js/img ...) 才执行

​       后者:  可以绑定多次     只需要加载html/js 就会被执行

```js
<script>
    //特点  等待静态资源 全部加载完成  才执行
    // 只能执行 一次
   window.onload=function () {
        alert("执行1次了")
   }

    window.onload=function () {
        alert("执行2次了")
    }
    //  ready   每个事件 都会去执行
    $(document).ready(function () {
        alert(" ready 执行了一次了")
    })
    $(document).ready(function () {
        alert(" ready 执行了2次了")
    })
    $(document).ready(function () {
        alert(" ready 执行了3次了")
    })
</script>
```

#### 7.jq的事件

​    1.on绑定事件  

```js
<button>添加事件</button>
<button>移除事件</button>

<script src="js/jquery3.3.1.js"></script>
<script>
    // 默认的click事件  可以绑定多个事件函数
/*  $("button:first").click(function () {
      console.log("事件111")
  })
  */
    $("button:first").click(function () {
        console.log("事件222")
    })

     $("button:first").on("click",function () {
         console.log("事件111")
     })
    $("button:first").on("click",function () {
        console.log("事件333")
    })
    // 移除单击事件
     $("button:last").on("click",function () {
         $("button:first").off("click");// 移除成功
     })
```

####  on的事件代理

​        xxx.on("事件名","事件代理对象",执行函数)

​       优点   减少事件绑定 提高性能

​      事件代理对象=>  指定的子元素

```html
 <style>
        /* */
    div{
        display: flex;
        justify-content: center;
        align-items: center;
    }
        .parent{
            width: 400px;height: 400px;
            background-color: aqua;
        }
        .son{
            width: 200px;height: 200px;
            background-color: antiquewhite;
        }
        .box{
            width: 100px;height:100px;
            background-color: #a01a1f;
        }
    </style>
</head>
<body>
<div class="parent"> d1
    <div  class="son">d2
        <a href="" class="box">d3</a>
    </div>
    <div class="son">新的</div>
</div>

<script src="js/jquery3.3.1.js"></script>
<script>

    //阻止冒泡
 $(".box").click(function (e) {
      // e.stopPropagation(); //阻止冒泡
       //  e.preventDefault();// 阻止 a 事件跳转
     console.log($(this).html());

     return  false ;   //    也可以阻止冒泡
 })

 // 底层依然是  冒泡原理  给父元素绑定事件 依然会去监听子元素的情况
//on 的事件代替       指定子元素的监听
    // 从而 没有冒泡
    $(".parent ").on("click",".son",function () {
        console.log($(this).html());//可以实现
    })
</script>
```

##### one 一次事件绑定

```html
<button>一次性</button>
<script src="js/jquery3.3.1.js"></script>
<script>

$("button").one("click",function () {
    console.log("点我一次")
})
</script>
```

##### trigger事件

​	  代替用户执行 事件

```html
<button class="all">执行所有</button>
<div>
    <button class="btn1">111</button>
    <button class="btn2">111</button>
    <button class="btn3">111</button>
</div>

<script src="js/jquery3.3.1.js"></script>
<script>
   $(".btn1").click(function () {
       console.log("点击了按钮111")
   })
   $(".btn2").click(function () {
       console.log("点击了按钮111")
   })
   //
   $(".btn3").click(function () {
       location.href="https://www.kugou.com/yy/rank/home/1-44615.html?from=rank";
   })
    $(".all").click(function () {
                //代替 用户 触发执行 js事件
               // $(".btn3").trigger('click')
            $(".btn2").trigger("click")
            $(".btn1").trigger("click")
        }
        )
</script>
```

#####   hover()事件 

​     相当于鼠标移入移出

```html
  <style>
        /* */
        div{
            width: 200px;height: 200px;
            background-color: aqua;
        }
        .a{
            border-radius: 50%;
            background-color:aquamarine;
        }
    </style>
</head>
<body>
<div>
</div>

<script src="js/jquery3.3.1.js"></script>
<script>
    /*    $("div").mouseover(function () {
            $(this).addClass("a")
        }).mouseout(function () {
            $(this).removeClass("a")
        })*/

    // hover  相当于鼠标的移入移出
      $("div").hover(function () {
          //鼠标移入
          $(this).addClass("a")
      },function () {
          //鼠标移出
          $(this).removeClass("a")
      })
```

##### toggle()方法

​	实现 显示或者消失  可以添加过渡性效果

​    toggle(时间,过度的函数,回调函数)

```html
  <style>
        /* */  div{
            width: 200px;height: 200px;
            background-color: aqua;
        }

    </style>
</head>
<body>
<button>点我</button>
<div></div>
<script src="js/jquery3.3.1.js"></script>
<script>
   $("button").click(function () {
       // 不给参数 默认 显示 隐藏
       //$("div").toggle()
       //            执行的时间 过程    执行完成之后的函数
       $("div").toggle(3000,'linear',function () {
           alert("动画执行成功了");
       });
   })
</script>
```

####  特效

1. 原理    修改高度 宽度 透明度

   ```
    1.$("div").show(500,'linear');   显示 
    2 $("div").hide(500);   隐藏       
    3  $("div").toggle(500);
   ```

 2.原理

​	 高度设置 显示或者隐藏

```
 $("div").slideDown(500,'linear');
 $("div").slideUp(500);
 $("div").slideToggle(500); 
```

 3.修改透明度原理

```
 $("div").fadeIn(500,'linear');
 $("div").fadeOut(500);
 $("div").fadeToggle(500);
```

#### day04=========================================================

####  1.动画

​     1.  xxx.animate({动画属性},执行时间,执行过程的函数,执行完的函数)

​             不是所有的属性都需要写

​     2.  xxx.animate().animate()...动画队列 会按照一个一个的动画顺序执行

​     3. xxx.delay(n)   延迟n毫秒执行

​     4.xxx.stop(bool,bool)停止动画	  具体情况如下

```js
   $(this).stop();// 停止当前的动画  立马执行队列中下一个动画
   $(this).stop(false,true); //立马结束掉动画的过程 属性还是会变
   $(this).stop(false,false); // 默认值 等于不加参数
   $(this).stop(true,false); //清空队列 ,当前动画也停止
   $(this).stop(true,true); //清空队列 ,当前动画过程立马结束
})
```
```html
<style>
        /* */
        .d1{
            width: 100px;
            height: 100px;
            background-color: aqua;
            position: absolute;

        }
        .d2{
            width: 100px;
            height: 100px;
            background-color: #a01a1f;
            position: absolute;
            top: 200px;
        }
    </style>
</head>
<body>
<div class="d1"></div>
<div class="d2"></div>

<script src="js/jquery3.3.1.js"></script>
<script>
    $(".d1").click(function () {
        //        第一个参数 是定义动画的 属性
        $(this).animate({
            // 动画属性 写在一个animate中 会一口气全部执行
            left:1000, // 可以省略 引号和 px
            bottom:300,
            width:"200px", //加上也可以说
        },500,'linear',function () {
            //执行动画完成之后 可以执行的函数
            alert("动画执行结束了")
        })
    })
    $(".d2").click(function () {
        $(this).animate({left:1000},5000)//往右
            .animate({top:400},5000)// 往下
            .animate({left:0},5000).delay(2000)  //队列延迟执行
            .animate({top:200},5000)
    })
    // 停止动画 可以防止用户交互次数过多
    $(".d2").mouseover(function () {
         //$(this).stop();// 停止当前的动画  立马执行队列中下一个动画
      //  $(this).stop(false,true); //立马结束掉动画的过程 属性还是会变
       // $(this).stop(false,false); // 默认值 等于不加参数
      //  $(this).stop(true,false); //清空队列 ,当前动画也停止
        $(this).stop(true,true); //清空队列 ,当前动画过程立马结束
    })
</script>
```

#### 2.位置有关

  xxx..offset() ;当前元素到页面左上角的 left 和top对象 想要拿则需要

​         xxx.offset().left:左边的距离    xxx.offset().top:到顶部的距离

 xxx.position() :当前元素的位置的left和top值 

 xxx.scorllTop() :  滚动的距离     

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
        body{
            min-height: 2000px;
        }
        div{
            width: 100px;
            height: 100px;
            background-color: aqua;
            position: absolute;
            left: 100px;
            top: 50px;
            margin: 20px;
        }
        a{
            position: fixed;
            right: 100px;
            bottom: 60px;
        }
    </style>
</head>
<body>
<div></div>
<a href="" style="display: none">返回页面顶部</a>
<script src="js/jquery3.3.1.js"></script>
<script>
   $(function () {
       //返回的 当前的元素到页面 左边和顶部的距离
       //以对象的形式存放在offset()方法中
       console.log($("div").offset()); //{top: 70, left: 120}
       console.log($("div").offset()["left"]); //120
       console.log($("div").offset().left); //120  通过.的形式获取

        // 返回的是 定位中端left 和 top
       console.log($("div").position()); //{top: 50, left: 100}
   })
    $(window).scroll(function () {
        console.log($(this).scrollTop());//滚动的高度
        if($(this).scrollTop()>50)
        $("a").css("display",'block');
        else 
            $("a").css("display",'none');
    })
</script>
</body>
</html>
```

####  3.尺寸

​    .width() //元素的宽度

   .innerWidth())// 元素的宽+padding

   .outerWidth())// 元素的高+padding+border

   高度类似

```html
<style>
        /* */
        div{
            width: 100px;
            height: 100px;
            background-color: aqua;
            position: absolute;
            left: 100px;
            top: 50px;
            margin: 20px;
            padding: 10px 5px;
            border: 5px solid #000;
        }
    </style>
</head>
<body>
<div></div>

<script src="js/jquery3.3.1.js"></script>
<script>
  $("div").click(function () {
      // width和hieght 只是内容 的宽高 不会包含padding 和边框
      console.log($(this).height())//元素的高度   100
      console.log($(this).width())//元素的宽度

      console.log($(this).innerHeight())// 元素的高+padding 120
      console.log($(this).innerWidth())// 元素的宽+padding

      console.log($(this).outerHeight())// 元素的高+padding+border 130
      console.log($(this).outerWidth())// 元素的高+padding+border


  })
</script>
```

#### 4.补充事件

 	 键盘操作 事件

​       keydown  按下

​       keyup     弹起

​       e.keycode 获取键盘的按键编码	

```html
<input type="text">

<script src="js/jquery3.3.1.js"></script>
<script>
   $(function () {
       //键盘按下时的事件
       $("input").keydown(function (e) {
           // 获取键盘的 编号
           console.log(e.keyCode)
           if(e.keyCode==13){// 13 是 回车键
               alert("发射导弹")

              // location.replace("http://www.baidu.com");
           }
           // 键盘 弹起来 事件  
       }).keyup(function () {
           $(this).val("");
       })
   })
</script>
```

#### each() 和$.each() 区别

   xxx.each()   数组遍历

   $.each(obj,function(){})  obj:可以是数组也可以是是对象。。。  更强大

```html
 <style>
        /* */
        ul{
            list-style: none;
        }
        ul li{
            width: 200px;
            height: 200px;
            float: left;
            margin:10px;
            background-color: aqua;
        }
    </style>
</head>
<body>
<ul>
    <li>1</li>
    <li>2</li>
    <li>3</li>
    <li>4</li>
    <li>5</li>
    <li>6</li>
    <li>7</li>
    <li>8</li>
</ul>

<script src="js/jquery3.3.1.js"></script>
<script>

    var len=$("ul li"); //8个li
    console.log(len);
    //最开始的写法
   /* for(var i=0;i<len.length;i++){
        len[i].style.opacity=(i+1)/10;
    }*/
   // each 写法
   /* len.each(function (index,value) { // len[index]
        //index => 下标
        //value=>  len[index] =>当前的元素
         value.style.opacity=(index+1)/10;
    })*/
    //$.each   更强大 可以传数组或者是其他的对象
    $.each(len,function (index,value) {
        value.style.opacity=(index+1)/10;
    })
    //还可以    遍历对象
    $.each( { name: "John", lang: "JS" }, function(key,value){
        // key=> name,lang ...
        // value =>  john  ,  Js ...
        alert(key+":"+value);  //
    });
</script>
```

#### 多库共存

​    如果遇到$序号有冲突时，可以进行替换

```html
<button>点我</button>
<script src="js/jquery3.3.1.js"></script>
<script>
    console.log($)
    console.log(jQuery)
    console.log($===jQuery); //
    jQuery("button").click(function () {
        console.log("我被点了") ;//可以执行
    })
    //比如 使用其他  框架时 $符号冲突  可以使用其他的符号代替
    var xu=jQuery.noConflict();//
    console.log(xu===jQuery)
    xu("button").click(function () {
        console.log("我被点了22222") ;// 可以实现替换
    })

   /* var $=jQuery.noConflict();
    $("button").click(function () {
        console.log("我被点了333333") ;// 可以实现替换
    })*/
    jQuery.noConflict();  //禁止了 $
    //  console.log($("button")) ;//
    (function($) {
        $(function() {  //  通过匿名自调函数 实现继续使用$
          //测试 调用 $
            console.log($("button")) ;
             $("button").click(function () {
                console.log("我被点了55555") ;// 可以实现替换
            })
        });
    })(jQuery);

</script>
```

####  自定义插件函数

   01.js   在jQuery对象中去添加方法 只能jQuery使用

```js
//定义一个全局的函数
jQuery.xu=function () {
     console.log("我是隔壁老徐");
}
```

02.js  原型中添加新的方法     处理jQuery其他的 元素都可以使用的方法

```js
//在  原型   中去挂载一个 全局的自定义函数
//所有人都可以用
jQuery.fn.xu1=function () {
    console.log("这个函数 jq中的人都可以使用")
}
```

简单的 自定义函数封装

```js
// bgc  $(xxx).bgc("") => 背景颜色
//       $(xxx).bgc("red") 设置当前元素的背景颜色了
jQuery.fn.bgc=function (color) {
    if(color==""){
       return   this.css("backgroundColor")
    }else{
        return  this.css("backgroundColor",color);
    }
}
// sum   遍历的 数字相加
jQuery.fn.sum=function () {
    var sum=0;
    this.each(function (key,value) {
        //  取整 进行相加
        sum+=parseInt($(value).html());
    })
    return  sum;
}
```

#### 插件拓展

  jquery本身来说功能是比较少的，如果想要其他炫酷的效果 可以借助于jq的一些插件

  jquery插件库: <http://www.jq22.com/>

  <http://www.htmleaf.com/>

或者自己百度搜索也可以 

使用注意: 需要先引入jquery.js 再引入插件.js

​                 如果有.css文件 也需要一并引入

#### 1.懒加载(优化)

​    如果网站中 图片过多 一口气加载完  消耗的时间多的话 用户等待的时间也会很久 影响体验

​      

![1597132345568](assets/1597132345568.png)

##### EasyLazyload.js 使用说明

  1.需要下载EasyLazyload.js 文件 先要引入jquery.js

```js
<script src="jquery.min.js"></script>
<script src="EasyLazyload.min.js"></script>
```

   如果说需要下载的时候要钱  则 可以去源码中获取对应的js文件

​		1.

![1597135524561](assets/1597135524561.png)

  		 2.![1597135473897](assets/1597135473897.png)

   2.所有 的需要懒加载的图片 src路径改为 data-lazy-src="xxx"

   3.需要调用全局的lazyLoadInit(）

```js
 lazyLoadInit({
        coverColor:"white",
        coverDiv:"<h1>test</h1>",
        offsetBottom:0,
        offsetTopm:0,
        showTime:1100,
        onLoadBackEnd:function(i,e){
            console.log("onLoadBackEnd:"+i);
        }
        ,onLoadBackStart:function(i,e){
            console.log("onLoadBackStart:"+i);
        }
    });
```

#####   参数说明

  1.coverColor**：图片即将显示时覆盖层的颜色

1. **coverDiv**：图片即将显示时覆盖层可显示的土自定义组件
2. **offsetBottom**：图片距离屏幕底部出现时间点的距离差值（注解：延迟加载图片会在图片顶部接触屏幕底部时出现，如果想要让图片顶部距离屏幕底部有一定距离时出现，请设置此值）
3. **offsetTopm**：图片距离屏幕底部出现时间点的距离差值（注解：同上，距离顶部）
4. **onLoadBackEnd**：图片已经完全出现时的回调函数，参数为（index，event）加载的图片下标，以及dom对象（dom对象为jquerydom或zeptodom对象）
5. **onLoadBackStart**：图片已经下载完成，即将开始显示时的回调函数（参数同上）

  优点

```
  EasyLazyload.js 是真延迟加载 而且不会对样式有任何影响。
  队列式加载，不会影响页面效率。
  不需要设置任何宽高，简单易用
```

