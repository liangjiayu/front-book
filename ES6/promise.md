## [Promise](http://es6.ruanyifeng.com/#docs/promise)

### 含义

`promise`就像一个容器，里面通常存放一些异步操作，这个容器会保存这些异步操作的结果，通过统一的`api`获取可以异步操作的数据。

### 基本用法

```javascript
var getSong = function (url) {
  var promise = new Promise(function (resolve, reject) {
    // ajax
    var client = new XMLHttpRequest();
    client.open('GET', url);
    client.onreadystatechange = handler;
    client.responseType = "json";
    client.setRequestHeader("Accept", "application/json");
    client.send();

    function handler() {
      if (this.readyState !== 4) {
        return;
      }
      if (this.status === 200) {
        //ajax 成功 将容器状态定型为成功 并保存数据
        resolve(this.response);
      } else {
        //ajax 错误 将容器状态定型为失败 并抛出错误                    
        reject(new Error(this.statusText));
      }
    }
  });
  return promise;
}

getSong('http://api.jirengu.com/fm/getSong.php').then(function (result) {
  console.log(result)
}).catch(function (error) {
  console.log(error);
})
```

