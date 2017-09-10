## vue过渡效果

#### css类名理解

##### 元素进入

```scss
.router-fade-enter {
  transform: translate(100px);
}
.router-fade-enter-to {
  transform: translate(300px);
}
.router-fade-enter-active {
  transition: all linear 5s;
}
```

`v-enter` 表示元素进入时候的第一帧的样式，通常定义元素将要过渡时的初始化的位置或状态

`v-enter-to` 表示元素进入结束时候的样式，通常定义元素最终效果，位置或状态

`v-enter-active`表示元素整个过渡过程中的状态，通常定义元素的过渡效果

##### 元素离开

```scss
.router-fade-leave {
  transform: translate(-100px);
}
.router-fade-leave-to {
  transform: translate(-300px);
}
.router-fade-leave-active {       
  transition: all linear 5s;
}
```

`v-leave` 表示元素离开时候的第一帧的样式，通常定义元素将要过渡时的初始化的位置或状态

`v-leave-to` 表示元素离开结束时候的样式，通常定义元素最终效果，位置或状态

`v-leave-active`表示元素整个过渡过程中的状态，通常定义元素的过渡效果