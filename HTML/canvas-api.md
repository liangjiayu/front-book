## canvas api

#### canvas 标签

```html
<canvas id="canvas" width="500" height="500"></canvas>
```

要在整个页面dom结构加载完成后才对`canvas`标签进行编程，画布的坐标系统为左上角为原点，向右向下延伸

**基础的绘画结构**

```javascript
function canvasApp() {
  var canvas = document.getElementById('canvas');
  var ctx = canvas.getContext('2d');
  function draw() {
    ctx.fillRect(0,0,100,100);
  }
  draw()
}
canvasApp()
```

#### 路径API 

`ctx.beginPath()`

新建一个新的绘制路径

`ctx.closePaht()`

关闭当前路径，并把首尾的路径闭合

`ctx.stroke()`

绘制当前路径，如果没有关闭路径会默认关闭路径

`ctx.strokeStyle`

设置画笔的样式

##### 线段

`ctx.lineWidth`

绘制的直线的宽度

`ctx.moveTo(x,y)`

路径的开始坐标

`ctx.lineTo(x,y)`

直线的第二个坐标

`ctx.setLineDash([线段,间距])`

设置绘制的直线为虚线 参数为一个数组 



##### 绘制文本

`ctx.fillText(text,x,y,[max-width])`

绘制填充文字 `x y `坐标为文字开始出现的坐标

`ctx.strokeText(text,x,y,[max-width])`

绘制描边文本

**字体样式相关**

`ctx.font` = `10px font-family` 

文本字体样式设置

`ctx.textAlign` = `left right center`

文本对齐设置

`ctx.Baseline` 

文本基线对齐设置











