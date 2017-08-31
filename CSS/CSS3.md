## CSS3.0基础知识

### 渐变

基础语法

```css
background-image: linear-gradient([<180deg>] | to <right>],<color>,<color 50%>,<color 80%>,<color>);
```

第一参数为 渐变色的方向 可以使用deg或者 关键字 to`top right bottom left`

第二个参数为颜色的列表，其中的百分比表示颜色出现的位置

```css
background: linear-gradient(to bottom right, red, rgba(0,0,0,0));
```

