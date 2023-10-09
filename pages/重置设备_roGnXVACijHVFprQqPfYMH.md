# 重置设备

恢复出厂设置；清除配置

[https://support.huawei.com/eirobot/#](https://support.huawei.com/eirobot/# "https://support.huawei.com/eirobot/#")

***

方法一、通过命令行方式 &#x20;

1、清空设备下次启动使用的配置文件内的内容，并取消指定系统下次启动时使用的配置文件。 &#x20;

\<HUAWEI> reset saved-configuration &#x20;

The action will delete the saved configuration in the device. &#x20;

The configuration will be erased to reconfigure. Continue? \[Y/N]:**y** &#x20;

2、重启设备。 &#x20;

\<HUAWEI> reboot &#x20;

Info: The system is now comparing the configuration, please wait. &#x20;

Warning: All the configuration will be saved to the configuration file for the next startup:, Continue?\[Y/N]:**n**（注意：此处提示是否保存当前配置，须选择"N"） &#x20;

System will reboot! Continue?\[Y/N]:**y** （再选"Y"，重启设备） &#x20;

方法二、通过web网页方式 &#x20;

单击导航栏中“系统管理 > 恢复出厂配置”>选择“恢复出厂配置”> 单击“确定”。
