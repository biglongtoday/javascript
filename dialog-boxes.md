##JavaScript - 对话框

JavaScript 支持三种重要的对话框类型。这些对话框可以用来弹出警告，或者根据用户的输入来得到确定的信息，或者得到用户输入的某一类型。

###警告对话框：

警告对话框是最常用的，它通常被用来给用户提示一些警告信息。比如，某个输入区域需要用户输入一些文本信息，但是用户并没有输入任何信息，那么为了使用户输入有效的信息，你可以利用警告对话框来提示警告信息，如下：

```
<head>
<script type="text/javascript">
<!--
   alert("Warning Message");
//-->
</script>
</head>
```

除了这个作用外，警告对话框也可以提示一些友好的信息。警告对话框仅仅值提供一个 "OK" 按钮供选择来继续执行。

###确认对话框：

确认对话框是最常用来获取用户对任何选项的赞成的观点。确认对话框会显示两个按钮：**Ok** 和 **Cancel**。

如果用户点击了 OK 按钮，窗口函数 _confirm()_ 的返回值为 true。如果用户点击了 Cancel 按钮，_confirm()_ 函数返回值为 false。你可以像如下的方式使用确认对话框：

```
<head>
<script type="text/javascript">
<!--
   var retVal = confirm("Do you want to continue ?");
   if( retVal == true ){
      alert("User wants to continue!");
	  return true;
   }else{
      alert("User does not want to continue!");
	  return false;
   }
//-->
</script>
</head>
```

为了更好的理解此处内容，你可以自己[尝试一下](http://www.tutorialspoint.com/cgi-bin/practice.cgi?file=javascript_30)。

###提示对话框：

当你想弹出一个文本框，并且得到用户的输入数据，提示框就可以实现这个功能。因此，这个框可以与用户进行交互。用户需要填写信息，然后点击 Ok
按钮。

这种对话框通过调用 _prompt()_ 函数来显示，给函数有两个形式参数 (i) 你想在框中显示的文本标签 (ii) 一个默认的显示在框中的字符串。

这种对话框提供两个按钮：**OK** 和 **Cancel**。 如果用户点击 OK 按钮，窗口函数 _prompt()_ 将会返回文本框中输入的值。如果用户点击 Cancel 按钮，窗口函数 _prompt()_ 的返回值为 _null_。

你可以使用如下的方式来实现提示对话框：

```
<head>
<script type="text/javascript">
<!--
   var retVal = prompt("Enter your name : ", "your name here");
   alert("You have entered : " +  retVal );
//-->
</script>
</head>
```

为了更好的理解此处的内容，你可以自己[尝试一下](http://www.tutorialspoint.com/cgi-bin/practice.cgi?file=javascript_31)。



