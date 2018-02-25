# sliderPro插件

## 一、相关资料

[github](https://github.com/bqworks/slider-pro)

## 二、基础使用

**引用**

```html
<link rel="stylesheet" href="./dist/css/slider-pro.css">
<script src="https://cdn.bootcss.com/jquery/3.2.1/jquery.js"></script>
<script src="./dist/js/jquery.sliderPro.js"></script>
```

**基本结构**

```html
    <div id="example1" class="slider-pro">
        <div class="sp-slides">
            <div class="sp-slide">
                <img class="sp-image" src="./dist/css/images/blank.gif" data-src="http://bqworks.com/slider-pro/images/image1_medium.jpg" />
            </div>
            <div class="sp-slide">
                <img class="sp-image" src="./dist/css/images/blank.gif" data-src="http://bqworks.com/slider-pro/images/image1_medium.jpg" />
            </div>
            <div class="sp-slide">
                <img class="sp-image" src="./dist/css/images/blank.gif" data-src="http://bqworks.com/slider-pro/images/image1_medium.jpg" />
            </div>
            <div class="sp-slide">
                <img class="sp-image" src="./dist/css/images/blank.gif" data-src="http://bqworks.com/slider-pro/images/image1_medium.jpg" />
            </div>
        </div>

        <div class="sp-thumbnails">
            <div class="sp-thumbnail">
                <img src="http://bqworks.com/slider-pro/images/image1_medium.jpg" alt="">
            </div>
            <div class="sp-thumbnail">
                <img src="http://bqworks.com/slider-pro/images/image1_medium.jpg" alt="">
            </div>
            <div class="sp-thumbnail">
                <img src="http://bqworks.com/slider-pro/images/image1_medium.jpg" alt="">
            </div>
            <div class="sp-thumbnail">
                <img src="http://bqworks.com/slider-pro/images/image1_medium.jpg" alt="">
            </div>
        </div>
    </div>
```

## 三、常用属性

```javascript
$(function() {
  // sliderPro 常用属性 以下为默认值
  $('#example1').sliderPro({
    // 基础属性
    width: 800, //宽度 
    height: 500, //高度
    // orientation: 'vertical', //垂直滑动
    startSlide: 0, //设置默认选择 滑块
    shuffle: false, //随机排序
    loop: true, //是否循环

    // fade 模块
    fade: false, //淡入淡出 

    // 自动播放 模块
    autoplay: false,
    autoplayDelay: 5000,

    // 箭头 模块
    arrows: false,

    // 分页器 模块
    buttons: true,

    // 拖拉
    touchSwipe: true,

    // 全屏模式
    fullScreen: false,

    // 小图 模块
    thumbnailWidth: 100,
    thumbnailHeight: 80,
    thumbnailsPosition: 'bottom', //设置位置
    thumbnailPointer: true, // 指示器
    thumbnailArrows: false, //箭头

    // 响应式 图片
    smallSize: 480,
    mediumSize: 767,
    largeSize: 1024,

    // 响应式
    breakpoints: {
      500: {
        thumbnailWidth: 120,
        thumbnailHeight: 50
      }
    }
  });
})
```

