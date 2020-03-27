---
title: css中常见技巧和特性
date: 2020-03-19 15:37:53
tags:
---
对css一些常见用法和特性的整理


# FlexBox和决定定位

也许你会认为：当在在弹性盒子中放置绝对定位元素时，它将不再是弹性盒子中的一部分。
但是；如果将子元素设置为绝对定位，但不设置任何top/right/bottom/left属性，则flexbox仍然起作用。
奇怪的是，它是存在一定意义的。当把`position: absolute;`应用到元素上时，它会停留在原处，甚至会随着内容大小一起调整，直到设置定位属性。因为它除了不影响其他任何内容之外，没有任何具体的定位说明。

<iframe height="400" style="width: 100%;" scrolling="no" title="flexbox和就绝对定位" src="https://codepen.io/ryanypm/embed/wvaXLxG?height=265&theme-id=dark&default-tab=css,result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/ryanypm/pen/wvaXLxG'>flexbox和就绝对定位</a> by ryanypm
  (<a href='https://codepen.io/ryanypm'>@ryanypm</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

<br>
<br>

***

# content 属性 attr

```
// html
<div data-tip="这是一个提示">
  鼠标放这里
</div>

// css
div {
  position: relative;
  font-size: 14px;
  color: #333;
  background-color: red;
  display: inline-block;
  margin-top: 100px;
}

div:hover::after {
  content: attr(data-tip);
  font-size: 12px;
  color: #ffffff;
  border-radius: 5px;
  background-color: rgba(0, 0, 0, 0.8);
  position: absolute;
  left: 0;
  top: -40px;
  width: 100px;
  height: 30px;
  text-align: center;
  line-height: 30px;
}

div:hover::before {
  content: "";
  border-width: 6px;
  border-color: rgba(0, 0, 0, 0.8) transparent transparent transparent;
  border-style: solid;
  position: absolute;
  left: 10px;
  top: -10px;
}
```

<br>
<br>

<iframe height="265" style="width: 100%;" scrolling="no" title="content 属性 attr" src="https://codepen.io/ryanypm/embed/mdJzmzM?height=265&theme-id=dark&default-tab=css,result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/ryanypm/pen/mdJzmzM'>content 属性 attr</a> by ryanypm
  (<a href='https://codepen.io/ryanypm'>@ryanypm</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

<br>
<br>
<br>

# :valid 和 :invalid 表单即时校验

```
<form>
  <div class="form-group">
    <label>name</label>
    <input type="text" required placeholder="请输入名称">
  </div>
  <div class="form-group">
    <label>email</label>
    <input type="email" required placeholder="请输入邮箱">
  </div>
  <div class="form-group">
    <label>homepage</label>
    <input type="url" placeholder="请输入url">
  </div>
</form>
```

<br>

<iframe height="265" style="width: 100%;" scrolling="no" title=":valid 和 :invalid 表单即时校验" src="https://codepen.io/ryanypm/embed/WNvaObL?height=265&theme-id=dark&default-tab=html,result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/ryanypm/pen/WNvaObL'>:valid 和 :invalid 表单即时校验</a> by ryanypm
  (<a href='https://codepen.io/ryanypm'>@ryanypm</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

<br>
<br>

# 锚点元素 :target

```
.collapse {
  width: 600px;
}
.collapse-item {
  border: 1px solid #ccc;
  background-color: #f5f5f5;
}

.collapse-item a {
  text-decoration: none;
  padding: 5px 15px;
  display: block;
  color: #337ab7;
}

.collapse-item .collapse-body {
  display: none;
  padding: 10px 15px;
}

.collapse-item .collapse-body:target {
  display: block;
}

```

<br>

<iframe height="465" style="width: 100%;" scrolling="no" title="锚点元素 :target" src="https://codepen.io/ryanypm/embed/wvaYeeN?height=265&theme-id=dark&default-tab=html,result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/ryanypm/pen/wvaYeeN'>锚点元素 :target</a> by ryanypm
  (<a href='https://codepen.io/ryanypm'>@ryanypm</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

# 元素左右对齐
> margin-left: auto;
```
<div class="box">
  <div class="cover"></div>
  <div class="info">
    <h5>你的名字</h5>
    <p>梦想在诗和远方</p>
  </div>
  <button>关注我</button>
</div>
```

<iframe height="265" style="width: 100%;" scrolling="no" title="元素两端对齐" src="https://codepen.io/ryanypm/embed/zYGMVOV?height=265&theme-id=dark&default-tab=css,result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/ryanypm/pen/zYGMVOV'>元素两端对齐</a> by ryanypm
  (<a href='https://codepen.io/ryanypm'>@ryanypm</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

# 通过css设置rem

```
html {
  font-size: calc(100vw / 7.5);
}
```

# 设置圆角边框头像

<iframe height="265" style="width: 100%;" scrolling="no" title="background-clip" src="https://codepen.io/ryanypm/embed/mdJabEy?height=265&theme-id=dark&default-tab=css,result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/ryanypm/pen/mdJabEy'>background-clip</a> by ryanypm
  (<a href='https://codepen.io/ryanypm'>@ryanypm</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

# ::first-letter 段落首字间隔
```
p::first-letter{
  font-size: 6em;
  line-height: 1;
  float: left;
}

p {
  width: 500px;
}
```

<iframe height="265" style="width: 100%;" scrolling="no" title="用::first-letter来实现段落首字间隔" src="https://codepen.io/ryanypm/embed/zYGyObX?height=265&theme-id=dark&default-tab=html,result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/ryanypm/pen/zYGyObX'>用::first-letter来实现段落首字间隔</a> by ryanypm
  (<a href='https://codepen.io/ryanypm'>@ryanypm</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

# 等等
https://codepen.io/chriscoyier/full/pMRgwW