## background

#### background-size

```html
<div class="box">梁嘉裕</div>
```

```css
.box {
  margin: 0 auto;
  width: 500px;
  height: 600px;
  background: yellow url('./tou.jpg') no-repeat center;
  background-size: 100% auto;
}
```

- `cover`根据背景的父容器宽度和高度拉伸图片
- `contain`根据父容器的宽度拉伸图片
- 百分比单位 根据父容器的宽度和高度定义百分比， 只设置一个值，另一个值为`auto`

#### background-position

```css
.box {
  margin: 0 auto;
  width: 500px;
  height: 600px;
  background: yellow url('./tou.jpg') no-repeat;
  background-size: 200px;
  background-position: 10%;
}
```

- 定义背景图片的位置
- 关键字`left right top bottom`等于百分比，只设置一个值时，另一个值为`center`
- 百分比的原理，父容器 减去 图片宽度，根据这个值来定义百分比

#### background-clip

```css
.box {
  margin: 0 auto;
  border: 10px solid rgba(0, 0, 0, 0.2);
  padding: 100px;
  width: 500px;
  height: 600px;
  background: pink url('./tou.jpg') no-repeat;
  color: yellow;
  font-size: 30px;
  background-size: 200px;
  background-clip: border-box;
}
```

- 背景剪裁， 定义一个容器的背景色的绘制区域，有`border-box` `padding-box` `content-box`，剪裁背景色不影响背景图片

#### background-origin

```css
.box {
  margin: 0 auto;
  border: 10px solid rgba(0, 0, 0, 0.2);
  padding: 100px;
  width: 500px;
  height: 600px;
  background: pink url('./tou.jpg') no-repeat;
  color: yellow;
  font-size: 30px;
  background-size: 200px;
  background-origin: content-box;
  background-position: 10px 10px;
}
```

- 定义背景图片的定位区域，有`border-box` `padding-box` `content-box`。

**总结**

**背景的理解，一个元素设置了背景，相对于内置一个一张定位的图片，这张图片的百分比都是相对父容器的，还可以设置这张图片的绘制区域**