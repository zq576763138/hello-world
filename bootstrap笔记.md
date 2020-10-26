### bootstrap响应式框架

####  1.响应式

​        一个网站可以根据浏览器设备不同 自动的改变网页的布局。

​        优点: 一个项目 可以同时匹配多个客户端 运营 开发 维护等角度都有优点

​                 官网、小型 简约风格 

​         缺点:没有办法去使用大型的复杂的网站、还是会分开写

#### 2.响应式原理

​     css3媒体查询 注意事项等 去css3模块复习  略

#### 3.bootstrap

##### 1.下载

<https://v3.bootcss.com/getting-started/>

![1597216567023](assets/1597216567023.png)

##### 2.新建模板

   如果是开发过程中建议使用cdn网址  加速更快一点

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <!-- 上述3个meta标签*必须*放在最前面，任何其他内容都*必须*跟随其后！ -->
    <title>模板</title>
    <!-- Bootstrap -->
    <link href="css/bootstrap.min.css" rel="stylesheet">

    <!-- HTML5 shim 和 Respond.js 是为了让 IE8 支持 HTML5 元素和媒体查询（media queries）功能 -->
    <!-- 警告：通过 file:// 协议（就是直接将 html 页面拖拽到浏览器中）访问页面时 Respond.js 不起作用 -->
    <!--[if lt IE 9]>
    <script src="js/html5shiv.min.js"></script>
    <script src="js/respond.min.js"></script>
    <![endif]-->
</head>
<body>





<!-- jQuery (Bootstrap 的所有 JavaScript 插件都依赖 jQuery，所以必须放在前边) -->
<script src="js/jquery.min.js"></script>
<!-- 加载 Bootstrap 的所有 JavaScript 插件。你也可以根据需要只加载单个插件。 -->
<script src="js/bootstrap.min.js"></script>
</body>
</html>
```

安装提示的插件

![1597216888372](assets/1597216888372.png)



##### 3.样式

###### 1.基本排版

​     text排版

​     字母大小写转换

​     列表

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <!-- 上述3个meta标签*必须*放在最前面，任何其他内容都*必须*跟随其后！ -->
    <title>模板</title>
    <!-- Bootstrap -->
    <link href="css/bootstrap.min.css" rel="stylesheet">

    <!-- HTML5 shim 和 Respond.js 是为了让 IE8 支持 HTML5 元素和媒体查询（media queries）功能 -->
    <!-- 警告：通过 file:// 协议（就是直接将 html 页面拖拽到浏览器中）访问页面时 Respond.js 不起作用 -->
    <!--[if lt IE 9]>
    <script src="js/html5shiv.min.js"></script>
    <script src="js/respond.min.js"></script>
    <![endif]-->
</head>
<body>
<h1>排版</h1>
<h1>h1. Bootstrap heading <small>Secondary text</small></h1>
<h1>水平排列</h1>
<p class="text-left">Left aligned text.</p>
<p class="text-center">Center aligned text.</p>
<p class="text-right">Right aligned text.</p>
<p class="text-justify">Justified text.</p>
<p class="text-nowrap">No wrap text.</p>
<h1>字体的大小写转换</h1>
<p class="text-lowercase">Lowercased text.</p>
<p class="text-uppercase">Uppercased text.</p>
<p class="text-capitalize">Capitalized text.</p>
<h1>列表</h1>
<ul class="list-unstyled">
    <li>张飞</li>
    <li>张三丰</li>
    <li>隔壁老张
        <ul class="list-inline">
            <li>班级web01</li>
            <li>年龄48</li>
            <li>身高148</li>
             <li>体重148</li>
        </ul>
    </li>
</ul>
<!--设置水平排列 -->
<dl class="dl-horizontal">
    <dt>悯农</dt>
    <dd>锄禾日当午、、、、</dd>
</dl>



<!-- jQuery (Bootstrap 的所有 JavaScript 插件都依赖 jQuery，所以必须放在前边) -->
<script src="js/jquery.min.js"></script>
<!-- 加载 Bootstrap 的所有 JavaScript 插件。你也可以根据需要只加载单个插件。 -->
<script src="js/bootstrap.min.js"></script>
</body>
</html>
```

###### 2.table

```html
<h1>条纹状的表格</h1>
<table class="table table-striped">
    <thead>
    <tr class="danger">
        <th>编号</th>
        <th>姓名</th>
        <th>年龄</th>
    </tr>
    </thead>
    <tbody>
    <tr>
        <td>01</td>
        <td>隔壁张</td>
        <td>28</td>
    </tr>
    <tr>
        <td>02</td>
        <td>隔壁徐</td>
        <td>18</td>
    </tr>
    <tr>
        <td>03</td>
        <td>隔壁王</td>
        <td>48</td>
    </tr>
    <tr>
        <td>04</td>
        <td>隔壁沈</td>
        <td>38</td>
    </tr>
    </tbody>
</table>
```

###### 3.按钮

```html
<h1>普通的按钮</h1>
<button class="btn btn-default">普通按钮</button>
<button class="btn btn-success">成功按钮</button>
<button class="btn btn-danger">危险按钮</button>
<button class="btn btn-info">一般按钮</button>
<button class="btn btn-warning btn_self">警告按钮</button>
<h1>不同大小的按钮</h1>
<button class="btn btn-warning btn-lg">大哒哒哒哒</button>
<button class="btn btn-warning ">大哒哒哒哒</button>
<button class="btn btn-warning btn-sm">中等的</button>
<button class="btn btn-warning btn-xs">超小</button>

<h1>块级按钮</h1>
<button class="btn-block btn-lg btn-danger active">块级按钮</button>
<h1>a链接可以使用btn</h1>
<a href="" class="btn-block btn-lg btn-info active text-center">链接按钮</a>
<h1>禁用</h1>
<button class="btn btn-primary " disabled>注册</button>
```

###### 4.图片

```html
<h1>图片</h1>
<!--响应式-->
<img src="01.jpg" class="img-responsive" alt="">
<!--圆 同时也是响应式-->
<img src="01.jpg" class="img-circle img-responsive" alt="">
<!--圆弧-->
<img src="01.jpg" class="img-rounded" alt="">
<!--下面的 自带响应式-->
<img src="01.jpg" class="img-thumbnail" alt="">
```

###### 5.辅助类

​    关闭按钮

​     三角形

​     浮动、清除浮动

```html
<!--背景和 字体颜色的类-->
<h3 class="bg-info  text-primary">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Blanditiis dicta distinctio dolores enim et incidunt non veritatis! Ad aut debitis, distinctio eum eveniet impedit nulla odio, optio quisquam, ratione saepe.</h3>

<h1>关闭按钮</h1>
<button type="button" class="close" ><span >&times;</span></button>
<h1>三角字符</h1>
<span class="caret"></span>
<h1>浮动  和清除浮动</h1>
<div class="bg-success clearfix">
    <div class="pull-left bg-info">我是左边的</div>
    <div class="pull-right bg-danger">我是右边的</div>
</div>
<div class="hidden">我是隐藏的</div>
<div class="show">我是现实的</div>
<h1 class="center-block" style="width: 500px">有宽度下的居中</h1>
```

###### 6.代码提示工具

​    用来检测html结构是否遵循 boot规则

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <!-- 上述3个meta标签*必须*放在最前面，任何其他内容都*必须*跟随其后！ -->
    <title>模板</title>
    <!-- Bootstrap -->
    <link href="css/bootstrap.min.css" rel="stylesheet">

    <!-- HTML5 shim 和 Respond.js 是为了让 IE8 支持 HTML5 元素和媒体查询（media queries）功能 -->
    <!-- 警告：通过 file:// 协议（就是直接将 html 页面拖拽到浏览器中）访问页面时 Respond.js 不起作用 -->
    <!--[if lt IE 9]>
    <script src="js/html5shiv.min.js"></script>
    <script src="js/respond.min.js"></script>
    <![endif]-->
</head>
<body>
<!--测试: 在boot中 按钮必须要添加type类型的值 否则boolint会报错 -->
<button type="button">点我</button>

<!-- jQuery (Bootstrap 的所有 JavaScript 插件都依赖 jQuery，所以必须放在前边) -->
<script src="js/jquery.min.js"></script>
<!-- 加载 Bootstrap 的所有 JavaScript 插件。你也可以根据需要只加载单个插件。 -->
<script src="js/bootstrap.min.js"></script>
<script src="js/bootlint.js"></script>
<script>
/*  (function(){var s=document.createElement("script");s.onload=function(){bootlint.showLintReportForCurrentDocument([]);};s.src="https://stackpath.bootstrapcdn.com/bootlint/latest/bootlint.min.js";document.body.appendChild(s)})();*/
//上面代码拆解为  新建一个script标签 导入bootlint.js文件 执行下面的方法
bootlint.showLintReportForCurrentDocument([])
</script>
</body>
</html>
```

###### 7.容器

   在容器中可以进行划分为12列 供栅格系统响应式

   可以给定宽 或者是100%

```html
<!--适用于pc端-->
<!--如果使用栅格系统(后面一个案例)   屏幕不同的宽度的情况下 会定宽 宽度也是不一样的-->
<div class="container">
    <h1 class="bg-success">测试container的容器的宽度</h1>
