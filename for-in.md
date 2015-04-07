##for...in循环:  
*JavaScript* 还支持另外一种循环模式，即 **for...in** 循环。这一种类型的循环将对象属性作为参数变量来实现循环。
  
对象的概念现在还没有讨论，对于 *for...in* 循环，用起来可能会觉得不舒服。但是一旦开始了解 *JavaScript* 中的对象概念，会发现 *for..in* 循环是非常有用的。 
###语法如下   
    for (variablename in object){  
        statement
    }    
在每次迭代中将一个对象的属性赋值给变量，这个循环会持续到这个对象的所有属性都枚举完。  
###例子  
下面的例子用于打印出一个 *Web* 浏览器**导航**对象的属性：
    
    <script type="text/javascript">
    <!--
    var aProperty;
    document.write("Navigator Object Properties<br /> ");
    for (aProperty in navigator)
    {
        document.write(aProperty);
        document.write("<br />");
    }
    document.write("Exiting from the loop!");
    //-->
    </script>
运行结果：  
     
    Navigator Object Properties
    appCodeName
    appName
    appMinorVersion
    cpuClass
    platform
    plugins
    opsProfile
    userProfile
    systemLanguage
    userLanguage
    appVersion
    userAgent
    onLine
    cookieEnabled
    mimeTypes
    Exiting from the loop!  
 
为了更好的理解此处内容，你可以自己[尝试一下](http://www.tutorialspoint.com/cgi-bin/practice.cgi?file=javascript_15)。 