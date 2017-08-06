# padding

### 与盒子模型的关系

#### block模型

```html
<div class="box">
  <p>文字文字</p>
</div>
```

```css
.box {
  display: block;
  width: 300px;
  height: 300px;
  margin: 0 auto;
  padding-top: 300px;
  padding-left: 300px;
  padding-right: 300px;
  padding-bottom: 300px;
}
```

-  谈论都为`border-box` 盒子为固定大小`padding`的值占据固定值，当大于固定值，会撑开盒子模型，其中的容器内容会根据方向变化。`padding`的值为真实的盒子模型尺寸，其中内容不占据空间。

#### inline模型

```html
<div class="box">
  <span>文字文字</span>
</div>
```

```css
.box {
  display: block;
  width: 300px;
  margin: 50px auto;
}

span {
  padding-top: 50px;
  padding-bottom: 50px;
  padding-left: 50px;
  padding-right: 50px;
  background-color: yellow;
}
```

- 结论 `inline` 垂直`padding`不会影响盒子模型尺寸，会影响背景色



### padding 百分比

- `padding` 的百分比是根据父元素的宽度计算的

```html
<div class="box">
  <!--可放背景和图片  -->
  <div class="box-img">
    <!--背景里面的内容  -->
    <div class="box-desc">
      <h3>文字</h3>
      <h4>文字文字</h4>
    </div>
  </div>
</div>
```

```css
.box-img {
  position: relative;
  padding-top: 100%;
  background-color: yellow;
  background-size: 100%;
}
/*放置图片  */
.box-img>img {
  position: absolute;
  top: 0;
  left: 0;
  max-width: 100%;
  max-height: 100%;
}
/*文字容器  */
.box-desc {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}
```

- 应用场景 图片需要控制尺寸并且要根据设备宽度变化但宽高比保存不变，也可以做一个响应式的盒子

