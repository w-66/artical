# \[思科]基础配置

## 基础

```纯文本
>enable          / 进入特权模式
 #conft           / 进入全局配置模式
 #hostname  xxx   /重命名设备
#enable password xxx        /设置特权口令

```

## 保存当前修改/运行的配置：

\#write

将 RAM 中的当前配置存储到NVRAM 中，下次路由器启动就是执行保存的配置

\#router#Copy   running-config    startup-config  &#x20;

命令与write 效果一样

## 静态路由

```纯文本
ip  route  xxx.xxx.xxx.xxx  xxx.xxx.xxx.xxx  下一跳
```

\#enable password xxx        /设置特权口令

\#hostname  xxx   /重命名设备
\#enable password xxx        /设置特权口令


\#hostname  xxx   /重命名设备
\#enable password xxx        /设置特权口令


\#conft           / 进入全局配置模式

\#hostname  xxx   /重命名设备

\#enable password xxx        /设置特权口令
