## overflow 滚动条

### 基础知识

```css
.item {
  overflow: hidden;
  overflow-x: auto;
  overflow-y: scroll;
}
```

- 游览器的滚动条是`html`产生的

### 出现滚动条作用前提

- 有尺寸限制 `width/height/max-widht/max-height/absolute拉伸`
- `table`元素要`table-layout:fixed`状态

### 滚动条的滚动高度 js

```javascript
// chrome 和 其他游览器
  var st = document.body.scrollTop || document.documentElement.scrollTop;
  console.log(st);
```

### 自定义滚动条样式

```css
/*整体部分 */
html::-webkit-scrollbar {
  width: 8px;
  height: 8px;
}
/*滚动滑块 */
html::-webkit-scrollbar-thumb {
  background-color: rgba(0, 0, 0, .3);
  border-radius: 6px;
}
/*滚动条背景 */
html::-webkit-scrollbar-track {
  background-color: #ddd;
  border-radius: 6px;
}
```

#### ios原生滚动回调效果

```css
-webkit-overflow-scrolling: touch;
```

### BFC作用和两栏自适应布局

- bfc就像一个结界，有清除浮动的作用
- overflow的两栏自适应

```css
/*固定宽度 隔开距离  */
.left {
  float: left;
  margin-right: 20px;
}
/*自适应内容  */
.right {
  overflow: hidden;
}
```

- `table-cell`两栏自适应 优点超出宽度不会隐藏

  ```css
  /*固定宽度 隔开距离  */
  .left {
    float: left;
    margin-right: 20px;
  }
  /*自适应内容  */
  .right {
    display: table-cell;
    width: 2000px;
  }
  ```

### 隐藏失效

- 父元素`overflow:hidden` 子元素绝对定位，子元素会找上级元素是相对定位的元素，当它是`overflow:hidden`才会被隐藏

### 锚点定位

- 应用场景单页面

```html
<div class="box">
  <div id="one"></div>
  <div id="two"></div>
  <div id="three"></div>
  <div id="four"></div>
</div>
<div class="link">
  <a href="#one"></a>
  <a href="#two"></a>
  <a href="#three"></a>
  <a href="#four"></a>
</div>
```

