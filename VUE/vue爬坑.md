## vue爬坑

#### axios的tip

[axios](https://github.com/axios/axios)

`axios`是一个基于`promise`异步请求工具

##### post

```javascript
axios.post('/user', {
    firstName: 'Fred',
    lastName: 'Flintstone'
  })
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  });
```

`axios`默认给后端的数据都是`json`，但是后端通常有`form`的格式

**可以通过`qs`工具将传递的参数转为`form`格式**

```javascript
var qs = require('qs');
axios.post('/foo', qs.stringify({ 'bar': 123 }));
```

**带cookie的请求**

```javascript
Vue.http.defaults.withCredentials = true
```

##### get

```javascript
axios.get('/user', {
    params: {
      ID: 12345
    }
  })
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  });
```

**基础使用，特殊的请求要调用自定义api**