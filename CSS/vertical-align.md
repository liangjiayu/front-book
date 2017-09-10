## vertical-align

#### 定义

定义内联元素的垂直表现

板块元素的高度是由多个匿名盒子或是内联盒子叠加生成的

#### 父元素的基线

父元素根据最高内联盒子来的定义 自身的幽灵节点X，最高的内联盒子的`vertical-align`的值定位幽灵节点的位置

#### 行为表现

所有的子元素都是根据父元素的幽灵节点来定位自身的位置

#### 起作用前提

内联元素 和表格元素

`middle` 元素垂直中心点和父级基线上1/2 x-height对齐	

### 实际运行

#### 小图标定位

```css
i {
  vertical-align: -10px;
}
```

#### 多行文字或图片居中

```css
.demo {
  height: 200px;
  background: red;
}

.demo span {
  display: inline-block;
  vertical-align: middle;
}

.demo i {
  display: inline-block;
  height: 100%;
  vertical-align: middle;
}
```

```html
<div class="demo">
  <span>捡垃圾发了疯房价案例集链接发<br>asdjajdlj</span>
  <i></i>
</div>
```

`i` 是一个辅助元素 用来定位父级的基线位置

`span`用`middle`垂直居中