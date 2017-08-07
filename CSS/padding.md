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


### 绘图

```css
.box {
  box-sizing: content-box;
  width: 150px;
  height: 30px;
  padding: 30px 0;
  border-top: 30px solid #000;
  background-color: #000;
  background-clip: content-box;
  border-bottom: 30px solid #000;
}

.box2 {
  box-sizing: content-box;
  width: 150px;
  height: 150px;
  border-radius: 50%;
  background-color: #000;
  background-clip: content-box;
  border: 10px solid #000;
  padding: 10px;
}
```

- 主要通过`background-clip:content-box`定义背景色的范围，`border`和`content-box`来绘制颜色，而`padding`只可以绘制白色区域。





### 等高布局

```html
<div class="box">
  <div class="son-green">
    <div>文字</div>
    <div>文字</div>
  </div>
  <div class="son-orange">
    <div>文字</div>
    <div>文字</div>
    <div>文字</div>
    <div>文字</div>
    <div>文字</div>
    <div>文字</div>
    <div>文字</div>
    <div>文字</div>
    <div>文字</div>
    <div>文字</div>
  </div>
</div>
```

```css
/*核心父元素bfc 产出结界  */
.box {
  overflow: hidden;
  text-align: center;
}

/*padding-bottom 为填充颜色，再margin-bottom减去填充色  */
.son-green,
.son-orange {
  margin-bottom: -600px;
  padding-bottom: 600px;
}

.son-green {
  float: left;
  width: 50%;
  font-size: 60px;
  color: #fff;
  background-color: green;
}

.son-orange {
  float: left;
  width: 50%;
  font-size: 60px;
  color: #fff;
  background-color: orange;
}
```

- 核心`bfc` `padding-bottom `做填充和`margin-bottom`负值减去填充。 