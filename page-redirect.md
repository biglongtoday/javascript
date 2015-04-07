##JavaScript - 页面重定向

###什么是页面重定向？


 当你点击一个 URL 会跳转到页面 X，但是在一个页面内部点击会直接跳转到另外一个页面 Y，这里能够跳转的原因是因为页面重定向。这个是与 JavaScript 页面刷新是有区别的。

这里有许多原因可以解释为什么想要从原始页面进行重定向。例举了如下几个原因：

- 你不喜欢你现在的域名，并且你想要使用一个新的域名。有时你想将你的所有的访问者转向到你的新的网站。在这种情况下，你可以继续维护你旧的域名，同时增加单独的一页用来进行重定向，这样你的所有旧域名的访问者就可以转到新的域名。

- 你已经基于浏览器的版本构建了各种网页或者他们的名称在不同的国家不同，你可以客户端网页让用户重定向到合适的网页，而不是在服务器端进行网页的跳转。

- 搜索引擎可能已经对你的网页建立了索引。但是当你网站迁移到另外一个域名时，你不想丢失通过搜索引擎访问你网站的用户。此时你可以使用客户端网页重定向。但是请记住，不要利用这种方式欺骗搜索引擎，否则你的网站会被禁止访问。

##网页重定向如何工作的？

###例子 1：

利用 JavaScript 在客户端进行重定向是非常简单的。为了重定向你网站的访问者，你仅仅只需要在网页代码的头部中添加一行代码，如下：

```

<head>
<script type="text/javascript">
<!--
   window.location="http://www.newlocation.com";
//-->
</script>
</head>
```
为了更好的理解此处内容，你可自己[尝试一下](http://www.tutorialspoint.com/cgi-bin/practice.cgi?file=javascript_27)。

###例子 2：

在重定向到一个新的网页之前，你可以给访问者显示一些合适的提示信息。虽然这样可能稍微需要一点的额外加载时间。下面是一个简单的例子来实现那个功能：

```
<head>
<script type="text/javascript">
<!--
function Redirect()
{
    window.location="http://www.newlocation.com";
}

document.write("You will be redirected to main page in 10 sec.");
setTimeout('Redirect()', 10000);
//-->
</script>
</head>
```

这里的 _setTimeout()_ 是 JavaScript 内置的函数，它可以在给定的时间之后执行另外一个函数。

为了更好的此处内容，你可以自己[尝试一下](http://www.tutorialspoint.com/cgi-bin/practice.cgi?file=javascript_28)。

###例子 3：

下面是一个基于用户的浏览器跳重定向网页到不同的网页的例子：

```
<head>
<script type="text/javascript">
<!--
var browsername=navigator.appName; 
if( browsername == "Netscape" )
{ 
   window.location="http://www.location.com/ns.htm";
}
else if ( browsername =="Microsoft Internet Explorer")
{
   window.location="http://www.location.com/ie.htm";
}
else
{
  window.location="http://www.location.com/other.htm";
}
//-->
</script>
</head>
```
