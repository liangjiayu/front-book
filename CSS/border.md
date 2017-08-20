## border

#### double

绘制三条杆

```css
.box {
  box-sizing: content-box;
  width: 120px;
  border-top: 20px solid red;
  height: 20px;
  border-bottom: 60px double red;
}
```

#### 与background定位

```css
.box {
  border-right: 50px solid transparent;
  height: 300px;
  background: url('./tou.jpg') no-repeat;
  background-size: 80px auto;
  background-position: 100% 40px;
}
```

通过`border-right`来的定位背景的位置

#### 三角形

```css
.box {
  display: inline-block;
  border-color: transparent;
  border-style: solid;
  /* 三角形大小和方向*/
  border-width: 100px;
  border-top-color: red;
}
```

