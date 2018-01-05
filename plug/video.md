## video.js

### 一、相关资料

[video.js](https://github.com/videojs/video.js)

[官网](http://videojs.com/)

### 二、基本使用

[bootCDN](http://www.bootcdn.cn/)

**第一步引用文件**

```html
<link href="https://cdn.bootcss.com/video.js/6.6.0/video-js.min.css" rel="stylesheet">
<script src="https://cdn.bootcss.com/video.js/6.6.0/video.min.js"></script>
```

**快速初始化**

```html
<video id="my-player" class="video-js" controls preload="auto" data-setup='{}' poster="http://vjs.zencdn.net/v/oceans.png">
  	<source src="http://vjs.zencdn.net/v/oceans.mp4" type="video/mp4"></source>
	<source src="http://vjs.zencdn.net/v/oceans.webm" type="video/webm"></source>
  	<source src="http://vjs.zencdn.net/v/oceans.ogv" type="video/ogg"></source>
</video>
```

通过`data-setup`这个属性可以快速初始化一个视频插件。

**通过函数初始化**

```javascript
var options = {};
var player = videojs('my-player', options, function onPlayerReady() {
  // 初始化成功后 并 this 指向player
  this.play();
  // 可以给 视频插件 绑定事件
  this.on('ended', function() {
    videojs.log('Awww...over so soon?!');
  });
});
```

`videojs`函数有三个参数，`id`、`选项`、`初始化回调函数` 

### 三、基础API

**方法**

```javascript
player.play(); //播放
player.pause(); //暂停
player.dispose(); //销毁
player.on('click', fn); //监听事件
```

**选项**

```javascript
autoplay :  true/false; //默认false 自动播放
controls : true/false; //显示控件 默认true
loop : true/false; //循环播放
muted : true/false; //是否静音
poster:url; //显示图片地址
preload:'auto'; //预加载

```



