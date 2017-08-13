# float

### 特点

####  包围性

- 宽度和高度是根据内容而撑开的

- 隔离性，`BFC`  块状化上下文

  ```css
  /* 有包围性的属性*/
  .item {
    display: inline-block;
    display: table-cell;
    position: absolute fixed sticky;
    overflow: hidden scroll;
  }
  ```

#### 破坏性

- 父容器高度塌陷

  ```css
  /* 有破坏性的属性*/
  .item {
    position: absolute fixed sticky;
    display: none;
  }
  ```

  ​

### 清除浮动带来的影响

#### 方法一 `clear`  

- 在父容器底部添加`clear:both`

  ```css
  .clearfix::before {
    content: '';
    display: table;
  }
  .clearfix::after {
    content: '';
    display: table;
    clear: both;
  }
  ```

#### BFC

- 通过给父容器 `BFC` 可以清除浮动的影响

- 常用的两种方法也可以制造两栏布局

  ```css
  .box {
    overflow: hidden;
    display: table-cell;
    width: 2000px;
  }
  ```


### 砌砖头

- 让元素block块状化

- 破坏性造成的紧密排列特性(去空格)

  ```html
    <button type="">按钮一</button>
    <button type="">按钮一</button>
    <button type="">按钮一</button>
    <button type="">按钮一</button>
  ```

  - 标签和标签之间的回车相对一个`nbsp;` 但是多个回车也是一个`nbsp`
  - 浮动可以去除回车的`nbsp`，形成紧密布局

- 切砖头布局

  ```css
  .box01 {
    float: left;
    width: 120px;
  }

  .box02 {
    float: left;
    width: 200px;
  }

  .box03 {
    float: right;
    width: 300px;
  }

  .item01 {
    float: left;
    width: 64px;
  }
  ```

  - 容错性差，复用性差

### 浮动布局

#### 看家本领 文字环绕

#### 单侧固定 自适应布局

```css
.left {
  float: left;
  width: 100px;
  height: 100px;
  background-color: #000;
}

.right {
  margin-left: 110px;
}
```

```html
<div class="con">
  <div class="left"></div>
  <div class="right">
    <p>附近垃圾费了进口量精神分裂看拉风啦简历垃圾看了就付款啦及</p>
    <p>附近垃圾费了进口量精神分裂看拉风啦简历垃圾看了就付款啦及</p>
    <p>附近垃圾费了进口量精神分裂看拉风啦简历垃圾看了就付款啦及</p>
  </div>
</div>
```



#### DOM与显示位置匹配自适应布局

```html
<div class="con">
  <!--自适应区域  -->
  <div class="left">
    <p>附近垃圾费了进口量精神分裂看拉风啦简历垃圾看了就付款啦及</p>
    <p>附近垃圾费了进口量精神分裂看拉风啦简历垃圾看了就付款啦及</p>
    <p>附近垃圾费了进口量精神分裂看拉风啦简历垃圾看了就付款啦及</p>
  </div>
</div>
<!--固定尺寸区域  -->
<div class="right"></div>
```

```css
/* 自适应的容器*/ 	
.con {
  float: left;
  width: 100%;
}
/* 容器真实尺寸*/
.left {
  margin-right: 120px;
}
/* 固定容器 通过margin位移*/
.right {
  float: left;
  margin-left: -100px;
  width: 100px;
  height: 100px;
  background-color: #000;
}
```

- 核心通过`margin`的值让右浮动的元素位移，使DOM结构和内容结构匹配

#### 智能自适应布局

```html
<div class="con">
  <div class="left"></div>
  <div class="right">
    <p>文字文字文字文字文字文字文字文字文字文字文字文字文字</p>
    <p>文字文字文字文字文字文字文字文字文字文字文字文字文字</p>
    <p>文字文字文字文字文字文字文字文字文字文字文字文字文字</p>
  </div>
</div>
```

```css
.left {
  float: left;
  width: 100px;
  height: 100px;
  margin-right: 20px;
  background-color: #000;
}

.right {
  display: table-cell;
  width: 2000px;
  /* overflow: hidden; */
}
```

- 核心通过`bfc`  让自适应区域隔离浮动，而且隔离的距离是固定区域设置的。