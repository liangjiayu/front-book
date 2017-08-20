## line-height

#### 定义

- 两行文字的基线的距离

### 高度原理

- 元素的高度不是文字撑开的，而是`line-height`撑开的
- 高度的表现，`内容区域`+`行间距`= `行高`
- 其中`内容区域`是由`font-size`和`font-family`决定的，不同字体是不一样的
- 行间距是上下拆分的

**总结**

**行高决定内联盒子的高度，通过行高和字体大小计算出行间距，可能是负值，行间距会上下拆分在字体的上下。单行文本垂直居中的原理**

**`p`标签的内部原理，由多个单行文字盒子组成，每一行的单行盒子的高度都是`line-height`决定的，表现为行间距，**



#### 多行文本垂直居中

```html
<div class="box">
  <div class="text">
    法军口粮发生捡垃圾啊房间拉伸金坷垃时代峻峰刻录机啊咖啡假两件 法军口粮发生捡垃圾啊房间拉伸金坷垃时代峻峰刻录机啊咖啡假两件 法军口粮发生捡垃圾啊房间拉伸金坷垃时代峻峰刻录机啊咖啡假两件 法军口粮发生捡垃圾啊房间拉伸金坷垃时代峻峰刻录机啊咖啡假两件 法军口粮发生捡垃圾啊房间拉伸金坷垃时代峻峰刻录机啊咖啡假两件
  </div>
</div>
```

```css
.box {
  line-height: 250px;
  text-align: center;
}

.text {
  max-width: 900px;
  display: inline-block;
  line-height: 1.5;
  font-size: 14px;
  vertical-align: middle;
  text-align: left;
}
```

- 父容器用行高的设置的高度，子容器垂直居中并设置内部的文字的样式，子容器设置最大宽度，水平居中。 

#### 图片垂直居中

```html
<div class="box">
  <img src="./mm1.jpg" alt="">
</div>
```

```css
.box {
  line-height: 300px;
  text-align: center;
}

img {
  vertical-align: middle;
  width: 200px;
}
```

