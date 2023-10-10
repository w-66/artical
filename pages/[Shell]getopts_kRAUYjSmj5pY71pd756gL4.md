# \[Shell]getopts

| 分类   | shell 脚本         |
| ---- | ---------------- |
| 简介   |                  |
| 标签   | 内置               |
| 创建时间 | 2022/06/23 11:47 |

<https://www.itbaoku.cn/post/1964890/Retrieving-multiple-arguments-for-a-single-option-using-getopts-in-Bash>

-   \[En]`man getopts`

    getopts is used by shell [procedures](procedures_4GvgUFGdb4FskNXQGtTawe.md "procedures") to [parse](parse_39Hy8CZEQP11RG2fUyYvn7.md "parse") [positional](positional_cdRreeLGcFF6Xu7L7g3y8N.md "positional") [parameters](parameters_wkHweCfqLmjtA8aBCrSGRU.md "parameters"). \[...[used](used_h52N5bC48YuyaE5fxUUtsC.md "used") [by](by_t4A4ncLjGUjTXrDMUFWo8d.md "by")...[to](to_sozhpxTKNj1Mpm29xcsBNo.md "to")...]
    getopts被shell程序用来解析位置参数。
    ```纯文本
    getopts optstring name [args]

    getopts is used by shell procedures to parse positional parameters.  optstring con‐
    tains the option characters to be recognized; if  a  character  is  followed  by  a
    colon,  the  option is expected to have an argument, which should be separated from
    it by white space.  The colon and question mark  characters  may  not  be  used  as
    option  characters.  Each time it is invoked, getopts places the next option in the
    shell variable name, initializing name if it does not exist, and the index  of  the
    next argument to be processed into the variable OPTIND.  OPTIND is initialized to 1
    each time the shell or a shell script is invoked.  When an option requires an argu‐
    ment,  getopts  places  that argument into the variable OPTARG.  The shell does not
    reset OPTIND automatically; it must be manually reset  between  multiple  calls  to
    getopts within the same shell invocation if a new set of parameters is to be used.

    When  the  end of options is encountered, getopts exits with a return value greater
    than zero.  OPTIND is set to the index of the first non-option argument,  and  name
    is set to ?.

    getopts  normally parses the positional parameters, but if more arguments are given
    in args, getopts parses those instead.
    getopts can report errors in two ways.  If the first character of  optstring  is  a
    colon, silent error reporting is used.  In normal operation diagnostic messages are
    printed when invalid options or missing option arguments are encountered.   If  the
    variable OPTERR is set to 0, no error messages will be displayed, even if the first
    character of optstring is not a colon.

    If an invalid option is seen, getopts places ? into name and, if not silent, prints
    an  error  message  and  unsets OPTARG.  If getopts is silent, the option character
    found is placed in OPTARG and no diagnostic message is printed.

    If a required argument is not found, and getopts is not silent, a question mark (?)
    is  placed  in  name,  OPTARG  is  unset,  and a diagnostic message is printed.  If
    getopts is silent, then a colon (:) is placed in name and  OPTARG  is  set  to  the
    option character found.

    getopts  returns true if an option, specified or unspecified, is found.  It returns
    false if the end of options is encountered or an error occurs.
    ```

getpots是Shell命令行参数解析工具，旨在从Shell Script的命令行当中解析参数。

getopts被Shell程序用来分析位置参数，option包含需要被识别的选项字符，**如果这里的字符后面跟着一个冒号，表明该字符选项需要一个参数，其参数需要以空格分隔**。冒号和问号不能被用作选项字符。getopts每次被调用时，它会将下一个选项字符放置到变量中，OPTARG则可以拿到参数值；如果option前面加冒号，则代表忽略错误；

-   冒号在开头，在传入参数为空时，不会报错

语法格式：getopts \[option\[:]] \[DESCPRITION] VARIABLE

option：表示为某个脚本可以使用的选项  &#x20;

":"：如果某个选项（option）后面出现了冒号（":"），则表示这个选项后面可以接参数（即一段描述信息DESCPRITION） &#x20;

VARIABLE：表示将某个选项保存在变量VARIABLE中



-   示例1：学习示例
    ```sql
    ]# vim getopts_test.sh
    while getopts ":a:b:c:" opt
    do
     case $opt in
      a)
      echo "参数a的值$OPTARG"
      ;;
      b)
      echo "参数b的值$OPTARG"
      ;;
      c)
      echo "参数c的值$OPTARG"
      ;;
      ?)
      echo "未知参数"
      exit 1;;
     esac
    done
    ```
    ```sql
    ./getopts_test.sh -a 1 -b 2 -c 333
    参数a的值1
    参数b的值2
    参数c的值333
    ```
-   示例a.1：传入IP端口判断端口是否开放
    ```sql
    while getopts ":i:p:" opt
    do
     case $opt in
      i)  
         ip=$OPTARG ;;  
      p)  
         port=$OPTARG ;;  
      ?)  
         echo "未知参数"
      exit 1 ;;           # 返回退出上方shell的退出状态为1 
     esac
    done
    #
    #
    #
    echo '############基本信息#############'
      echo "-i传入IP是:${ip}"
      echo "-p传入端口是:${port}"
    #
    echo '############测试结果#############'
    nc -v -w  -z ${ip} ${port} &> /dev/null
    age=$?
    if (( $age == 0 )); then
        echo "${ip}的${port}端口正常"
    else
        echo "${ip}的${port}端口异常"
    fi
    #
    ```
