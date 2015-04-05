## JavaScript 在 HTML 文件中位置
JavaScript 脚本可以很灵活的写在几乎 HTML 网页的任何地方。  
但是，在 HTML 文件中编写的 JavaScript 脚本只可以放置在如下部分中：  
1. HTML 网页的 `<head>...</head>` 里。  
2. HTML 网页的 `<body>...</body>` 里。  
3. HTML 网页的 `<head>...</head>` 和 `<body>...</body>` 里。  
4. 外部文件里,并且引用在 `<head>...</head>` 中。  

如下章节，我们将了解如何在上述 HTML 文件的不同的地方编写 JavaScript 脚本。  
###在 `<head>...</head>` 之间编写JavaScript脚本：  
如果你希望在某个事件中编写脚本，比如，当用户点击一个按钮时触发一个事件。  
你可以按照如下方式将脚本编写在 `<head>...</head>` 结构中
  
    <html>
    <head>
    <script type="text/javascript">
    <!--
    function sayHello() {
       alert("Hello World")
    }
    //-->
    </script>
    </head>
    <body>
    <input type="button" onclick="sayHello()" value="Say Hello" />
    </body>
    </html>
上述例子将产生如下效果：
> <html>
> <head>
> <script type="text/javascript">
> <!--
> function sayHello() {
>    alert("Hello World")
> }
> //-->
> </script>
> </head>
> <body>
> <input type="button" onclick="sayHello()" value="Say Hello" />
> </body>
> </html>

为了更好的理解此处内容，你可以自己[尝试一下](http://www.tutorialspoint.com/cgi-bin/practice.cgi?file=javascript_2)。

###在 `<body>...</body>` 之间编写 JavaScript 脚本：  
如果你需要一段脚本来实现页面加载后将信息内容显示在页面中的功能。  
这段脚本需要编写在HTML文件的 `<body>...</body>` 部分。  
这种情况下，你不需要定义任何 JavaScript 函数。  

    <html>
    <head>
    </head>
    <body>
    <script type="text/javascript">
    <!--
    document.write("Hello World")
    //-->
    </script>
    <p>This is web page body </p>
    </body>
    </html>
上述例子将产生如下效果：

    Advertisements
    
    Hello World
    This is web page body

为了更好的理解此处内容，你可以自己[尝试一下](http://www.tutorialspoint.com/cgi-bin/practice.cgi?file=javascript_3)。
###在`<body>`与`<head>`中编写JavaScript脚本：  
你也可以同时将脚本编写在 `<body>` 与 `<head>` 中。  

    <html>
    <head>
    <script type="text/javascript">
    <!--
    function sayHello() {
       alert("Hello World")
    }
    //-->
    </script>
    </head>
    <body>
    <script type="text/javascript">
    <!--
    document.write("Hello World")
    //-->
    </script>
    <input type="button" onclick="sayHello()" value="Say Hello" />
    </body>
    </html>
上述例子将产生如下效果：
> Advertisements
> 
> Hello World 
> 
> <html>
> <head>
> <script type="text/javascript">
> <!--
> function sayHello() {
>    alert("Hello World")
> }
> //-->
> </script>
> </head>
> <body>
> <script type="text/javascript">
> <!--
> document.write("Hello World")
> //-->
> </script>
> <input type="button" onclick="sayHello()" value="Say Hello" />
> </body>
> </html>

为了更好的理解此处内容，你可以自己[尝试一下](http://www.tutorialspoint.com/cgi-bin/practice.cgi?file=javascript_4)。
###在外部文件中编写 JavaScript 脚本：  
当你在工作中开始广泛使用 JavaScript 后，你会发现在多 HTML 页面中重用相同的 JavaScript 是一个不错的选择。  

这样，你可以不用维护多个 HTML 文件中相同的代码。  
Script 标签提供了在外部文件中编写 JavaScript 脚本并引用在 HTML 文件中的功能。  
下面的例子将展示如何使用 script 标签将外部 JavaScript 脚本文件引用在 HTML 文件中。  

    <html>
    <head>
    <script type="text/javascript" src="filename.js" ></script>
    </head>
    <body>
    .......
    </body>
    </html>

为了实现上述功能，需要将所有的 JavaScript 源代码编写到以 “.js” 为格式后缀名的外部文本文件中，然后按照上面的方式引用入 HTML 文件中。  
例如，你可以将下面的内容编写到“文件名.js” 文件中，然后在 HTML 文件中引入该外部脚本文件后，你可以使用 sayHello 函数。  

    function sayHello() {
       alert("Hello World")
    }
    