</div>
<!--适用于移动端-->
<!-- 无论在哪个屏幕下 宽度都是100%-->
<div class="container-fluid">
    <h1 class="bg-success">测试container-fluid的容器的宽度</h1>
</div>
<!--默认也去100%显示-->
<h1 class="bg-success">默认</h1>
```

#### 4.栅格系统

#####  1.原理是css3的媒体查询

​    作用是基于不同的浏览器宽度 显示不同的元素样式的宽度

​     通过给每一行(.row)设置为12列，通过在不同屏幕下占比列的数量的改变从而达到宽度的变化

​      不同的屏幕对应的类名前缀不同(b3)

​      .col-xs-n  : 超小屏=》手机

​      .col-sm-n:小屏  =》 pad

​      .col-md-n =》 中等屏  笔记本

​      .col-lg-n  =》 大屏  

![1597224506425](assets/1597224506425.png)

##### 2.使用:

   1.最外围必须添加一个容器:

​    2.每一行都必须要添加一个.row 对应的是行

```html
  <style>
        div{
            border:1px solid #ccc;
        }
    </style>
</head>
<body>
<div class="container">
    <!--1 : 2 : 1 比例-->
    <div class="row">
        <!--.col-md对应的中等屏幕 992-1200-->
        <div class="col-md-3 bg-success">1</div>
        <div class="col-md-6 bg-danger">2</div>
        <div class="col-md-3 bg-info">3</div>
    </div>
    <!--1:1:1-->
    <div class="row">
        <!--.col-md对应的中等屏幕 992-1200-->
        <div class="col-md-4 bg-success">1</div>
        <div class="col-md-4 bg-danger">2</div>
        <div class="col-md-4 bg-info">3</div>
    </div>
    <!--响应式 操作-->
    <!--设置在pc中占比 1/4 在 pad端占比1/2-->
    <div class="row">
        <div class="col-md-3 col-sm-6 bg-success">11</div>
        <div class="col-md-3 col-sm-6 bg-danger">22</div>
        <div class="col-md-3 col-sm-6 bg-info">33</div>
        <div class="col-md-3 col-sm-6 bg-warning">44</div>
    </div>
    <!--在手机端100% 显示 在Pad端 显示一半 在pc端显示1/3 超大屏1/4-->
    <div class="row">
        <div class="bg-primary col-xs-12 col-sm-6 col-md-4 col-lg-3">响应式</div>
    </div>
    <!--规律 如果大屏没有设置占比宽度 则会按照上一个小屏幕设置的宽度进行相应
        延伸性
    -->
    <div class="row">
        <div class="col-xs-6 col-sm-6 col-md-6 col-lg-6">永远占一半</div>
    </div>
    <div class="row">
        <div class="col-xs-6 ">永远占一半</div>
    </div>
</div>
```

##### 5.列偏移

​     实现原理是margin  具备延伸性

```html
<h1> 列偏移 实现原理是margin  具备延伸性</h1>
<div class="container">

    <div class="row">
        <div class="col-xs-3 col-md-6 col-md-offset-3">我要去中间</div>
    </div>
    <!--任意屏幕下都移动3列 -->
    <div class="row ">
        <div class="col-xs-offset-3 col-xs-6">
            任意屏幕都移动
        </div>
    </div>
 <!--如果偏移的列数 过多 则会超出范围-->
    <div class="row">
        <div class="col-xs-6 col-lg-offset-10 ">我占2列</div>
    </div>
</div>
```

##### 6.列排序 

   列排序  原理是通过相对定位实现的

```html
<h1>列排序  原理是通过相对定位实现的</h1>
<div class="container">
    <!--默认排列-->
    <div class="row">
        <div class="col-xs-5">我是左边的</div>
        <div class="col-xs-7">我是右边的</div>
    </div>
    <!--
         push  ->推  left给正值
         pull ->拉   right给正值
    -->
     <div class="row">
         <div class="col-xs-5 col col-xs-push-7">我是左边的</div>
         <div class="col-xs-7 col col-xs-pull-5">我是右边的</div>
     </div>
     <div class="row">
         <!--在Pc端 推2列-->
         <div class="col-xs-5 col-md-push-2 ">我站5列</div>

     </div>
    <!--多了的 也会超过去-->
    <div class="row">
        <div class="col-xs-6 col-lg-push-10 ">我占2列</div>
    </div>

    <div class="row">
        <div class="col-xs-6 col-xs-offset-3 col-xs-push-3">我在哪</div>
    </div>
</div>
```

##### 7.显示和隐藏

   如果说希望一个元素在指定的屏幕宽度下 显示或者不显示 可以通过类去设置

   .visible-xxx-xx     写什么屏幕就只在当前的屏幕下显示

   .hidden-xxx         写什么屏幕就只在当前的屏幕下隐藏 

```html
<h1>列排序  原理是通过相对定位实现的</h1>
<div class="container">
    <div class="row">
        <div class="col-md-3">左边</div>
        <div class="col-md-6">中间</div>
        <!--最右边到了 pad端 隐藏起来-->
        <div class="col-md-3  hidden-sm">右边</div>
    </div>
    <div class="row">
        <div class="col-md-3">左边</div>
        <div class="col-md-6">中间</div>
        <!--最右边 只在lg屏下显示 -->
        <!--<div class="col-md-3 visible-lg">右边</div>-->
        <!--使用 hidden- 替换-->
        <div class="col-md-3 hidden-xs hidden-sm hidden-md">右边</div>
    </div>
</div>
```

##### 8.表单

​     1.每一个组件外围都有一个div包裹 类名是form-group bootstrap里表单控件必须加label

​        input的类名是 form-control

​     2.内联表单 form-inline给form添加的类

​     3.可以在在栅格系统中使用表单 

​     4.可以添加额外的图标    外围div需要加 has-feedback类(相对定位)

​         通过字体的形式添加span 并添加类 form-control-feedback（绝对定位） 

```html
<h1>默认的表单</h1>
<form action="" method="post" role="form">
<!--每一个form的组件 都会按照 这个写法-->
    <div class="form-group">
        <label for="txt1"><h1>用户名:</h1></label>
        <input type="text" class="form-control" name="" id="txt1" placeholder="用户名">
    </div>
     <div class="form-group">
         <label for="pwd1">密&nbsp;&nbsp;&nbsp;码:</label>
         <input type="text" class="form-control" name="" id="pwd1" placeholder="用户名">
     </div>
    <div class="checkbox">
        <label>
            <input type="checkbox" disabled> 同意协议
        </label>
    </div>
    <!--提交按钮-->
    <button type="submit" class="btn btn-primary">Submit</button>
</form>
<h1>内联表单 form-inline给form添加的类 </h1>
<form action="" method="post" class="form-inline" role="form">
    <div class="form-group">
        <label for="txt">用户名:</label>
        <input type="text" class="form-control" name="" id="txt" placeholder="用户名">
    </div>
    <div class="form-group">
        <label for="pwd">密&nbsp;&nbsp;&nbsp;码:</label>
        <input type="text" class="form-control" name="" id="pwd" placeholder="用户名">
    </div>
    <div class="checkbox">
        <label>
            <input type="checkbox"> 同意协议
        </label>
    </div>
    <!--提交按钮-->
    <button type="submit" class="btn btn-primary">Submit</button>
</form>
<h1>在栅格系统中使用表单</h1>
<div class="container-fluid">
    <div class="row">
       <div class="col-md-6">
           <form action="" class="">
                   <div class="form-group has-success">
                       <label for="txt2"><h1>用户名:</h1></label>
                       <input type="text" class="form-control" name="" id="txt2" placeholder="用户名">
                       <span class="help-block">用户名必须是6-16为字母</span>
                   </div>
                   <div class="form-group has-error">
                       <label class="control-label" for="pwd2">密&nbsp;&nbsp;&nbsp;码:</label>
                       <input type="text" class="form-control" name="" id="pwd2" placeholder="用户名">
                       <span class="help-block">密码必须是6位数字</span>
                   </div>
           </form>
       </div>
    </div>
</div>
<h1>可以添加额外的图标</h1>
<form action="" class="">
    <div class="form-group has-success has-feedback">
        <label for="txt4">用户名:</label>
        <input type="text" class="form-control" name="" id="txt4" placeholder="用户名">
        <span class="glyphicon glyphicon-search form-control-feedback"></span>
        <span class="help-block">用户名必须是6-16为字母</span>
    </div>
    <!-- 要想添加标识 想要 在外围加 has-feedback -->
    <div class="form-group has-error has-feedback">
        <label class="control-label" for="pwd4">密&nbsp;&nbsp;&nbsp;码:</label>
        <input type="text" class="form-control" name="" id="pwd4" placeholder="密码">
        <span class="glyphicon glyphicon-ok form-control-feedback"></span>
        <span class="help-block">密码必须是6位数字</span>
    </div>
    <!--测试-->
    <div class="form-group has-success has-feedback">
        <label class="control-label" for="inputSuccess2">Input with success</label>
        <input type="text" class="form-control" id="inputSuccess2" aria-describedby="inputSuccess2Status">
        <span class="glyphicon glyphicon-ok form-control-feedback" aria-hidden="true"></span>
        <span id="inputSuccess2Status" class="sr-only">(success)</span>
    </div>
