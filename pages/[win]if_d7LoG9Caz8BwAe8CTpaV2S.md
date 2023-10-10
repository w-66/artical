# \[win]if

`if`执行批处理程序中的条件处理。

***

> 执行成功是0 ，失败是1



判断两个字符串是否相等，if "字符串1"=="字符串2" command 语句;

判断两个数值是否相等，if 数值1 equ 数值2 command 语句；

判断判断驱动器，文件或文件夹是否存在，if exist filename command 语句;

判断变量是否已经定义，if defined 变量 command 语句；

判断上个命令的返回值，if errorlevel 数值 command 语句。

```纯文本
/i  不区分大小写(默认区分)
```

-   示例1 `if`、`goto`
    ```纯文本
    ::::::::::改变颜色.bat::::::::::
    @echo off
    echo 您希望字体的颜色是红色还是绿色？

    :RETRY
    set /p choice=请输入您的选择，R 或者 G ：

    if "%choice%"=="R" goto R
    if "%choice%"=="r" goto R
    if "%choice%"=="G" goto G
    if "%choice%"=="g" goto G
    goto RETRY

    :R
    color c
    echo 您选择了红色字体
    pause
    exit

    :G
    color a
    echo 您选择了绿色字体
    pause
    exit
    :::::::::::::::::::::::::::::::: 
    ```
-   判断是否是回车
    ```纯文本
    @echo off
    echo "判断是否是回车"
    set /p enter ="回车"
    if "%enter%"== "" (echo enter ) else (echo "no enter"  )
    pause
    ```
