# \[HTML]background

> 📌此处都是CSS的样式属性

<https://developer.mozilla.org/zh-CN/docs/Web/CSS/background>

# background-position

<https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-position>

# background-[attachment](attachment_qQXYWGEysAoqBpUHPp8ss4.md "attachment")

**`background-attachment`** [CSS](https://developer.mozilla.org/en-US/docs/CSS "CSS") 属性决定背景图像的位置是在视口内固定，或者随着包含它的区块滚动。

<https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-attachment>

# background-[repeat](repeat_rXvcZVytghdxBtoGqk4pgL.md "repeat")

<https://developer.mozilla.org/zh-CN/docs/Web/CSS/background-repeat>

```html
/* 单值语法 */
background-repeat: repeat-x;
background-repeat: repeat-y;
background-repeat: repeat;
background-repeat: space;
background-repeat: round;
background-repeat: no-repeat;

/* 双值语法: 水平horizontal | 垂直vertical */
background-repeat: repeat space;
background-repeat: repeat repeat;
background-repeat: round space;
background-repeat: no-repeat round;

background-repeat: inherit;
```

repeat
图像会按需重复来覆盖整个背景图片所在的区域. 最后一个图像会被裁剪, 如果它的大小不合适的话.

[space](space_kzCekXJZ7jfaevcZfrywNR.md "space")  &#x20;
图像会尽可能得重复, 但是不会裁剪. 第一个和最后一个图像会被固定在元素(element)的相应的边上, 同时空白会均匀地分布在图像之间. background-position属性会被忽视, 除非只有一个图像能被无裁剪地显示. 只在一种情况下裁剪会发生, 那就是图像太大了以至于没有足够的空间来完整显示一个图像.

[round](round_vyadtbz49AFt18uUrXmkkD.md "round")  &#x20;
随着允许的空间在尺寸上的增长, 被重复的图像将会伸展(没有空隙), 直到有足够的空间来添加一个图像. 当下一个图像被添加后, 所有的当前的图像会被压缩来腾出空间. 例如, 一个图像原始大小是260px, 重复三次之后, 可能会被伸展到300px, 直到另一个图像被加进来. 这样他们就可能被压缩到225px.
译者注: 关键是浏览器怎么计算什么时候应该添加一个图像进来, 而不是继续伸展.

no-repeat  &#x20;
图像不会被重复(因为背景图像所在的区域将可能没有完全被覆盖). 那个没有被重复的背景图像的位置是由background-position属性来决定.

