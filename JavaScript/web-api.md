## WEB API

#### [FileReader](https://developer.mozilla.org/zh-CN/docs/Web/API/FileReader)

**定义**

让web应用异步读取计算机或手机的文件，把文件读取到内存中，并且可以读取到文件的数据

**属性**

`reader.result`

读取到的文件内容，其中的内容由操作的方法决定

**方法**

`reader.readAsDataURL(blob|file)`

读取文件，并且返回数据为base64

**事件**

`reader.onload()`

当取值数据成功就会调用

**实例 图片预览**

```javascript
var img = document.getElementById('img');
document.getElementById('file').addEventListener('change', function () {
  var file = this.files[0];
  var reader = new FileReader();
  reader.addEventListener('load', function () {
    img.setAttribute('src', reader.result);
  })
  reader.readAsDataURL(file);
})
```

