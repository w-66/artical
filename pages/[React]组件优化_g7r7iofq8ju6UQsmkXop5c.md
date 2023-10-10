# \[React]组件优化

-   `PureComponent`
    -   `PureComponent`重写了`shouldComponentUpdate()` \[[🖼️ 图片](../image/image_hCydPyUBum.png "🖼️ 图片")]
        -   在shouldCompoentUpdate()中进行了一次浅比较，如果旧的数据与更新的数据内存地址相同则返回false，不进行更新
