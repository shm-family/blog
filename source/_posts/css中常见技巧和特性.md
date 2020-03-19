---
title: css中常见技巧和特性
date: 2020-03-19 15:37:53
tags:
---
对css一些常见用法和特性的整理


### FlexBox和决定定位

也许你会认为：当在在弹性盒子中放置绝对定位元素时，它将不再是弹性盒子中的一部分。
但是；如果将子元素设置为绝对定位，但不设置任何top/right/bottom/left属性，则flexbox仍然起作用。
奇怪的是，它是存在一定意义的。当把`position: absolute;`应用到元素上时，它会停留在原处，甚至会随着内容大小一起调整，直到设置定位属性。因为它除了不影响其他任何内容之外，没有任何具体的定位说明。

<a href="https://www.chenhuijing.com/blog/flexbox-and-absolute-positioning/#%F0%9F%8E%AE" target="__black">具体参考```陈慧静博客```</a>

<iframe height="400" style="width: 100%;" scrolling="no" title="flexbox和就绝对定位" src="https://codepen.io/ryanypm/embed/wvaXLxG?height=265&theme-id=dark&default-tab=css,result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/ryanypm/pen/wvaXLxG'>flexbox和就绝对定位</a> by ryanypm
  (<a href='https://codepen.io/ryanypm'>@ryanypm</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

### box-sizing

 box-sizing定义了 user agent 应该如何计算一个元素的总宽度和总高度。

```
    box-sizing的常用属性有:
    content-box
    border-box
```
常用的场景是列表:

![](/blog-site/images/box-sizing-demo.png)

当横排的列表设置了固定宽度时，子元素同时设置了border边框，当子元素数量超过一定数量时会超过父容器。
当我们设置了: box-sizing: border-box;的时候，计算方式会以padding+content+border作为内容宽度。这样子元素的内容宽度就会包含border不会超出父容器。