</form>
```

### 组件

##### 9表单中的下拉菜单

​       data-toggle="dropdown"   直接不用写js  点击弹出显示
​      外围div 类名dropdown

```html
<h1>下拉菜单</h1>
  <!--
  data-toggle="dropdown"   直接不用写js  点击弹出显示
  外围div 类名dropdown

-->
<div class="dropdown">
    <button class="btn btn-default dropdown-toggle" type="button" id="dropdownMenu1" data-toggle="dropdown"  >
         下拉显示
        <span class="caret"></span>
    </button>
    <ul class="dropdown-menu" >
        <li class="dropdown-header">旅游景点</li>
        <li><a href="#">北京天安门</a></li>
        <li><a href="#">故宫颐和园</a></li>
        <li><a href="#">长城</a></li>
        <!--分割线-->
        <li role="separator" class="divider"></li>
        <!--禁用-->
        <li class="disabled"><a href="#" >Separated link</a></li>
    </ul>
</div>
```

##### 10按钮组合

​    案例中有各种情况测试

```html
<!--
    最外围的div  类btn-group

-->
<h1>基本按钮组</h1>
<div class="btn-group btn-group-lg">
    <button type="button" class="btn btn-default">Left</button>
    <button type="button" class="btn btn-default">Middle</button>
    <button type="button" class="btn btn-default">Right</button>
</div>
<h1>按钮组 链接</h1>
<div class="btn-group btn-group-lg">
    <a href="" class="btn btn-default"><span class="glyphicon glyphicon-step-backward"></span></a>
    <a href="" class="btn btn-default"><span class="glyphicon glyphicon-step-backward"></span></a>
    <a href="" class="btn btn-default"><span class="glyphicon glyphicon-step-backward"></span></a>
    <a href="" class="btn btn-default"><span class="glyphicon glyphicon-step-backward"></span></a>
</div>
<h1>按钮式下拉菜单</h1>
<!-- Single button -->
<div class="btn-group">
    <!--加了这个button  没有点击功能 可以去掉-->
    <button class="btn btn-default btn-lg">  请选择</button>
    <button type="button" class="btn btn-default dropdown-toggle btn-lg" data-toggle="dropdown" >
       <span class="caret"></span>
    </button>
    <ul class="dropdown-menu" >
        <li class="dropdown-header">旅游景点</li>
        <li><a href="#">北京天安门</a></li>
        <li><a href="#">故宫颐和园</a></li>
        <li><a href="#">长城</a></li>
        <!--分割线-->
        <li role="separator" class="divider"></li>
        <!--禁用-->
        <li class="disabled"><a href="#" >Separated link</a></li>
    </ul>
</div>
<h1>下拉菜单和 搜索框组合</h1>
<div class="container">
    <div class="row">
        <!--组合的最外围-->
        <div class="col-xs-6 col-xs-offset-3 input-group">
            <!--搜索框 任选一个 写在左边还是右边-->
            <input type="text" class="form-control">
            <div class="input-group-btn">

                <button class="btn btn-default  dropdown-toggle " data-toggle="dropdown">
                    请选择 <span class="caret"></span>
                </button>
                <ul class="dropdown-menu" >
                    <li class="dropdown-header">旅游景点</li>
                    <li><a href="#">北京天安门</a></li>
                    <li><a href="#">故宫颐和园</a></li>
                    <li><a href="#">长城</a></li>
                    <!--分割线-->
                    <li role="separator" class="divider"></li>
                    <!--禁用-->
                    <li class="disabled"><a href="#" >Separated link</a></li>
                </ul>
            </div>
            <input type="text" class="form-control">
        </div>
    </div>
</div>
```

##### 11.标签导航

 需要加基础类nav     标签页最外部是 nav-tabs 
 每一个 a 可以添加data-toggle="tab"  可以实现锚点功能
 对应的锚点的内容外围需要添加 tab-content类
 每个具体的锚点需要添加tab-pane

```html
<h1>标签导航</h1>
<!--
     nav-tabs 标签页
     每一个 a 可以添加data-toggle="tab"  可以实现锚点功能
     对应的锚点的内容外围需要添加 tab-content类
     每个具体的锚点需要添加tab-pane
     如果要实现带下拉菜单的导航 则需要注意
     data-toggle="tab" href="#d311" 这两个必须写在一块可以写在li 或者a中
-->
<div>
    <ul class="nav nav-tabs">
        <li  class="active"><a href="#d1" data-toggle="tab">首页</a></li>
        <li  class=""><a href="#d2" data-toggle="tab">起步</a></li>
        <li  class=""><a href="#d3" data-toggle="tab">组件</a></li>
    </ul>
    <div class="tab-content">
        <div class="tab-pane active" id="d1">
            首页:   Lorem ipsum dolor sit amet, consectetur adipisicing elit. A ab delectus earum eos est ex, excepturi illum ipsa iure iusto labore laborum molestiae natus neque nobis quos repellat temporibus, veniam.
        </div>
        <div class="tab-pane" id="d2">
            起步:   Lorem ipsum dolor sit amet, consectetur adipisicing elit. A ab delectus earum eos est ex, excepturi illum ipsa iure iusto labore laborum molestiae natus neque nobis quos repellat temporibus, veniam.
        </div>
        <div class="tab-pane" id="d3">
            组件:   Lorem ipsum dolor sit amet, consectetur adipisicing elit. A ab delectus earum eos est ex, excepturi illum ipsa iure iusto labore laborum molestiae natus neque nobis quos repellat temporibus, veniam.
        </div>
    </div>
</div>
<h1>胶囊式标签</h1>
<div>
    <!--nav-justified  变大-->
    <ul class="nav nav-pills nav-justified">
        <li  class="active"><a href="#d11" data-toggle="tab">首页</a></li>
        <li  class=""><a href="#d21" data-toggle="tab">起步</a></li>
        <li  class=""><a href="#d31" data-toggle="tab">组件</a></li>
    </ul>
    <div class="tab-content">
        <div class="tab-pane active" id="d11">
            首页:   Lorem ipsum dolor sit amet, consectetur adipisicing elit. A ab delectus earum eos est ex, excepturi illum ipsa iure iusto labore laborum molestiae natus neque nobis quos repellat temporibus, veniam.
        </div>
        <div class="tab-pane" id="d21">
            起步:   Lorem ipsum dolor sit amet, consectetur adipisicing elit. A ab delectus earum eos est ex, excepturi illum ipsa iure iusto labore laborum molestiae natus neque nobis quos repellat temporibus, veniam.
        </div>
        <div class="tab-pane" id="d31">
            组件:   Lorem ipsum dolor sit amet, consectetur adipisicing elit. A ab delectus earum eos est ex, excepturi illum ipsa iure iusto labore laborum molestiae natus neque nobis quos repellat temporibus, veniam.
        </div>
    </div>
</div>
<h1>带下拉菜单的导航标签</h1>
<div>
    <!--nav-justified  变大-->
    <ul class="nav nav-pills ">
        <li  class="active"><a href="#d111" data-toggle="tab">首页</a></li>
        <li  class=""><a href="#d211" data-toggle="tab">起步</a></li>
        <li  class="dropdown"  >
            <a href="" class="dropdown-toggle" data-toggle="dropdown" >组件 <span class="caret"></span></a>
            <ul class="dropdown-menu">
                <li><a href="#d311">按钮</a></li>
                <li><a href="">导航</a></li>
                <li><a href="">分页</a></li>
                <li><a href="">分页标签</a></li>
            </ul>
        </li>
    </ul>
    <div class="tab-content">
        <div class="tab-pane active" id="d111">
            首页:   Lorem ipsum dolor sit amet, consectetur adipisicing elit. A ab delectus earum eos est ex, excepturi illum ipsa iure iusto labore laborum molestiae natus neque nobis quos repellat temporibus, veniam.
        </div>
        <div class="tab-pane" id="d211">
            起步:   Lorem ipsum dolor sit amet, consectetur adipisicing elit. A ab delectus earum eos est ex, excepturi illum ipsa iure iusto labore laborum molestiae natus neque nobis quos repellat temporibus, veniam.
        </div>
        <div class="tab-pane" id="d311">
            组件:   Lorem ipsum dolor sit amet, consectetur adipisicing elit. A ab delectus earum eos est ex, excepturi illum ipsa iure iusto labore laborum molestiae natus neque nobis quos repellat temporibus, veniam.
        </div>
    </div>
</div>
```

##### 12.分页导航、标签、徽章

```html
<h1>分页导航</h1>
<nav aria-label="Page navigation">
    <ul class="pagination pagination-lg">
        <li>
            <a href="#" >
                <span >&laquo;</span>
            </a>
        </li>
        <li><a href="#">1</a></li>
        <li><a href="#">2</a></li>
        <li><a href="#">3</a></li>
        <li><a href="#">4</a></li>
        <li><a href="#">5</a></li>
        <li>
            <a href="#" aria-label="Next">
                <span aria-hidden="true">&raquo;</span>
            </a>
        </li>
    </ul>
</nav>
<h1>分页</h1>
<nav >
    <ul class="pager">
        <li><a href="#">Previous</a></li>
        <li><a href="#">Next</a></li>
    </ul>
</nav>
<h1>标签  类名:label</h1>
<h3>Example heading <span class="label label-default">New</span></h3>
<h1>徽章</h1>
<a href="#">Inbox <span class="badge btn-danger">42</span></a>

