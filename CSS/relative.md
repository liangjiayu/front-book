## relative

###  限制作用

-  `absolute`的元素脱离文档流
- 限制绝对定位的元素的`top, left right bottom`
- 限制绝对定位元素`z-index` 所有层级高低要看相对定位的父元素的`z-indxe`的值
- 父元素 `overflow` +`relative` 可以限制绝对定位子元素

### 定位

- 相对自身
-  无侵入 元素相对定位，原本元素占据空间不变
- 当同时设置`left right top bottom` 其中`left top`优先起作用，后者忽略

#### 层叠关系

- 可以通过`relative`提高元素上下文层级
- 可以通过具体的`z-index`来上下文层级和内部的绝对定位元素

### 原则

- 尽量避免使用`relative`

  - `absolute`元素不依赖相对定位 不可以要给父元素添加`relative`属性，可以通过`margin` 来做位置的细节调整

- `relative`最小化

  ```html
  <div class="con">
    <div class="relative">
      <div class="box"></div>
    </div>
    <p>
      我方可垃圾啊家具卡昆仑决
    </p>
  </div>
  ```

  - 可以通过空的`div` 做最小化的`relative`，从而不影响整体的层级关系

  ​