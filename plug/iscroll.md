# iscroll



## 一、相关资料

[GITHUB](https://github.com/cubiq/iscroll)

[中文API](https://iiunknown.gitbooks.io/iscroll-5-api-cn/index.html)

**这是一个轻量级的插件，主要用于内部滚动，如移动端的下拉导航。**



## 二、基本使用

**最基础的DOM结构**

```html
<div id="wrapper">
  <ul>
    <li>...</li>
    <li>...</li>
    <li>...</li>
    <li>...</li>
    <li>...</li>
  </ul>
</div>
```

**通常使用样式提供容器的宽度和高度**

```css
#wrapper {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  bottom: 0;
  overflow: hidden;
}
```

**初始化**

```javascript
$(function() {
  var myScroll = new IScroll('#wrapper', {});
})
```


**只有当容器下的 `ul` 元素高度或宽度超过容器，才会回有内部滚动的效果**



## 常用API

```javascript
// 下面为为默认值

var myScroll = new IScroll('#wrapper', {
    // 基础功能
    click:false, //是否监听点击事件
    mouseWheel:false, //是否监听鼠标滚动事件
    scrollbars:false, //是否显示滚动条
    scrollX: false, // 是否使用X轴
    scrollY: true, //是否使用Y轴
    tap:false, //是否抛出一个tap事件
    freeScroll:false, //是否自由滚动


    // 滚动条
    scrollbars: false, //是否显示滚动条
    fadeScrollbars:false, //滚动条 淡入淡出
    interactiveScrollbars:false, //拖拉滚动条
    
    // 自定义滚动条
    scrollbars: 'custom', 
    .iScrollHorizontalScrollbar,// 横向滚动条容器
    .iScrollVerticalScrollbar, // 纵向滚动条容器
    .iScrollIndicator, //滚动条指示器

    // zoom 相关属性
    zoom: true,
	mouseWheel: true,
	wheelAction: 'zoom',
	zoomMax: 4,
	zoomMin: 1,
	zoomStart: 1,
});


// 方法

// 更新数据
setTimeout(function () {
    myScroll.refresh();
}, 0);

// 销毁
myScroll.destroy();

// 滚动方法
scrollTo(x, y, time, easing) // x为左上角 

scrollBy(x, y, time, easing) //相对现在位置偏移
```



