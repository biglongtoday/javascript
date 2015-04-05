##启用浏览器的 JavaScript 功能
目前，几乎所有浏览器均支持 JavaScript。但是，一般情况下需要用户手动的启动或禁用浏览器对 JavaScript 的支持。

本教程将指导用户了解在浏览器 （IE、Firefox 和 Opera 浏览器）中启用和禁用 JavaScript 支持的流程。  
###IE浏览器：  
如下为在 IE 浏览器中启用或禁用 JavaScript 的大致流程：  
1. 在IE浏览器的菜单栏中找到“**工具**”选项，然后点击工具选项后选择“**Internet 选项**”。  
2. 在上个步骤后出现的对话框中选择“ **安全**”标签。  
3. 选择“**自定义级别**”按钮。  
4. 向下滚动下滑条找到“ **脚本**”选项。  
5. 在“ **活动脚本**”子选项下选择“ **启动**”选项。  
6. 最后，点击“ **确定**”按钮，并退出。
  
如果需要禁用 IE 浏览器对 JaveScript 功能的支持，只需要在上述补流程的第 5 个步骤，选择” **禁用**“选项即可。  
###火狐浏览器（Firefox）：  
如下为在火狐浏览器中启用或禁用 JavaScript 的大致流程：  
1. 从火狐浏览器的菜单栏中找到“ **工具**”选项，然后选择“**选项**”。  
2. 从出现的对话框中选择“ **内容**”选项。  
3. 选择” **启用 JavaScript**”选项。  
4. 最后，点击” **确定**“按钮，并退出。
  
如果需要禁用火狐浏览器对 JaveScript 功能的支持，只需要在上述补流程的第 5 个步骤，选择” 禁用JavaScript “选项即可。  
###Opera浏览器：  
如下为在 Opera 浏览器中启用或禁用 JavaScript 的大致流程：  
1. 从 Opera 浏览器的菜单栏中找到“ **工具**”选项，然后选择“偏好”。  
2. 在出现的对话框中选择“ **高级**”选项。  
3. 从列表中选择“ **内容**”。  
4. 选择“ **启动 JavaScript**”。  
5. 最后，点击“ **确定**”按钮，并退出。

如果需要禁用 Opera 浏览器对 JaveScript 功能的支持，只需要在上述补流程的第 4 个步骤，选择”禁用 JavaScript “选项即可。  
**警告：**  
在使用 JavaScript 的过程中可以通过 `<noscript>` 标记来显示警告信息。  
可以按照下面的方式添加 `noscript`  代码。  

    <html>
    <body>
    
    <script language="javascript" type="text/javascript">
    <!--
       document.write("Hello World!")
    //-->
    </script>
    
    <noscript>
      Sorry...JavaScript is needed to go ahead.
    </noscript>
    </body>
    </html>

如果用户的浏览器不支持或者没有开启JavaScript功能，
 `</noscript>` 标记的信息就会显示在用户的屏幕上