<button class="btn btn-primary" type="button">
   未读信息 <span class="badge">14</span>
</button>

```

自定义.bat文件可以自动打开多个应用

```
start /d   xxxx对应的是软件安装的地址
start /d  "D:\tool\q\Bin" QQScLauncher.exe
```



####  导航条

```html
<!--
   最外围: nav包裹  紧接着是 container-fluid类栅格处理
      navber-header: 三条杠
     data-toggle= "collapse"  必须加用来点击触发
     data-target="#d1" 对应的id的值的元素  在移动端三条杠点击显示的内容
     navbar-brand :对应的是 logo/文本

    navbar-collapse : 主体内容
    
    navbar-fixed-top 固定在顶部
     navbar-inverse 背景颜色
-->
<nav class="navbar navbar-default navbar-fixed-top navbar-inverse">
    <div class="container">
        <!--头部 在phone端的 三条杠-->
        <div class="navbar-header">
            <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#d1" >
                <span class="icon-bar"></span>
                <span class="icon-bar"></span>
                <span class="icon-bar"></span>
            </button>
            <!--logo图 -->
            <a class="navbar-brand" href="#">
                <img src="logo.png" width="20" alt="">
            </a>
        </div>
<!--内容-->
        <div class="collapse navbar-collapse" id="d1">
            <ul class="nav navbar-nav">
                <li class="active"><a href="#">发现音乐 <span class="sr-only">(current)</span></a></li>
                <li><a href="#">我的音乐</a></li>
                <li><a href="#">朋友</a></li>
                <li><a href="#">商城</a></li>
                <li><a href="#">音乐人</a></li>
                <li><a href="#">下载</a></li>
            </ul>
            <!--表单-->
            <form class="navbar-form navbar-right">
                <div class="form-group">
                    <input type="text" class="form-control" placeholder="Search">
                </div>
                <button type="submit" class="btn btn-success">登录</button>
                <a href="" class="btn btn-info">注册</a>
            </form>

        </div><!-- /.navbar-collapse -->
    </div><!-- /.container-fluid -->
</nav>
```

#### 模态框

```html
<h1>模态框</h1>
<!--
     data-toggle="modal"  触发
     data-target="#myModal" 触发显示的元素
     data-dismiss="modal"  进行删除掉模态框

     类 bs-example-modal-sm  小模态框 加载 子元素需要添加 modal-sm
     
     data-keyboard="false"  可以通过data-xxxjs属性名去修改模态框的状态
     
     或者是直接通过js的写法去实现 功能
-->
<button type="button" class="btn btn-primary btn-lg" data-toggle="modal" data-target="#myModal" data-keyboard="false">
  登录
</button>
<a href="" id="btn" class="btn btn-default">js实现登录</a>
<!-- Modal -->
<div class="modal fade bs-example-modal-sm" id="myModal" tabindex="-1"  >
    <!-- 可以改模态框的大小-->
    <div class="modal-dialog  modal-sm" role="document">
        <div class="modal-content">
            <!--头部-->
            <div class="modal-header">
              <span class="close" data-dismiss="modal">X</span>
                <h2>用户登录</h2>
            </div>
            <!--主体-->
            <div class="modal-body">
               <div class="form-group">
                   <label for="txt">用户名:</label>
                   <input id="txt" type="text" class="form-control">
               </div>
                <div class="form-group">
                    <label for="pwd">密 码:</label>
                    <input id="pwd" type="password" class="form-control">
                </div>
            </div>
            <!--尾部-->
            <div class="modal-footer">
                <button type="button" class="btn btn-default" data-dismiss="modal">取消</button>
                <button type="button" class="btn btn-primary">登陆</button>
            </div>
        </div>
    </div>
</div>

<!-- jQuery (Bootstrap 的所有 JavaScript 插件都依赖 jQuery，所以必须放在前边) -->
<script src="js/jquery.min.js"></script>
<!-- 加载 Bootstrap 的所有 JavaScript 插件。你也可以根据需要只加载单个插件。 -->
<script src="js/bootstrap.min.js"></script>
<script>
  $("#btn").click(function (e) {
        e.preventDefault(); //阻止a的事件
        $("#myModal").modal({
            keyboard:false,// 键盘esc按下不会被取消 默认是true
             show:true,   // 点击显示模态框  false则不会显示
// 如果改为false 则没有遮罩层 static 点击模态框不会隐藏 默认会隐藏
             backdrop:'static' , 
        })


    })
    //   modal 一旦执行就会执行的方法  先执行
    $("#myModal").on("show.bs.modal",function () {
        console.log("我立即执行了");
    })
    // 等待css样式 完成加载完才执行
    $("#myModal").on("shown.bs.modal",function () {
        console.log("我立即执行了22222");  //后执行
    })
</script>
```

#### 导航条+模态框+滚动监听

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <!-- 上述3个meta标签*必须*放在最前面，任何其他内容都*必须*跟随其后！ -->
    <title>模板</title>
    <!-- Bootstrap -->
    <link href="css/bootstrap.min.css" rel="stylesheet">

    <!-- HTML5 shim 和 Respond.js 是为了让 IE8 支持 HTML5 元素和媒体查询（media queries）功能 -->
    <!-- 警告：通过 file:// 协议（就是直接将 html 页面拖拽到浏览器中）访问页面时 Respond.js 不起作用 -->
    <!--[if lt IE 9]>
    <script src="js/html5shiv.min.js"></script>
    <script src="js/respond.min.js"></script>
    <![endif]-->
    <style>
        body{
            padding-top: 50px;
            position: relative;
        }
    </style>
</head>
<body  data-spy="scroll" data-target="#d1" data-offset="250">
<!--

   1.给body添加相对定位 添加属性
     data-spy="scroll"   滚动事件
     data-target="#navbar-example"  触发的执行的元素
     data-offset="250"  //值越大 相对来说滚动监听的距离就越大 越早变化
-->
<!--导航条-->
<nav class="navbar navbar-default navbar-fixed-top navbar-inverse">
    <div class="container">
        <!--头部 在phone端的 三条杠-->
        <div class="navbar-header">
            <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#d1" >
                <span class="icon-bar"></span>
                <span class="icon-bar"></span>
                <span class="icon-bar"></span>
            </button>
            <!--logo图 -->
            <a class="navbar-brand" href="#">
                <img src="logo.png" width="20" alt="">
            </a>
        </div>
        <!--内容-->
        <div class="collapse navbar-collapse" id="d1">
            <ul class="nav navbar-nav">
                <li class="active"><a href="#box1">发现音乐 </a></li>
                <li><a href="#box2">我的音乐</a></li>
                <li><a href="#box3">朋友</a></li>
                <li><a href="#box4">商城</a></li>
                <li><a href="#box5">音乐人</a></li>
                <li><a href="">下载</a></li>
            </ul>
            <!--表单-->
            <form class="navbar-form navbar-right">
                <div class="form-group">
                    <input type="text" class="form-control" placeholder="Search">
                </div>
                <button type="button" class="btn btn-primary " data-toggle="modal" data-target="#myModal" data-keyboard="false">
                    登录
                </button>
                <a href="" class="btn btn-info">注册</a>
            </form>

        </div><!-- /.navbar-collapse -->
    </div><!-- /.container-fluid -->
</nav>
<!--模态框-->
<div class="modal fade bs-example-modal-sm" id="myModal" tabindex="-1"  >
    <!-- 可以改模态框的大小-->
    <div class="modal-dialog  modal-sm" role="document">
        <div class="modal-content">
            <!--头部-->
            <div class="modal-header">
                <span class="close" data-dismiss="modal">X</span>
                <h2>用户登录</h2>
            </div>
            <!--主体-->
            <div class="modal-body">
                <div class="form-group">
                    <label for="txt">用户名:</label>
                    <input id="txt" type="text" class="form-control">
                </div>
                <div class="form-group">
                    <label for="pwd">密 码:</label>
                    <input id="pwd" type="password" class="form-control">
                </div>
            </div>
            <!--尾部-->
            <div class="modal-footer">
                <button type="button" class="btn btn-default" data-dismiss="modal">取消</button>
                <button type="button" class="btn btn-primary">登陆</button>
            </div>
        </div>
    </div>
</div>

<div id="box1"><h1>发现音乐</h1><img class="img-responsive img" src="img/1.jpg" alt=""></div>
<div id="box2"><h1>我的音乐</h1><img class="img-responsive" src="img/2.jpg" alt=""></div>
<div id="box3"><h1>朋友</h1><img class="img-responsive" src="img/3.jpg" alt=""></div>
<div id="box4"><h1>商城</h1><img class="img-responsive" src="img/4.jpg" alt=""></div>
<div id="box5"><h1>音乐人</h1><img class="img-responsive" src="img/5.jpg" alt=""></div>
<!-- jQuery (Bootstrap 的所有 JavaScript 插件都依赖 jQuery，所以必须放在前边) -->
<script src="js/jquery.min.js"></script>
<!-- 加载 Bootstrap 的所有 JavaScript 插件。你也可以根据需要只加载单个插件。 -->
<script src="js/bootstrap.min.js"></script>
</body>
</html>
```

#### 提示框

