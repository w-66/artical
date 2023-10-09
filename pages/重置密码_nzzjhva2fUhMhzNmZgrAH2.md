# 重置密码

思科忘记密码；思科交换机重置密码；忘记console密码;忘记enable密码；思科密码重置；

***

1.  SW上电，并按下mode
2.  控制台
    ```纯文本
    The system has been interrupted, or encountered an error
    during initializion of the flash filesystem.  The following
    commands will initialize the flash filesystem, and finish
    loading the operating system software:

        flash_init
        load_helper
        boot


    switch: 
    ```
3.  在控制台上输入flash\_init后回车

    查看文件 `dir flash:/`
4.  `switch:remane flash:/config.txt flash:/config.old`
5.  重启 `boot`



恢复之前的配置：`rename flash:/config.old flash:/config.text`

恢复之前的配置到当前(running-config)配置：`copy flash:/config.text system:/running-config`

然后修改console密码
