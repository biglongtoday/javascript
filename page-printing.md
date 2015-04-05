##JavaScript - 页面打印

很多时候你会想在你 web 页面上添加一个按钮来用实际的打印机打印当前页面的内容。

JavaScript 能使用 *window* 对象的打印函数来帮你实现这个功能。

当JavaScript的打印方法 **window.print()** 执行后，就会打印当前的 web 页面。
你可以使用 *onclick* 事件直接调用这个函数，如下所示：

    <head>
    <script type="text/javascript">
    <!--
    //-->
    </script>
    </head>
    <body>
    <form>
    <input type="button" value="Print" onclick="window.print()" />
    </form>
    </body>

这段代码会产生如下的所示的按钮，它能让你打印当前的页面。试着点击一下：
<head>
<script type="text/javascript">
<!--
//-->
</script>
</head>
<body>
<form>
<input type="button" value="Print" onclick="window.print()" />
</form>
</body>

虽然这能够满足你将页面打印出来的要求，但并不推荐这种方法将页面提供给打印设备。一个友好的打印页面，仅仅是打印一个包含文本的页面，而不包括图片，图形或者广告。

你可以采用以下方法之一来使一个页面友好的打印：

- 拷贝一份页面，并且删去不想要的文本和图形，然后从原始页面链接到能友好打印的页面。[点击例子](http://www.tutorialspoint.com/javascript/printfriendly.htm)。

- 如果你不想额外的拷贝一份页面，那你可以使用合适的注释来标记可以打印的文本。例如，<!-PRINT STARTS HERE -->..... <!-PRINT ENDS HERE -->。然后你可以使用 PERL 或者其他任何语言的脚本在后台对最终可打印的文本进行净化并展示出来。我们网站使用的是同样的方法来提供给网站访问者的打印设备打印。[点击例子](http://www.tutorialspoint.com/cgi-bin/printversion.cgi?tutorial=javascript&file=javascript_page_printing.htm)。

###怎样打印一个页面：

如果某个页面并没有提供如上所示的打印工具，那你可以使用浏览器的标准工具栏来打印出 web 页面。操作流程如下所示：

文件-->打印-->点击确定按钮。