```html
<body>
<!--
    $('[data-toggle="tooltip"]').tooltip()  需要手动调用否则无效
    data-toggle="tooltip"  触发的属性

-->
<h1>提示功能</h1>
<button type="button" class="btn btn-default" data-toggle="tooltip" data-placement="top" title="hello">点击提示</button>

<button type="button" class="btn btn-default" data-toggle="tooltip" data-placement="right" data-trigger="click" title="Tooltip on right">Tooltip on right</button>

<h1>通过js实现</h1>
<input id="btn" type="text" data-trigger="click" data-toggle="tooltip" title="必须是6位数字密码">
<!-- jQuery (Bootstrap 的所有 JavaScript 插件都依赖 jQuery，所以必须放在前边) -->
<script src="js/jquery.min.js"></script>
<!-- 加载 Bootstrap 的所有 JavaScript 插件。你也可以根据需要只加载单个插件。 -->
<script src="js/bootstrap.min.js"></script>
<script>
    // 需要手动调用方法
    $(function () {
        $('[data-toggle="tooltip"]').tooltip()
    })
    $("#btn").tooltip({
        placement:"right", //默认就是top方向
        trigger:"focus",
    })
</script>
```

#### 弹出框

```html
<!--
   需要手动执行   $('[data-toggle="popover"]').popover()
    属性 data-toggle="popover"
    js实现 
    
-->
<h1>弹出框</h1>
<button type="button" class="btn btn-lg btn-danger" data-toggle="popover" title="提示的头部信息" data-content="提示的主体内容">点我弹出/隐藏弹出框</button>

<button  type="button" data-placement="left" class="btn btn-lg btn-danger" data-toggle="popover" title="提示的头部信息" data-content="提示的主体内容">点我弹出/隐藏弹出框</button>
<h1>js实现</h1>
<button id="btn"  type="button"  class="btn btn-lg btn-danger"  >点我弹出/隐藏弹出框</button>
<!-- jQuery (Bootstrap 的所有 JavaScript 插件都依赖 jQuery，所以必须放在前边) -->
<script src="js/jquery.min.js"></script>
<!-- 加载 Bootstrap 的所有 JavaScript 插件。你也可以根据需要只加载单个插件。 -->
<script src="js/bootstrap.min.js"></script>
<script>
    $(function () {
        $('[data-toggle="popover"]').popover()
    })
    //js实现
    $("#btn").popover({
        placement:'right',//方向
        delay: { "show": 500, "hide": 500 }, // 显示和隐藏都需要500毫秒过程
        trigger:"hover",
        title:"我的js的头部",   // title  也是头部信息
        content:'我是通过js实现的',  //主体信息  
    })
</script>
```

#### 轮播图  

   

最外围: .carousel

 触发的属性  data-ride="carousel"

 .slide   加上之后 变为轮播 否则是 切换

​    可以通过js实现

```
// 可以修改时间
$('.carousel').carousel({
    interval: 1000
})
```

```html
<div class="container">
    <h1>基本的轮播图</h1>
    <div class="row">
        <div class="col-xs-6 col-xs-offset-3" >
            <div id="c1" class="carousel slide" data-ride="carousel">
                <!--没有圆点的轮播图-->
                <div class="carousel-inner" role="listbox">
                    <div class="item active">
                        <img src="img/1.jpg" alt="...">
                    </div>
                    <div class="item ">
                        <img src="img/2.jpg" alt="...">
                    </div>
                    <div class="item ">
                        <img src="img/3.jpg" alt="...">
                    </div>
                    <div class="item ">
                        <img src="img/4.jpg" alt="...">
                    </div>
                    <div class="item ">
                        <img src="img/5.jpg" alt="...">
                    </div>

                </div>
            </div>
        </div>
    </div>

    <h1>左右点击的轮播图</h1>
    <div class="row">
        <div class="col-xs-6 col-xs-offset-3" >
            <div id="c2" class="carousel slide" data-ride="carousel">
                <!--没有圆点的轮播图-->
                <div class="carousel-inner" role="listbox">
                    <div class="item active">
                        <img src="img/1.jpg" alt="...">
                    </div>
                    <div class="item ">
                        <img src="img/2.jpg" alt="...">
                    </div>
                    <div class="item ">
                        <img src="img/3.jpg" alt="...">
                    </div>
                    <div class="item ">
                        <img src="img/4.jpg" alt="...">
                    </div>
                    <div class="item ">
                        <img src="img/5.jpg" alt="...">
                    </div>

                </div>

                <!-- 按钮 -->
                <a class="left carousel-control" href="#c2"  data-slide="prev">
                    <span class="glyphicon glyphicon-chevron-left" aria-hidden="true"></span>
                </a>
                <a class="right carousel-control" href="#c2" role="button" data-slide="next">
                    <span class="glyphicon glyphicon-chevron-right" aria-hidden="true"></span>
                </a>
            </div>
        </div>
    </div>

    <h1>左右点击和圆点的轮播图</h1>
    <div class="row">
        <div class="col-xs-6 col-xs-offset-3" >
            <div id="c3" class="carousel slide" data-ride="carousel">

                <!---->
                <!--没有圆点的轮播图-->
                <div class="carousel-inner" role="listbox">
                    <div class="item active">
                        <img src="img/1.jpg" alt="...">
                    </div>
                    <div class="item ">
                        <img src="img/2.jpg" alt="...">
                    </div>
                    <div class="item ">
                        <img src="img/3.jpg" alt="...">
                    </div>
                    <div class="item ">
                        <img src="img/4.jpg" alt="...">
                    </div>
                    <div class="item ">
                        <img src="img/5.jpg" alt="...">
                    </div>

                </div>

                <!-- 按钮 -->
                <a class="left carousel-control" href="#c3"  data-slide="prev">
                    <span class="glyphicon glyphicon-chevron-left" aria-hidden="true"></span>
                </a>
                <a class="right carousel-control" href="#c3" role="button" data-slide="next">
                    <span class="glyphicon glyphicon-chevron-right" aria-hidden="true"></span>
                </a>
                <!--圆点-->
                <ol class="carousel-indicators">
                    <li data-target="#c3" data-slide-to="0" class="active"></li>
                    <li data-target="#c3" data-slide-to="1"></li>
                    <li data-target="#c3" data-slide-to="2"></li>
                    <li data-target="#c3" data-slide-to="3"></li>
                    <li data-target="#c3" data-slide-to="4"></li>
                </ol>
            </div>
        </div>
    </div>
    <h1>左右点击和圆点和文本的轮播图</h1>
    <div class="row">
        <div class="col-xs-6 col-xs-offset-3" >
            <div id="c4" class="carousel slide" data-ride="carousel">

                <!---->
                <!--没有圆点的轮播图-->
                <div class="carousel-inner" role="listbox">
                    <div class="item active">
                        <img src="img/1.jpg" alt="...">
                        <!--提示文本-->
                        <div class="carousel-caption">
                            <h3>一座山</h3>
                            <p>一座很神奇的山</p>
                        </div>
                    </div>
                    <div class="item ">
                        <img src="img/2.jpg" alt="...">
                        <!--提示文本-->
                        <div class="carousel-caption">
                            <h3>一片天</h3>
                            <p>一片很神奇的山</p>
                        </div>
                    </div>
                    <div class="item ">
                        <img src="img/3.jpg" alt="...">
                        <!--提示文本-->
                        <div class="carousel-caption">
                            <h3>一条船</h3>
                            <p>一条很神奇船</p>
                        </div>
                    </div>
                    <div class="item ">
                        <img src="img/4.jpg" alt="...">
                        <!--提示文本-->
                        <div class="carousel-caption">
                            <h3>一间房</h3>
                            <p>一间很神奇的房</p>
                        </div>
                    </div>
                    <div class="item ">
                        <img src="img/5.jpg" alt="...">
                        <div class="carousel-caption">
                            <h3>一条河</h3>
                            <p>一条很神奇的河</p>
                        </div>
                    </div>

                </div>

                <!-- 按钮 -->
                <a class="left carousel-control" href="#c4"  data-slide="prev">
                    <span class="glyphicon glyphicon-chevron-left" aria-hidden="true"></span>
                </a>
                <a class="right carousel-control" href="#c4" role="button" data-slide="next">
                    <span class="glyphicon glyphicon-chevron-right" aria-hidden="true"></span>
                </a>
                <!--圆点-->
                <ol class="carousel-indicators">
                    <li data-target="#c4" data-slide-to="0" class="active"></li>
                    <li data-target="#c4" data-slide-to="1"></li>
                    <li data-target="#c4" data-slide-to="2"></li>
                    <li data-target="#c4" data-slide-to="3"></li>
                    <li data-target="#c4" data-slide-to="4"></li>
                </ol>
            </div>
        </div>
    </div>

</div>
```

#### day04

#####    node下载  

   1.官网:

​     <http://nodejs.cn/download/>

![1597634656363](assets/1597634656363.png)

 镜像 存在阿里的淘宝镜像中存放着所有的Node的版本 如有需要我们直接去那里下载

​    <https://npm.taobao.org/mirrors/node>

  2.安装

​    如果是zip文件 则直接解压就可以用

​     如果是安装包 直接下一步可以自动配置环境变量

#####  需要配置环境变量

​    1.右键我的电脑、 点击高级系统设置、

![1597634798752](assets/1597634798752.png)

