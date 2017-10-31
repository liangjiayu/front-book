#### VUE打包路径

```
└─static
    ├─css
    ├─fonts
    ├─img
    └─js
index.html
```

通常我们会把静态的背景的路径写在样式中，而`vue`打包后的样式中的路径都会转为绝对路径，通常都会出现路径不对的问题，样式中的路径是相对于样式文件本身，所以通常采用相对路径。

#### 解决方案

更改`build/utils.js`

```javascript
if (options.extract) {
  return ExtractTextPlugin.extract({
    use: loaders,
    publicPath: '../../',         // 注意配置这一部分，根据目录结构自由调整
    fallback: 'vue-style-loader'
  })
} else {
  return ['vue-style-loader'].concat(loaders)
}
```

**这样打包出来的样式路径都会加上`publiPath`，../../的让引用的路径回到根目录，从而解决路径上面的问题**