# margin

#### 控制容器的尺寸

- `margin`可以控制一个没有设置宽度的盒子的水平尺寸，通过`margin-left`和`margin-right`
- `margin`可以控制盒子的垂直占据尺寸，通过`margin-bottom`和`margin-top`

#### 百分比

- 子元素的`margin`的百分比都是相对于父容器的宽度计算的
- 绝对定位的元素的`margin`百分比是根据祖先元素的定位元素的宽度计算的

#### margin重叠

相邻的兄弟元素重叠

```html
<p>的解放垃圾离开</p>
<p>的解放垃圾离开</p>
```

父元素和第一元素或最后一个元素

- 父元素和子元素公用同一个`margin`

```html
<div class="box">
  <div style="margin: 10px">打开了</div>
</div>
```

#### 清除重叠的方法

- 通过`BFC`
- 用`padding border`等属性让它们之间有间隙

**任何地方插入一个裸的div对原来的布局没有影响， 直接使用margin-top，margin-bottom可以做出更加健壮的布局**

### margin的auto

块状元素没有设置width时候，回自动填充宽度，当设置宽度后，剩余的空间由`margin`控制

```css
.box {
  width: 500px;
  height: 200px;
  margin: 0 auto;
  background-color: gray;
}
```

表示剩余的空间由`margin-left margin-right`左右平分

垂直居中

```html
<div class="con">
  <div class="box"></div>
</div>
```

```css
.con {
  position: relative;
  height: 300px;
}

.box {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  width: 100px;
  height: 100px;
  margin: auto;
  background-color: gray;
}
```

子元素通过绝对定位拉伸，填充这个空间，然后用宽度和高度限制了尺寸，所有`margin:auto`可以自动填充剩余的空间

#### magin负值

两端对齐

```css
.con {
  margin-left: -10px;
  margin-right: -10px;
}
```

通过负值撑开父容器的宽度

#### margin失效

- inline 元素 垂直margin失效

- `margin`重叠

- `table-cell`失效

- 鞭长莫及失效

- 内联特效导致无效

  内联元素是基线对齐