2.点击环境变量

![1597634830646](assets/1597634830646.png)

3.直接设置系统变量

​    1.新建一个系统变量 名字叫做 NODE_PATH(大写)

​      变量值  是 文件夹下的node文件夹下的 node_modules

![1597634936842](assets/1597634936842.png) 

2.添加path路径

​       是 文件夹下的node文件夹

![1597635066202](assets/1597635066202.png)

测试是否配置成功

 **node -v**  测试 当前按照的版本

  ![1597635108747](assets/1597635108747.png)

  **where node**  查看node的安装的路径、如果说路径不一致 需要重新配置一下node的环境变量



#### less

#####  1.静态样式语言css

​       直接被浏览器解析执行、 怎么引入都会的

​        css文件 它的**可重用性**和**可维护性**极差、相对于动态样式语言来说，太低端

##### 2.动态的样式语言   

less    =>是由js写入的

 在静态语言的基础上  添加了动态的属性 加入了一些   变量、运算、逻辑、函数、对象等

 语言中才具备的特性 从而大大的提高了代码的可维护性和可重用性。

当然除了less 之外 还有其他的动态样式语言   sass stylus....

在v4 bootstrap4中   使用的是sass   

 **所有的css端的语法 在less中都支持**

##### 3.less环境搭建

​       官网  <http://lesscss.cn/>

##### 4.运行

    1. 通过npm 下载  

```
npm  install -g less
```

2.直接浏览器引用(浏览器默认是不支持less)

```
<script src="//cdnjs.cloudflare.com/ajax/libs/less.js/2.5.3/less.min.js"></script>
```

##### 5.过程

​      1 先写一个less文件  xxx.less

​       2  通过less编译器 生成一个.map文件 再 转为 xxx.css

​       3.引入html网页中(引入解析好的xxx.css文件即可)

##### 6、less编译器

 可以通过npm去下载

有可能会出现 外网进不去 下载不了 卡死了

![1597645459197](assets/1597645459197.png)

补救办法  使用淘宝镜像 

1.设置cnpm   

```
npm install -g cnpm --registry=https://registry.npm.taobao.org
```

2.以后再使用npm下载时 不再是npmxxx而是

```
cnpm install -g less
```

![1597648959602](assets/1597648959602.png)

按照指定版本的bootstrap源码

```
cnpm install -g  bootstrap@3
```

查看

![1597649461175](assets/1597649461175.png)

##### 7.使用

   1.通过lessc 编译 将less文件转为 css文件

​     语法:  node  lessc文件夹路径    less文件路径  >  css文件路径

```html
   node  E:\server\htdocs\web\web\node-v12.6.0-win-x64\node_modules\less\bin\lessc   E:/01.less  > E:/01.css
```

   2.通过工具实现 自动转换

​     file->setting>tools>files watchers ![1597650740411](assets/1597650740411.png)

vscode       搜索  easy less 插件 

![1597650979196](assets/1597650979196.png)

#### 语法

#####   1.注释

​     // 单行注释   css文件中不会被解析出来

​     /**/         多行注释    css文件中可见

##### 2.变量的使用  @声明变量

```css
@xu_color:#aaa;
@xu_width:100px;
.box{
  width:@xu_width;
  height:2*@xu_width ;
  background-color: #aaaaaa+#00ff00;
}
//解析为css如下
.box {
  width: 100px;
  height: 200px;
  background-color: #aaffaa;
}
```

##### 3.mixin    混入写  已经写好的类的样式可以直接引用

   1、初级版 不带参数

```css
@xu_color:#aaa;
@xu_width:100px;
.box{
  width:@xu_width;
  height:2*@xu_width ;
  background-color: #aaaaaa+#00ff00;
}
// mixin    混入写  初级版
.main{
  .box;// 如果需要 可以引入之前写好的样式
  margin:@xu_width*0.1;
}
```

 2、带参数(增强重用性)

```css
//  引入 参数  增加的可用性
//   变量名 : 值    值表示的默认参数
.box1(@w,@h,@bgc,@sld:solid){
  width: @w;
  height: @h;
  background-color: @bgc;
  //  直接引用 @sld 自动去匹配默认给的值
  border:@xu_width*0.01 @sld @xu_color;
}
//引入的时候 可以实现数据的可变性
.main1{
  //传自定义的参数过去
  .box1(@xu_width*2,@xu_width*3,@xu_color+#f0f);
}
```

 3、解析问题

​       写公共样式类的时候 哪怕没有参数都要加() 避免被css解析

```css
// 默认情况 公共样式只是作为引入的对象 不需要去被css解析
// 如果 类名后面加了()  .a(){} css语法是不认识的 不会解析
//  .a{xxx}  css认识 所以会被解析
.pub{
  font-size: @xu_width*0.35;
}
//推荐使用后面的
.pub1(){
  font-size: @xu_width*0.35;
}
.box3{
  // .pub;
  .pub1();
}

//css解析情况
.pub {
  font-size: 35px;
}
.box3 {
  font-size: 35px;
}
```

4.嵌套写法

​     &:当前的元素

​     每个{} 对应一个层级

```less
.box1{
  width:50%;
  min-height: 300px;
  .header1{
    border:1px solid #ccc;
    //无序列表的 样式
    .list{
      list-style: none;
      //li的样式
      .item{
        float: left;
        //a 的样式
        a{
            text-decoration: none;
         // a:hover的写法
       //  & 当前的元素同一代
         &:hover{
           background-color: #aaa;
            
         } 
        }
      //鼠标移入 li的情况下添加hover
      &:before{
        content: "123";
      }
      }
    }
  }
}
```

4.引入问题

 1.css文件引入

```css
/* 可以引入其他写好的样式表*/
@import "04_body.css";
@import "04_header.css";
```

​	css引入 其实是无效且没有必要的
​	依然会去加载 @import引入的css子文件

![1597656960057](assets/1597656960057.png)

2.less文件的引入

```less
// 可以省略后缀
@import "05_body";
@import "05_header";
```

  案例04 测试 直接看案例

 只会引入一个 其他的不会出现

![1597657253500](assets/1597657253500.png)

#### less 定制问题

  一个项目中可能用不到全部的 bootstrap的css文件

 比如 项目中没有表格的样式 则不需要引入表格的样式

1. 注释掉不需要的 组件部分

   ![1597657700374](assets/1597657700374.png)

2.修改原有的不好看的样式

![1597657665085](assets/1597657665085.png)

### day05

1.下载

![1597715160475](assets/1597715160475.png)

  

```
使用npm下载
cnpm  install -g bootstrap //直接下的是最新的版本
```



#### 2.模板

```html
<!doctype html>
<html lang="en">
<head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">

    <!-- Bootstrap CSS -->
    <link rel="stylesheet" href="css/bootstrap.min.css">

    <title>Bootstrap 4</title>
</head>
<body>



<!-- b4中  不再需要支持低版本的浏览器  如果项目老的话 请用b3-->
<script src="js/jquery.slim.min.js"></script>
<!-- 用来实现 弹出框 下拉菜单 提示等 js操作
    如果不需要 可以直接引入bootstrap.min.js即可
                          59kb  非常的轻量
-->
<!--<script src="js/popper.min.js" ></script>
<script src="js/bootstrap.min.js"></script>-->

<!--如果 想要使用popper.min.js的内容 也可以直接引入-->
<script src="js/bootstrap.bundle.min.js"></script>
</body>
</html>
```

#### 语法特征

   b3:  浮动+定位+margin

   b4:  flex 弹性布局

#### 栅格系统(12列)

​     小于576像素下 还要分 则可以使用.col-n  

​     576-768像素之间.col-sm-n

​      768px-992 像素之间  .col-md-n

​     992-1200像素之间    .col-lg-n

​     1200以上                    .col -xl-n

![1597716597577](assets/1597716597577.png)

测试代码

   具体看案例

```html
 <style>
        div{
            border:1px solid #ccc;
        }

    </style>
</head>
<body>
 <h1 class="text-center">栅格系统</h1>
<div class="container">
 <div class="row">
     <!-- 没有了xs 多了 col-  多了xl  -->
     <!-- -->
     <div class="col-6 col-sm-4 col-md-3 col-lg-2 col-xl-1">测试栅格系统</div>

 </div>
    <!--所有屏 都是 6列-->
    <div class="row">
        <div class="col-6">测试延伸性</div>
    </div>
    <!-- 如果不加数据  则显示的是 等分操作 没有设置最小屏 默认是100%-->
    <div class="row">
        <div class="col-sm col-lg-3">1</div>
        <div class="col-sm col-lg-6">2</div>
        <div class="col-sm col-lg-3">3</div>
    </div>
    
    <!-- 测试水平和垂直 排列-->
    <div style="height: 100px" class="row justify-content-center align-items-center">
        <div style="height:50px" class="col-md-3">我要居中</div>
        <div style="height:50px" class="col-md-3 align-self-end">我要在底部</div>
    </div>
    <!-- 测试列偏移  可以在指定的屏幕宽度下 进行列偏移-->
    <!--不同屏幕下 可以指定不同的偏移-->
    <div class="row">
        <div class="col-6 offset-md-2 offset-3 offset-xl-6">我要偏移2列</div>
    </div>
    <!--测试一下边距  ml:margin-left 3表示一个rem的单位 -->
    <div class="row">
        <div class="col-6 ml-3">测试外边距</div>
    </div>
</div>
```

