##JavaScript 变量与数据类型
### JavaScript 数据类型：
可编程语言的基本特征之一就是对常用数据类型的支持。这些数据类型可以用可编程语言来表示和操作。  
按照JavaScript的语法规范，它允许有如下三类基础数据类型：  
1. 数值类型：比如 123,120.50 等。  
2. 字符串类型：比如“This text string”。  
3. 布尔类型：比如 true or false。
  
JavaScript也支持另外两个常用类型：null 和 undefined，这两个类型均仅限定一个单一的值。  
除了上述的基础数据类型，JavaScript 也支持符合数据类型，我们称之为“对象”。我们会在其他章节中学习“对象”的具体内容。  
**注意：**JAVA语言并区分整数类型与浮点类型。JavaScript 中的数值均使用浮点值来表示。同时，按照 IEEE754 标准，JavaScript 用64位浮点格式来表示数。  
###JavaScript变量：  
和其他可编程语言相同，JavaScript 也有“变量”的概念。“变量”可以认为是有名字的容器。你可以将数据置于这些容器中，然后通过容器的名称就可以知道数据的类型。  
值得注意的是，在 JavaScript 编程过程中，必须先声明一个变量，这个变量才能被使用。  
此外，变量是通过 **“var”** 来声明的，例子如下：  

    <script type="text/javascript">
    <!--
    var money;
    var name;
    //-->
    </script>

使用 **“var”** 关键词也可以同时声明多个变量。例子如下：  

    <script type="text/javascript">
    <!--
    var money, name;
    //-->
    </script>
变量初始化就是在一个变量中存储一个值。  
变量初始化可以在创建变量或者再需要使用变量时进行。  
比如，需要创建一个名叫 money 的变量，然后赋值 2000.50.  
或者直接在初始化的时候对变量进行赋值：  
例子如下：  


    <script type="text/javascript">
    <!--
    var name = "Ali";
    var money;
    money = 2000.50;
    //-->
    </script>

**注意：** “var” 关键字仅能用于变量的声明或初始化。同一个 HTML 网页中，同一变量名称不能声明多次。  
 JavaScript 是一种无类型语言。这就是说， JavaScript 变量可以存储任何类型的值。与其他语言不同的是，我们不需要在变量声明阶段告诉变量其要存储的数据类型是什么。  
变量中存储的数据类型在程序执行阶段可以被改变，这些操作都是对编程人员透明的。 

为了更好的理解此处内容，你可以自己[尝试一下](http://www.tutorialspoint.com/cgi-bin/practice.cgi?file=javascript_5)。
 
###JavaScript变量作用域：
一个变量的作用域就是该变量定义后在程序中的作用范围。JavaScript 变量有两个变量作用域。  
    1.	全局变量：全局变量具有全部整体范围的作用域，这意味着它可以在 JavaScript 代码任何地方定义。  
    2.	局部变量：局部变量仅在定义它的函数体内可以访问到。函数参数对于函数来说就是局部变量。  

在函数体内部，局部变量可以与全局变量同名，此时是局部变量在起作用。如果局部变量或者函数参数与全局变量同名，那么此时全部变量会被隐藏到，并不会起作用。  
例子如下：  

    <script type="text/javascript">
    <!--
    var myVar = "global"; // Declare a global variable
    function checkscope( ) {
       var myVar = "local";  // Declare a local variable
       document.write(myVar);
    }
    //-->
    </script>
该例子产生如下结果：
  
    Local


为了更好的理解此处内容，你可以自己[尝试一下](http://www.tutorialspoint.com/cgi-bin/practice.cgi?file=javascript_6)。

### JavaScript 变量名称：
JavaScript 中变量的命名规则如下：  

1. 不能使用 JavaScript 中的保留关键字来命名变量。这些保留关键字会在下一节中介绍。比如 break 或 boolean，这些命名变量是无效的。
2. JavaScript 变量名称不能以数字 （0-9） 开头，只能以字母或下划线来命名变量。比如 123tes t就是无效的变量名。但是， _123 就是有效的变量名。
3. JavaScript 变量名称对大小写敏感。比如，Name 和 name 是两个不同的变量。

### JavaScript 保留的关键字：
下面是 JavaScript 中的保留关键字。他们不能用来命名 JavaScript 中的变量、行数、方法、循环标签或任何对象名称。  
  
<table>
   <tr>
      <td>abstract</td>
      <td>else</td>
      <td>instanceof</td>
      <td>switch</td>
   </tr>
   <tr>
      <td>boolean</td>
      <td>enum</td>
      <td>int</td>
      <td>synchronized</td>
   </tr>
   <tr>
      <td>break</td>
      <td>export</td>
      <td>interface</td>
      <td>this</td>
   </tr>
   <tr>
      <td>byte</td>
      <td>extends</td>
      <td>long</td>
      <td>throw</td>
   </tr>
   <tr>
      <td>case</td>
      <td>FALSE</td>
      <td>native</td>
      <td>throws</td>
   </tr>
   <tr>
      <td>catch</td>
      <td>final</td>
      <td>new</td>
      <td>transient</td>
   </tr>
   <tr>
      <td>char</td>
      <td>finally</td>
      <td>null</td>
      <td>TRUE</td>
   </tr>
   <tr>
      <td>class</td>
      <td>float</td>
      <td>package</td>
      <td>try</td>
   </tr>
   <tr>
      <td>const</td>
      <td>for</td>
      <td>private</td>
      <td>typeof</td>
   </tr>
   <tr>
      <td>continue</td>
      <td>function</td>
      <td>protected</td>
      <td>var</td>
   </tr>
   <tr>
      <td>debugger</td>
      <td>goto</td>
      <td>public</td>
      <td>void</td>
   </tr>
   <tr>
      <td>default</td>
      <td>if</td>
      <td>return</td>
      <td>volatile</td>
   </tr>
   <tr>
      <td>delete</td>
      <td>implements</td>
      <td>short</td>
      <td>while</td>
   </tr>
   <tr>
      <td>do</td>
      <td>import</td>
      <td>static</td>
      <td>with</td>
   </tr>
   <tr>
      <td>double</td>
      <td>in</td>
      <td>super</td>
      <td></td>
   </tr>

</table>