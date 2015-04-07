##JavaScript and Cookies

##Cookies 是什么？

Web 浏览器与服务器之间利用 HTTP 协议进行通信，而且 HTTP 是一种无状态的协议类型。但是对于商业网站，它通常需要维护一些与客户端在不同网页交互的信息。例如，一个用户在很多网页中填写信息后完成了注册，此时应该如何维护(或者缓存)众多网页中用户的信息。

在很多情况下，利用 Cookies 是最有效的方式，通过这种方式可以记录和跟踪一些用户的偏好，购物车，工资，和其他的信息，而利用这些信息可以更好的了解用户经历或者进行网站统计。

##它是如何的起作用的？


服务器以 Cookies 的形式发送一些数据给访问者的浏览器。浏览器可以选择接收这些 Cookies。如果它被接收了，它就会被以纯文本的形式存储在访问者的硬盘中。接着，当访问者访问网站中的另外一个网页时，那些被缓存的 Cookies 会被发送到服务器进行检索。一旦服务器在服务端检索到该 Cookies 信息，服务器就会知道访问者本地已经缓存了的数据。

Cookies 是纯文本数据，记录了 5 个可变长度的字段：

 - **Expires：** 这个字段记录 Cookies 有效时间长度。如果这个字段为空，该 Cookies 将会在用户关闭浏览器时过期，即该 Cookies 的数据不再可用。
 - **Domain:** 这个字段记录网站名。
 - **Path:** 这个字段记录设置 Cookies 的目录或者网页的路径。如果你想在任何目录或网页里面等够检索到 Cookies 数据这个字段可以被设置为空。
 - **Secure:** 如果这个字段包含"secure"这个单词，那么 Cookies 仅仅只能被安全服务器进行检索。如果这个字段为空，就没有前面的限制。
 - **Name=Value:** Cookies 以键值对的形式进行赋值和检索。

Cookies 最初是为 CGI 编程提供的，并且 Cookies 数据在网页浏览器和服务器之间是自动的传输的，因此服务器端的 CGI 脚本能够读写存储在客户端的 Cookies。

JavaScript 通过使用 Document 对象的 Cookies 属性同样可以操作 Cookies。JavaScript 可以读、创建、修改、和删除 Cookie，或者那些应用于当前网页的       Cookies。

##Cookies 的存储：

创建 Cookie 最简单的方式就是给 document.cookie 对象赋值一个字符串值，它的语法如下：

###**语法:**

```
document.cookie = "key1=value;key2=value2;expires=date";
```

这里的 expires 属性字段是可选的。如果你给它提供一个有效的日期或者时间值，Cookie 将会在你给定的日期或时间达到时过期，并且这之后 Cookie 的属性值都会变的不可访问。

####**注意:**
Cookie 的值不包括分号，逗号或者空格。因此，在存储 Cookie 之前，你可能需要利用 JavaScript 提供的  _escape()_ 函数来对其值进行转义。如果你按照那样做的话，当你读取 Cookie 的值时，你就需要利用相应的 _unescape()_ 函数。

###例子：

下面是一个将用户的名称记录在 Cookie 的例子。

```
<html>
<head>
<script type="text/javascript">
<!--
function WriteCookie()
{
   if( document.myform.customer.value == "" ){
      alert("Enter some value!");
      return;
   }

   cookievalue= escape(document.myform.customer.value) + ";";
   document.cookie="name=" + cookievalue;
   alert("Setting Cookies : " + "name=" + cookievalue );
}
//-->
</script>
</head>
<body>
<form name="myform" action="">
Enter name: <input type="text" name="customer"/>
<input type="button" value="Set Cookie" onclick="WriteCookie();"/>
</form>
</body>
</html>
```
上面代码执行效果如下。当在文本框中输入文字并且点击了 "Set Cookie" 按钮就可以设置 Cookie。