#### 排版操作

```html
<p class="h1">排版布局  图片</p>
<div class="container">
    <div>
        <img src="img/1.jpg" alt="">
    </div>
    <!-- img-thumbnail 自适应 max-width:100% 加了内边距和圆角-->
    <div>
        <img src="img/1.jpg" alt="" class="img-thumbnail">
    </div>
    <!-- 自适应 max-width:100%   没有其他样式-->
    <div >
        <img src="img/1.jpg" alt="" class="img-fluid">
    </div>

    <!--浮动 -->
    <div class="clearfix">
        <img width="200px" src="img/1.jpg" alt="" class="float-right">
        <img width="200px" src="img/2.jpg" alt="" class="float-left">
    </div>
    <!-- 测试  mx-auto==margin: 0 auto  d-block =display:block
       rounded : 圆角  my-3：1个单位的上下的外边距   具体的在工具类模块的 间距模块
    -->
    <div>
        <img width="200px" src="img/3.jpg" class="my-3 rounded mx-auto d-block" alt="...">
    </div>

    <!--给父元素添加 居中-->
    <div class="text-center">
        <img src="img/4.jpg" width="200" class="rounded" alt="...">
    </div>
</div>
```

#### table

```html
<div class="container">
    <h1 class="text-center"> 表格演示</h1>
    <div class="row justify-content-center">
        <div class="col-6">
            <!--
            table-striped 隔行变色
            table-hover 鼠标移入变
            table-dark : 黑底白字
            -->
            <table class="table  table-striped table-hover">
                <thead class="table-dark">
                <tr class="table-primary">
                    <th scope="col">#</th>
                    <th scope="col">First</th>
                    <th scope="col">Last</th>
                    <th scope="col">Handle</th>
                </tr>
                </thead>
                <tbody>
                <tr>
                    <th scope="row">1</th>
                    <td>Mark</td>
                    <td>Otto</td>
                    <td>@mdo</td>
                </tr>
                <tr>
                    <th scope="row">2</th>
                    <td>Jacob</td>
                    <td>Thornton</td>
                    <td>@fat</td>
                </tr>
                <tr>
                    <th scope="row">3</th>
                    <td>Larry</td>
                    <td>the Bird</td>
                    <td>@twitter</td>
                </tr>
                </tbody>
            </table>
        </div>

    </div>
</div>
```

#### border

   可以设置边框、颜色、圆角、不同边框的不同的值

```html
<div class="container">
    <h1>边框</h1>
    <!-- 边框 边框的颜色  d->display -->
    <span class="border d-inline-block border-info">hello</span>
    <!--border-top 上边框-->
    <span class="border-top d-inline-block border-info">上边框</span>

    <!--角度 rounded-circle-->
    <span class="border d-inline-block border-info rounded-circle">上边框</span>
    <!--文本颜色-->
    <span class="text-white bg-dark">添加文本颜色</span>
</div>
```

颜色: text-xxx

背景: bg-xxx

#### flex

  d-flex实现  在栅格系统中 .row自带了flex布局  不需要额外加 d-flex

  语法 和之前讲的一致  略

```html
 <style>
        div{
            border:1px solid #ccc;
        }
        .h{
            height: 10rem;
        }
    </style>
</head>
<body>
<h1>flex垂直布局 和学过的 flex布局是一样的</h1>

<div class="container">
    <!--如果 在栅格系统中 .row自带了flex布局  不需要额外加 d-flex -->
    <div class="h row  align-items-center">
        <div class="col-3 bg-dark">1</div>
        <div class="col-3 bg-danger align-self-end">2</div>
        <div class="col-3 bg-info">3</div>
    </div>
    <!-- 测试排序  order -->
    <div class="h row  align-items-center">
        <div class="col-3 order-3 bg-dark">1</div>
        <div class="col-3 order-2 bg-danger align-self-end">2</div>
        <div class="col-3 order-1 bg-info">3</div>
    </div>
</div>
<!--如果 在栅格系统中 .row自带了flex布局  不需要额外加 d-flex -->
<div class=" h d-flex  align-items-end">
    <div class="col-3 bg-dark">1</div>
    <div class="col-3 bg-danger">2</div>
    <div class="col-3 bg-info">3</div>
</div>
```

#### 尺寸和间隔

w-n   占比宽度的 百分之n
h-n   占比高度的 百分之n

```
<div style="height:200px">
     <div class="w-50 h-50">我要占一半</div>
</div>
```

##### 间隔

- `m` - 指的是 `margin`
- `p` - 指的是 `padding`

Where *sides* is one of:

- `t` - for classes that set `margin-top` or `padding-top`
- `b` - for classes that set `margin-bottom` or `padding-bottom`
- `l` - for classes that set `margin-left` or `padding-left`
- `r` - for classes that set `margin-right` or `padding-right`
- `x` - for classes that set both `*-left` and `*-right`
- `y` - for classes that set both `*-top` and `*-bottom`
- blank - for classes that set a `margin` or `padding` on all 4 sides of the element

Where *size* is one of:

- `0` - for classes that eliminate the `margin` or `padding` by setting it to `0`
- `1` - (by default) for classes that set the `margin` or `padding` to `$spacer * .25`
- `2` - (by default) for classes that set the `margin` or `padding` to `$spacer * .5`
- `3` - (by default) for classes that set the `margin` or `padding` to `$spacer` * 1
- `4` - (by default) for classes that set the `margin` or `padding` to `$spacer * 1.5`
- `5` - (by default) for classes that set the `margin` or `padding` to `$spacer * 3`
- `auto` - for classes that set the `margin` to auto

```html
<style>
        div{border:1px solid #ccc;}
    </style>
</head>
<body>
<!--
     w-n   占比宽度的 百分之n
     h-n   占比高度的 百分之n
-->
<div style="height:400px">
     <div class="w-50 h-50">我要占一半</div>
    <!-- 测试 边距
         p-3  ==padding:1rem;
         m-3  == margin:1rem;
         py-3 ==padding: 1rem 0;
         mx-3 == margin: 0 1rem;
         ml-n3  == margin-left:-1rem;
    -->
    <div class="w-25 p-3 m-3">测试 内外边距</div>
    <div class="w-25 py-3 mx-3">测试 内外边距分开写法</div>
    <div class="w-25 mx-auto">测试margin auto</div>
    <!--可以给负值  margin-left:-1rem; -->
    <div class="w-25 ml-n3">测试 给负值</div>
</div>
```

#### 文本修饰

```html
<!--
text-center  水平居中
text-truncate 多出的内容 省略号显示
font-xxx 字体粗细有关
-->
   <h1>文本测试</h1>
   <div class="text-center  ">
       <span class="font-weight-lighter">测试文本</span>
   </div>

   <div class="container">
       <div class="row">
           <a href="" class="col-1 text-truncate">震惊:杀人犯总算归案了</a>
       </div>
   </div>
```

#### 弹出框

```html
<!-- data-dismiss="alert"  直接使用 -->
<div class="alert alert-danger alert-dismissible fade show" >
    <strong>警告</strong> 你必须满足足够帅才可以浏览 <a href="" class="alert-link text-primary">这里</a>
    <button type="button" class="close" data-dismiss="alert" >
        <span aria-hidden="true">&times;</span>
    </button>
</div>
<h1>js操作</h1>
<div id="at" class="alert alert-danger alert-dismissible fade show" >
    <strong>警告</strong> 你必须满足足够帅才可以浏览 <a href="" class="alert-link text-primary">这里</a>
    <button type="button" class="close"  >
        <span aria-hidden="true">&times;</span>
    </button>
</div>
<!-- b4中  不再需要支持低版本的浏览器  如果项目老的话 请用b3-->
<script src="js/jquery.slim.min.js"></script>
<!-- 用来实现 弹出框 下拉菜单 提示等 js操作
    如果不需要 可以直接引入bootstrap.min.js即可
                          59kb  非常的轻量
-->
<!--<script src="js/popper.min.js" ></script>
<script src="js/bootstrap.min.js"></script>-->

<!--如果 想要使用popper.min.js的内容 也可以直接引入-->
<script src="js/bootstrap.bundle.min.js"></script>
<script>
   $(".alert button").click(function () {
       $("#at").alert("close")
   })
</script>
```

#### 轮播图

```html
<h1>左右按钮+三条杠 +文本 轮播图</h1>
<!--修改时间 -->
<div class="row">
    <div id="c4" class="carousel slide " data-interval="500" data-ride="carousel">
        <!--3条杠-->
        <ol class="carousel-indicators">
            <li data-target="#c4" data-slide-to="0" class="active"></li>
            <li data-target="#c4" data-slide-to="1"></li>
            <li data-target="#c4" data-slide-to="2"></li>
        </ol>
        <!--图片-->
        <div class="carousel-inner">
            <div class="carousel-item active">
                <img src="img/1.jpg" class="d-block w-100" alt="...">
                <!--文本-->
                <div class="carousel-caption d-none d-md-block">
                    <h5>一座神奇的山</h5>
                    <p><a href="" class="alert-link text-white">Nulla vitae elit libero, a pharetra augue mollis interdum.</a></p>
                </div>
            </div>
            <div class="carousel-item">
                <img src="img/2.jpg" class="d-block w-100" alt="...">
            </div>
            <div class="carousel-item">
                <img src="img/3.jpg" class="d-block w-100" alt="...">
            </div>
        </div>
        <!--左右按钮-->
        <a class="carousel-control-prev" href="#c4" role="button" data-slide="prev">
            <span class="carousel-control-prev-icon" aria-hidden="true"></span>

        </a>
        <a class="carousel-control-next" href="#c4" role="button" data-slide="next">
            <span class="carousel-control-next-icon" aria-hidden="true"></span>
        </a>
    </div>
</div>
```

