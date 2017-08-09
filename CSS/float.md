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