现在你的机器中存在一个名称为 name 的 Cookie。你可以利用多个 key = value 键值对，他们之间用逗号分开，这样来设置多个 Cookie 信息。

###读取 Cookies：

读取 Cookie 就像写它一样简单，因为 document.cookie 对象的值就是 Cookie 的属性值。因此你可以利用这个字符串在任何时候对 Cookie 进行访问。

document.cookie 字符串会保存一系列用分号分开的 name = value 键值对，这里的 name 就是一个 Cookie 名称，value 是它的值。

你可以利用 _split()_ 函数将字符串分解成如下形式的 key 和 value：

###例子：

下面的是读取前面一节设置的 Cookie 信息。

```
<html>
<head>
<script type="text/javascript">
<!--
function ReadCookie()
{
   var allcookies = document.cookie;
   alert("All Cookies : " + allcookies );

   // Get all the cookies pairs in an array
   cookiearray  = allcookies.split(';');

   // Now take key value pair out of this array
   for(var i=0; i<cookiearray.length; i++){
      name = cookiearray[i].split('=')[0];
      value = cookiearray[i].split('=')[1];
      alert("Key is : " + name + " and Value is : " + value);
   }
}
//-->
</script>
</head>
<body>
<form name="myform" action="">
<input type="button" value="Get Cookie" onclick="ReadCookie()"/>
</form>
</body>
</html>
```
###注意：
这里的 length 是 Array 类型的一个方法，该方法返回一个数组的长度。我们会在一个单独的章节再讨论数组类型。在那个时候请再好好理解这个方法。

上面的代码会有如下的效果。当你按下 "Get Cookie" 按钮，你就会看到你在上一节设置的 Cookie 信息。
###注意：
在你的机器上可能已经存在一些其他的 Cookie。因此上面的代码会显示存储在你的机器上所有的 Cookies 信息。

##设置 Cookies 有效日期：


你可以设置有效日期并且将该有效日期与 Cookie 进行绑定，从而可以延长 Cookie 的生存时间超过当前浏览器的会话。这个可以为 expires 属性赋值一个日期或者时间来实现。

###例子：

下面的代码说明怎样设置让 Cookie 在一个月之后失效：

```
<html>
<head>
<script type="text/javascript">
<!--
function WriteCookie()
{
   var now = new Date();
   now.setMonth( now.getMonth() + 1 ); 
   cookievalue = escape(document.myform.customer.value) + ";"
   document.cookie="name=" + cookievalue;
   document.cookie = "expires=" + now.toUTCString() + ";"
   alert("Setting Cookies : " + "name=" + cookievalue );
}
//-->
</script>
</head>
<body>
<form name="formname" action="">
Enter name: <input type="text" name="customer"/>
<input type="button" value="Set Cookie" onclick="WriteCookie()"/>
</form>
</body>
</html>
```

##删除一个 Cookie

有时你想要删除一个 Cookie，从而下次尝试读取 Cookie 信息时会返回一个空值。为了实现这个，你可以设置 Cookie 的有效生存时间为过去的某个时间的即可。

###例子:

下面的代码说明如何将一个 Cookie 的有效时间设置为过去的一个月来删除       Cookie。

```
<html>
<head>
<script type="text/javascript">
<!--
function WriteCookie()
{
   var now = new Date();
   now.setMonth( now.getMonth() - 1 ); 
   cookievalue = escape(document.myform.customer.value) + ";"
   document.cookie="name=" + cookievalue;
   document.cookie = "expires=" + now.toUTCString() + ";"
   alert("Setting Cookies : " + "name=" + cookievalue );
}
//-->
</script>
</head>
<body>
<form name="formname" action="">
Enter name: <input type="text" name="customer"/>
<input type="button" value="Set Cookie" onclick="WriteCookie()"/>
</form>
</body>
</html>
```
###注意：
除了设置日期你还可以利用 _setTime()_ 方法来实现设置有效时间。
