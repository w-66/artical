# 指定桌面文件夹

1.  配置文件

```python
/home/你的用户文件夹/.config/user-dirs.dirs
```

参数：

```python
XDG_DESKTOP_DIR="$HOME/Desktop"
```

例如`XDG_DESKTOP_DIR="$HOME/Desktop"`

这个就是把用户的桌面设置在Desktop文件夹



-   [知乎答案](https://zhuanlan.zhihu.com/p/31640919 "知乎答案")

    装好了一个简体中文的Linux发行版，一般家目录下面都默认会有桌面，模板，音乐，公共，视频，文档，下载，图片等目录，有些发行版，这些目录名字是中文的，也就是与locale相关的，有些是英文的。

    其实这些目录是由 [http://freedesktop.org](http://freedesktop.org/ "http://freedesktop.org") 定义的，由 xdg-user-dirs程序来管理，其主页为：[xdg-user-dirs](https://freedesktop.org/wiki/Software/xdg-user-dirs/ "xdg-user-dirs") 。

    在archlinux下它属于xdg-user-dirs包
    ```python
    $ pacman -Qo xdg-user-dir
    ```
    /usr/bin/xdg-user-dir 属于 xdg-user-dirs 0.14-3

    安装这个程序后，进thunar后，可以看见不同的默认目录，会有不同的图标，一般的图标主题都会为这几个默认目录设定与普通目录不同的图标。

    在模板文件夹中放几个模板，在右键“创建文档”下级菜单中就能看见定义的模板了，如果没有装xdg-user-dirs就看不到。

    其主要配置文件为：

    一般定义为：
    ```python
    XDG_DESKTOP_DIR=”HOME/Desktop”XDGDOWNLOADDIR=”HOME/Downloads” 
    XDG_TEMPLATES_DIR=”HOME/Templates”XDGPUBLICSHAREDIR=”HOME/Public” 
    XDG_DOCUMENTS_DIR=”HOME/Documents”XDGMUSICDIR=”HOME/Music” 
    XDG_PICTURES_DIR=”HOME/Pictures”XDGVIDEOSDIR=”HOME/Videos”
    ```
    另一个为：
    ```python
    ~/.config/user-dirs.locale
    ```


    一般定义为：跟你的系统语言相关。

    以上两个配置文件在运行xdg-user-dirs-update后会自动生成，你如果想改动设置的话，比如将中文的改为英文的。
    ### 方法一
    是先运行` xdg-user-dirs-update` 命令，然后修改 `~/.config/user-dirs.dirs` 文件，将其中的中文目录改为英文目录。
    ### 方法二
    是先删除 \~/.config/user-dirs.dirs 文件，再运行 LANG=en\\\_US.UTF-8 xdg-user-dirs-update 命令，让其重新生成 \~/.config/user-dirs.locale 及 \~/.config/user-dirs.dirs 配置文件。

    第一种方法较好，第二种方法只是临时设置了语言。

    当然你可以更狠的去修改其源文件中中文翻译为英文，然后生成mo文件放到系统中去，这样子不管系统语言是中文还是英文生成的目录都会是英文的，其中文mo文件为：
    ```python
    /usr/share/locale/zh_CN/LC_MESSAGES/xdg-user-dirs.mo
    ```