-   [通过批处理检测是否输入回车键或者空格键](https://www.lmdouble.com/113311107.html "通过批处理检测是否输入回车键或者空格键")
    ```纯文本
    @echo off
    :start
    cls
    set a=
    set /p a=请输入空格或者回车键，会自动检测按下了哪个键:

    REM 注意 "%a%"==后面的参数，两者不一样，一个是直接两个双引号，一个是双引号中间有一个空格。
    if "%a%"=="" echo 你敲了回车键
    if "%a%"==" " echo 你按下了空格键
    echo.
    echo.
    echo 返回，继续。。。
    pause>nul
    goto start
    exit
    ```

```纯文本
执行批处理程序中的条件处理。

IF [NOT] ERRORLEVEL number command
IF [NOT] string1==string2 command
IF [NOT] EXIST filename command

  NOT               指定只有条件为 false 的情况下，Windows 才
                    应该执行该命令。

  ERRORLEVEL number 如果最后运行的程序返回一个等于或大于
                    指定数字的退出代码，指定条件为 true。

  string1==string2  如果指定的文字字符串匹配，指定条件为 true。

  EXIST filename    如果指定的文件名存在，指定条件为 true。

  command           如果符合条件，指定要执行的命令。如果指定的
                    条件为 FALSE，命令后可跟 ELSE 命令，该命令将
                    在 ELSE 关键字之后执行该命令。

ELSE 子句必须出现在同一行上的 IF 之后。例如:

    IF EXIST filename. (
        del filename.
    ) ELSE (
        echo filename. missing.
    )
```

# 示例

## 示例

-   示例：判断用户输入的数字是否等于 123[\[win|bat\]if](\[win-bat]if_2VXCtuStMcwYYvPUdaiAqA.md "\[win|bat]if")&#x20;
    ```powershell
    @echo off

    setlocal enabledelayedexpansion

    set /p "user_input=请输入一个数字: "

    if !user_input! equ 123 (
      echo 你输入的数字等于 123
    ) else (
      echo 你输入的数字不等于 123
    )

    endlocal

    ```

***

-   **判断两个字符串是否相等，if"字符串1"=="字符串2" command 语句 **

    注意：在"字符串1"`==`"字符串2"中，是两个连续的"="
    ```纯文本
    @echo off
    set /p var1=请输入第一个比较的字符：
    set /p var2=请输入第二个比软的字符：
    if "%var1%"=="%var2%" (echo 输入的两个字符相同) else echo 输入的两个字符不相同
    pause
    ```
    执行后会要求你输入两个字符串，然后批处理判断它俩是否相同。在判断字符串是否相等的时候，if是会**区分大小写**。
-   **判断两个数值是否相等，if 数值1 equ 数值2 command 语句 **

    语句中的equ 表示相等的意思，判断两个数值之间的大小关系还有以下关系符号：

    `equ`  等于 equal &#x20;
    `gtr`  大于 greater than &#x20;
    `geq`  大于或等于 greater than or equal &#x20;
    `lss`  小于 less than &#x20;
    `leq`  小于或等于  less than or equal &#x20;
    `neq`  不等于  no equal
    -   判断数值是否大于等于10
        ```纯文本
        @echo off
        set /p var=请输入一个数字:
        if %var% geq 10 (echo 此数大于或等于10) else echo 此数小于10
        pause
        ```
    -   字符串比较
        ```纯文本
        @echo off
        if "12" lss "4" (echo 12竟然小于4哦?) else echo 12当然不会小于4的！
        pause

        执行的结果是：12竟然小于4哦?
        --------------------------------------
        if 12 lss 4 (echo 12竟然小于4哦?) else echo 12当然不会小于4的！
        Pause

        执行的结果是：12当然不会小于4的！
        ```
        ☆注意：if 比较字符串与比较数字 之间的区别,它们的区别体现在引号""上面,请看下面的例子

        如果要比较的两个元素加了双引号""，那么会被当成是字符的比较。两个元素作比较的流程是：先比较两个元素 &#x20;
        的首位，如果首位相同，再比较第二位，如果第二位相同，再比较第三位。

        ☆建议：如果是字符串的比较就使用双引号"" 是数字的比较就不用双引号了！
-   **判断判断驱动器、文件或文件夹是否存在，****`if exist filename command`**
    -   判断e: 是否存在！
        ```纯文本
        @echo off
        if exist "e:" (echo e盘存在) else echo e盘不存在
        pause>nul

        ```
    -   判断文件是否存在
        ```纯文本
        @echo off
        if exist d:\123.bat (echo 123.bat文件存在！) else echo 123.bat文件不存在！
        pause
        ```
        > 这个例子是用来判断123.bat文件是否存在的，但并不严谨！如果123.bat是一个文件夹而不是一个文件时，上面的判断就不行了！那么如何判断指定的文件123.txt是否存在？
        `dir /a-d` 显示当前目录中的非目录文件
        ```纯文本
        @echo off
        dir /a-d d:\123.bat >nul 2>nul
        if %errorlevel%==0 (echo 123.bat文件存在！) else echo 123.bat文件不存在！
        Pause
        ```
        先用dir的/a-d参数去除123.bat的目录属性，指定说明要搜索的123.bat是文件而不是文件夹，并把结果（包括正确和错误）屏蔽(>nul 2>nul)，如果dir找到了文件123.bat，那么其errorlevel值(dir命令的退出编码)会被设为0，否则为1则是没有此文件。当然也可以用||和&&来判断。关于为什么要用`if %errorlevel%==0` 而不用`if errorlevel 0` 呢？在后面if errorlevel中会有说明！
    -   判断文件夹是否存在
        ```纯文本
        @echo off
        if exist test\ (echo test 是文件夹) else echo test 是文件
        pause
        ```
-   **判断变量是否已经定义，****`if defined 变量 command 语句`**** &#x20;
    这是一个判断变量是否已被定义的语句，我们还是先看例子，**
    -   例
        ```纯文本
        @echo off
        if defined a (echo 变量 a 已定义) else (echo 变量 a 没有被定义)
        pause
        ```
    -   例
        ```纯文本
        @echo off
        set a=
        if defined a (echo 变量 a 已定义) else (echo 变量 a 没有被定义)
        pause
        ```
        ![](../image/image_OPX9r7ApNn.png)
        ```纯文本
        @echo off
        set a=1
        if defined a (echo 变量 a 已定义) else (echo 变量 a 没有被定义)
        pause
        ```
        ![](../image/image_INpjSWbAqr.png)
    > 当我们用if defined 变量 command 语句判断变量是否被定义时，请注意 变量 为不使用引导符号%的变量名，不能用写为%变量%，否则出错。
    -   例
        ```纯文本
        @echo off
        set var1=5
        if defined var1 (echo 变量var1已定义) else (echo 变量var1没有被定义)
        set /p var2=请输入一个数字:
        if defined %var2% (echo 变量var2已定义) else (echo 变量var2没有被定义)
        pause
        ```
        ![](../image/image_tBcySio0ht.png)
        ```纯文本
        @echo off  
        set var1=5  
        if defined var1 (echo 变量var1已定义) else (echo 变量var1没有被定义)  
        set /p var2=请输入一个数字:  
        if defined var2 (echo 变量var2已定义) else (echo 变量var2没有被定义)  
        pause
        ```
        ![](../image/image_Y6SmLuEooX.png)
-   **判断上个命令的反回值，if errorlevel 数值 command 语句**

    这个语句是用于判断上一个命令执行的返回值errorlevel，我们还是先来看看例子
    ```纯文本
    @echo off
    net user
    if %errorlevel% == 0 (echo net user 命令执行成功) else (echo net user 命令执行失败)
    Pause
    ```
    ![](../image/image_e9DACtoqQ2.png)
    ***
    错误示范
    ```纯文本
    @echo off
    set /p input=请输入任意一条命令：
    if errorlevel 0 (echo %input% 命令执行成功) else (echo %input% 命令执行失败)
    pause

    用这种语法,不管你前面的命令，是否执行成功,它都会认为命令成功了。
    ```
    \#`%errorlevel%`

    if errorlevel  语句的特点： &#x20;


    当使用  if errorlevel 0 cmmand 句式时，它的含义是：如果返回的错误码值大于或等于0 的时候，将执行cmmand &#x20;
    操作； &#x20;
    当使用  if %errorlevel%==0 cmmand 句式时，它含义是：如果返回的错误码值等于0 的时候，将执行cmmand操作。

    一般上一条命令的执行结果返回的值只有两个，"成功"用0 表示 "失败"用 1 表示，实际上，errorlevel 返回值可以在0\~255 之间，  例如xcopy 默认的errorlevel 值就有5 个，分别表示5 种执行状态：

    0复制文件成功 &#x20;
    1 未找到复制文件 &#x20;
    2 用户通过CTRL C 终止了xcopy操作 &#x20;
    4 出现了初始化错误  &#x20;
    5 出现了磁盘写入错误
-   对于if 条件语句，常用的也就上面那5条吧，下面我们来看一下它的两种格式：
    -   if条件语句的完整格式是：if 条件表达式 (语句1) else (语句2)&#x20;

        它的含义是：如果 条件表达式 成立，就执行 语句1，否则，将执行 语句2。?  else后的 语句2 也可以不用括号括起。
    -   if条件语句的简单格式是：if 条件表达式 (语句)

        它的含义是：如果 条件表达式 成立，将执行 语句，否则，什么都不做。条件表达式后的 语句 也可以不用括号括起。
        ```纯文本
        @echo off
        if exist "d:\123.txt" (del "d:\123.txt")
        pause
        ```
        ```纯文本
        @echo off
        if exist "d:\123.txt" del "d:\123.txt"
        pause
        ```
-   补充1：对于if 语句前面的5种基本语法，都可以加上`not`参数

    1。if not "字符串1"=="字符串2" command 语句; &#x20;
    2。if not数值1 equ 数值2 command 语句； &#x20;
    3。If not exist filename command 语句; &#x20;
    4。if not defined 变量 command 语句； &#x20;
    5。if not errorlevel 数值 command 语句。

    例
    ```纯文本
    @echo off
    if not exist "c:\" (echo  C盘存在) else echo  C盘不存在
    pause
    ```
    执行后显示：C盘不存在

    不会吧，例18中执行后显示：C盘不存在，这简值是在说瞎话了，那到底是什么回事呢？

    if not exist "c:\\" (echo  C盘存在) else echo  C盘不存在 &#x20;
    此语句中文意思：如果不存在C:\ 就执行显示C盘存在；否则<指的是存在C:\\>就执行显示C盘不存在。 &#x20;
    注：if exist 意为如果存在,那么if not exist就是如果不存在

    你的C盘当然是实实在在存在的啦，根椐上面的中文分得知，那执行例18后就显示为：C盘不存在  通过分析例18,你 &#x20;
    应该明白if语句中not参数是怎么用了吧！
-   补充2：if嵌套

    例
    ```纯文本
    @echo off
    set a=55
    if %a% geq 50 (
       if %a% geq 80 (
           if %a% geq 100 (
               echo a大于等于100
           ) else echo a小于100
       ) else echo a小于80
    ) else echo a小于50
    pause
    ```
    这是一种比较规范的写法，那这种写法是怎样写的呢？那我们一步步的来：

    第一步： &#x20;

    ```纯文本
    if  %a% geq 50 ( ) else echo a小于50
    ```
    第二步：在第一步geq 50 后面的括号（）里按两下回车，主要是空两行出来。 &#x20;

    ```纯文本
    if  %a% geq 50 (  
       if  %a% geq 80 ( )else echo小于80  
    ) else echo a小于50
    ```
    第三步：在第二步geq 80 后面的括号（）里按两下回车，主要是空两行出来。 &#x20;

    ```纯文本
    if  %a% geq 50 (  
       if  %a% geq 80 (  
          if  %a% geq 100 ( ) else echo a小于100  
       )else echo小于80  
    ) else echo a小于50
    ```
    第四步：在第三步geq 100 后面的括号（）里按两下回车，主要是空两行出来。 &#x20;

    ```纯文本
    if  %a% geq 50 (  
       if  %a% geq 80 (  
          if  %a% geq 100 (  
             echo a大于等于100  
          ) else echo a小于100  
       )else echo小于80  
    ) else echo a小于50
    ```
    上面的代码中，if  %a% 和 )else 要适当的缩进，以达到写书清晰！

