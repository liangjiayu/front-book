## [async](http://es6.ruanyifeng.com/#docs/async)

### 含义

`async`函数可以看做一个多个异步操作，包装成的一个`promise`的对象。`async`函数返回一个`promise`对象，遇到`await` 先完成异步操作完成后，再接着运行下一步的语句。

### 基础用法

```javascript
function before() {
  return new Promise((resolve, reject) => {
    var tip = '开始唱歌';
    setTimeout(() => {
      resolve(tip);
    }, 1000);
  })
}

function after() {
  return new Promise((resolve, reject) => {
    var tip = '唱歌结束';
    setTimeout(() => {
      resolve(tip);
    }, 100);
  })
}

// 通过async 关键字 声明多步异步操作函数
async function foo() {
  // 运行第一个异步任务
  var a = await before().then(function (result) {
    console.log(result);
  })
  console.log('唱歌中');
  // 运行第二个异步任务
  var b = await after().then(function (result) {
    console.log(result)
  })
  }
foo()
```

