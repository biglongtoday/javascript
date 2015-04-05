##JavaScript - Void关键字
JavaScript 中 **void** 是一个重要的关键字。它可以用作一个一元运算符，此时它会出现在一个操作数之前，这个操作数可以是任意类型的。

这个操作符指定要计算一个表达式但是不返回值。它的语法可能是下列之一:

    <head>
    <script type="text/javascript">
    <!--
    void func()
    javascript:void func()
    
    or:
    
    void(func())
    javascript:void(func())
    //-->
    </script>
    </head> 

###例子1
这个运算符最常用在客户端的 *javascript: URL* 中，在 URL 中可以写带有副作用的表达式，而 void 则让浏览器不必显示这个表达式的计算结果。

这里的 *alert('Warning!!!')* 表达式被执行了，但是它不会在当前文档处装入任何内容：

    <head>
    <script type="text/javascript">
    <!--
    //-->
    </script>
    </head>
    <body>
    <a href="javascript:void(alert('Warning!!!'))">Click me!</a>
    </body>

为了更好的理解此处内容，你可以自己[尝试一下](http://www.tutorialspoint.com/cgi-bin/practice.cgi?file=javascript_32)

###例子2
另外的一个例子，下面的超级链接并不会做任何事情，因为在 JavaScript 中表达式 “0” 没有任何作用。这里的表达式 “0” 已被计算，但是它并没有在当前文档处装入任何内容：

    <head>
    <script type="text/javascript">
    <!--
    //-->
    </script>
    </head>
    <body>
    <a href="javascript:void(0))">Click me!</a>
    </body>

为了更好的理解此处内容，你可以自己[尝试一下](http://www.tutorialspoint.com/cgi-bin/practice.cgi?file=javascript_33)

###例子3

*void* 的另一种用法是有意的生成 *undefined* 值，如下所示：

    <head>
    <script type="text/javascript">
    <!--
    function getValue(){
       var a,b,c;
    
       a = void ( b = 5, c = 7 );
       document.write('a = ' + a + ' b = ' + b +' c = ' + c );
    }
    //-->
    </script>
    </head>

为了更好的理解此处内容，你可以自己[尝试一下](http://www.tutorialspoint.com/cgi-bin/practice.cgi?file=javascript_34)