#### 表单

```html
<div class="container">
    <h1>基本表单</h1>
    <!--
        每一个子控件组 外围是form-group
        input对应的是  form-control
    -->
    <form>
        <!--用户名-->
        <div class="form-group">
            <label for="exampleInputEmail1">用户名</label>
            <input type="email" class="form-control" id="exampleInputEmail1" >
            <small id="emailHelp" class="form-text text-muted">用户名只能是数字字母组合</small>
        </div>
        <!--密码-->
        <div class="form-group">
            <label for="exampleInputPassword1">密码</label>
            <input type="password" class="form-control" id="exampleInputPassword1">
        </div>
        <!--复选框-->
        <div class="form-group form-check">
            <input type="checkbox" class="form-check-input" id="exampleCheck1">
            <label class="form-check-label" for="exampleCheck1">勾选</label>
        </div>
        <!--文件-->
        <div class="form-group">
            <label for="e1"><h3 class="btn btn-lg btn-info">上传资料</h3></label>
            <input type="file" style="display: none" class="form-control-file" id="e1">
        </div>

        <button type="submit" class="btn btn-primary">提交</button>
    </form>
    <h1>横向的 </h1>
<!--
   外围 需要加 .row
   里面需要 分列操作 .col去操作
-->
    <form>
        <!--用户名-->
        <div class="form-group row">
            <label for="exampleInputEmail1" class="col-sm-3">用户名</label>
            <input type="email" class="form-control col-sm-6" id="i1" >
            <small id="e11" class="form-text text-muted col-sm-3">用户名只能是数字字母组合</small>
        </div>
        <!--密码-->
        <div class="form-group row">
            <label for="i2" class="col-sm-3">密码</label>
            <input type="password" class="form-control col-sm-6" id="i2" >
        </div>

        <button type="submit" class="btn btn-primary">提交</button>
    </form>
</div>
```

#### sass

   和less类似也是动态的css预编译处理语言 也同样支持css语法

##### 1.下载   

  因为sass采用的 Ruby这门语言开发的  需要先安装ruby开发环境 去进行安装

  官网的下载地址: <https://rubyinstaller.org/downloads/>

![1597805510016](assets/1597805510016.png)

##### 2.安装

 ![1597806876132](assets/1597806876132.png)

![1597806888006](assets/1597806888006.png)

测试是否安装成功

![1597806978921](assets/1597806978921.png)

##### 安装sass

```
gem install sass
```

![1597807396260](assets/1597807396260.png)

##### 找到安装在哪里

```
where sass
```

![1597807425719](assets/1597807425719.png)

##### 工具配置

![1597807740842](assets/1597807740842.png)

##### 新建文件

![1597807891512](assets/1597807891512.png)

##### 自动生成css文件(安装ok)

![1597807916064](assets/1597807916064.png)

##### 疑惑:

  sass => 建立的scss？

  scss是sass3引入的 新的语法 语法兼容css3样式，集成了sass的强大语法，也就是说

 任何标准的css3样式都可以在scss文件中使用。css hacks部分(对浏览器的兼容处理)

  scss更强大！

#### 官网

<https://www.sass.hk/>

![1597818887655](assets/1597818887655.png)

#### 具体语法

  **ctrl+alt+l 代码格式化的快捷键**

##### 1.变量、嵌套、@mixin

  注意: 

```
@charset "utf-8";
// 注释   在第一行添加 文件的编码设置 否则注释会报错
```

```css
// 1.变量 $
$xu:#123456;
$w:10px;
.a{
  color:$xu;
  width: $w*20;
  height: $w*20;
  background-color:$xu+ #ff585d;
}
//支持嵌套写法
#content{
  .box{
    background-color: $xu;
    .a{
      margin:$w;
      &:hover{
        border-bottom:$w*0.3 solid $xu;
        span{
          display: none;
        }
      }
    }
  }
}

// mixin写法

//不带参数的定义
@mixin text{
  font:{
    family: "DM Sans", sans-serif;
    weight: bold;
    color:$xu;
  }
}
//  带参数的 定义
@mixin myborder($color,$width){
  border:{
    width: $width;
    color: $color;
    style: solid;
  }
}
//通过 @include去引入之前定义好的 模块
.b{

  @include myborder(#0f0,$xu);
   @include  text;
}
```

##### 2.参数 之 默认参数  不确定参数

```css
//   设置默认参数
@mixin  xu_border($width:1px,$st:solid,$color:#ccc){
     border:$width $st $color;
}
//给实参 必须按照顺序给
.b1{
  @include xu_border(5px, dashed,#aaa);
}

//不确定参数  $变量...
@mixin box-s($shadow...){
  box-shadow: $shadow;
}
//  参数可以写多个
.b3{
  @include box-s(5px 5px 5px 5px #aaa )
}
```

##### 3.数学运算

```css
//数学运算
.fon{
  $a:10px;
  $b:10;
  $c:#112233;

   width: $a*$b; //100px
   border:$a*0.1 solid $c+#000000;
   font-size: $a/0.5; //20px
   //height: round(1.95)*$a; // 四舍五入
  // 如果想要 计算 除法则需要用()括起来
   height: (20px/2);
  //如果不想要计算   则用 #{xxx}
  padding: #{20px}/#{2};
     //减法   注意空格
  margin: $a - $b ;
}
```

##### 4.颜色

```css
// 颜色
.colla{
    $c:#112233;
    $cc:$c+#222222;
  background-color: rgb(22,22,22)+rgb(55,55,55);
}
```

##### 5.字符串拼接问题

```css
//字符串运算
.str{
  $t:"微软雅黑";
  $s:"sans";

  font-family:$s+"-serif";//可以
  font-family: $s+-serif; // 可以 字符串加 不是字符串 可以实现
  font-family: sans+"-serif";// 不可以  字符串写在前面
  font-family: $s+"-"+$t; //可以
  font-family: $s+-$t; // 不可以
}
```

##### 6.if判断 和bool

```css
//运算
// bool  and  or 连接 不再是 || &&
@mixin  bol($age){
  @if($age>18 and $age<60){
    color:yellow;
    }@else{
    color:red;
}
}
.col{
 @include bol(10);
}
// if else if
@mixin  bol($age){
  @if($age>18 and $age<60){
    color:yellow;
  }@elseif($age<18){
    color:black;
  }@else {
    color:red;
  }
}
```

##### for循环

​      注意 through 和 to 的区别

```css
//遍历 for循环
//    through  包含 开头结合
//  从1 到3
@for $i from 1 through 3 {
  .item-#{$i} { width: 2em * $i; }
}
//  不包含结尾  从1 到 2
@for $i from 1 to 3 {
  .item-#{$i} { width: 2em * $i; }
}
//解析为

.item-1 {
  width: 2em; }

.item-2 {
  width: 4em; }

.item-3 {
  width: 6em; }

.item-1 {
  width: 2em; }

.item-2 {
  width: 4em; }


```

##### @each遍历

```css
//@each 遍历   遍历注意类名不能从数字开头
@each $img in 1, 2,3,4,5 {
  .p#{$img} {
    background-image: url('img/#{$img}.png');
  }
}
//解析为
.p1 {
  background-image: url("img/1.png"); }

.p2 {
  background-image: url("img/2.png"); }

.p3 {
  background-image: url("img/3.png"); }

.p4 {
  background-image: url("img/4.png"); }

.p5 {
  background-image: url("img/5.png"); }
```

##### @while循环

```css
// while 循环
$i:6;
@while $i > 0 {
 .d#{$i}{
   width:$i*10rem;
   }
 $i:$i - 1;
}
//编译
.d6 {
  width: 60rem; }

.d5 {
  width: 50rem; }

.d4 {
  width: 40rem; }

.d3 {
  width: 30rem; }

.d2 {
  width: 20rem; }

.d1 {
  width: 10rem; }
```

##### map

```css
// map 遍历
$color:(
   c1:#123456,
   c2:#cccccc,
   c3:#0f0,
);
.bgc{
   background-color: map_get($color,c3);
}
//编译

.bgc {
  background-color: #0f0; }
```

##### 引入文件 @import "01";

##### 继承样式 @extend

```css
//继承 选择器
.err{
  border:1px solid red;
}
// @extend  以 群组选择器的形式 实现使用 .err继承过来的样式
.boo2{
  @extend .err;
  background-color: #0AB5F3;
}
//解析
.err, .boo2 {
  border: 1px solid red; }

.boo2 {
  background-color: #0AB5F3; }
```

##### 安装 高亮文本显示

去搜索BrowserWordAtCaeret下载 

![1597829224709](assets/1597829224709.png)



![1597829190307](assets/1597829190307.png)

