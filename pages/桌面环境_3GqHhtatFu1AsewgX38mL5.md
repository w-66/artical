# 桌面环境

Linux桌面软件；桌面环境；桌面界面；Linux桌面；

***

[https://blog.csdn.net/dyausasd/article/details/92844891](https://blog.csdn.net/dyausasd/article/details/92844891 "https://blog.csdn.net/dyausasd/article/details/92844891")

[KDE](KDE_bi2ZucoPnajnpvseducdup.md "KDE")

[GNOME](GNOME_m6adwiGa7ytFitA7Vj5FkH.md "GNOME")

[Unity](Unity_wyn325DohgN8ihzakmrpup.md "Unity")

[MATE](MATE_2UQ1W63wym36yd1hGPNeRT.md "MATE")

[Cinnamon](Cinnamon_4ATHGPDSXANFNJoLB6qFdt.md "Cinnamon")

适用于较老硬件设备的 Linux 桌面环境

图形化桌面环境的弊端在于它们要占用相当一部分的系统资源来保证正常运行。在 Linux 发展之初，Linux 的标志和卖点之一就是它可以运行在处理能力较弱的老旧 PC 上，这些 PC 无力运行较新的 Windows 桌面。

然而随着 KDE 和 GNOME 桌面环境的普及，情况发生了变化。运行 KDE 或 GNOME 桌面要占用的内存资源和较新的 Windows 桌面环境旗鼓相当。

如果你的 PC 已经有些年代了，也不要泄气。Linux 开发人员已经联手让 Linux 返璞归真。他们开发了一些低内存开销的图形化桌面应用，提供了能够在老旧 PC 上完美运行的基本功能。尽管这些图形化桌面环境并没有大量专为其设计的应用，但它们仍然能运行许多基本的图形化程序，支持如文字处理、电子表格、数据库、绘图以及多媒体等功能。

下表列出了一些可在配置较低的 PC 和笔记本电脑上运行的轻量级 Linux 图形化桌面环境。

Fluxbox  一个没有面板的轻型桌面，仅有一个可用来启动程序的弹出式菜单。
Xfce  和 KDE 很像的一个桌面，但少了很多图像以适应低内存环境。
JWM  Joe 的窗口管理器（Joe’s Window Manager），非常适用于低内存低硬盘空间环境的超轻型桌面。
Fvwm  支持如虚拟桌面和面板等高级桌面功能，但能够在低内存环境中运行。
fvwm95  从 fvwm 衍生而来，但看起来更像是 Windows 95 桌面。

以上这些图形化桌面环境并不如 KDE 或 GNOME 桌面一样绚丽，但却提供了恰到好处的基本图形化功能。

如果你用的是老旧 PC，尝试一下基于上述某个桌面环境的 Linux 发行版，看看怎么样，可能会有惊喜哦。





查看桌面环境



我们可以通过环境变量 DESKTOP\_SESSION 来查看当前 Linux 发行版使用了哪种桌面环境，例如：

\[[c.biancheng.net](http://c.biancheng.net "c.biancheng.net")]\$ echo \$DESKTOP\_SESSION
gnome-classic

这表明我使用的是 GNOME。

另外，你也可以查看/etc下有没有对应的目录，例如 gnome 目录或者 kde 目录，如果有的话，就说明已经安装了。

echo \$DESKTOP\_SESSION
