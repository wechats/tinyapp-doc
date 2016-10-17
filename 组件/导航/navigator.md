#### navigator

页面链接。

| 属性名 | 类型 | 默认值 | 说明 |
| --- | --- | --- | --- |
| url | String |  | 应用内的跳转链接 |
| redirect | Boolean | false | 是否关闭当前页面 |
| hover-class | String | navigator-hover | 指定点击时的样式类，当`hover-class="none"`时，没有点击态效果 |

**注：**`navigator-hover`**默认为**`{background-color: rgba(0, 0, 0, 0.1); opacity: 0.7;}`**, **`<navigator/>`**的子节点背景色应为透明色**

**示例代码：**

```
/** wxss **/
/** 修改默认的navigator点击态 **/
.navigator-hover {
    color:blue;
}
/** 自定义其他点击态样式类 **/
.other-navigator-hover {
    color:red;
}
```

```
<!-- sample.wxml -->
<view class="btn-area">
  <navigator url="navigate?title=navigate" hover-class="navigator-hover">跳转到新页面</navigator>
  <navigator url="redirect?title=redirect" redirect hover-class="other-navigator-hover">在当前页打开</navigator>
</view>
```

```
<!-- navigator.wxml -->
<view style="text-align:center">{{ ' {{title}} ' }}</view>
<view> 点击左上角返回回到之前页面 </view>
```

```
<!-- redirect.wxml -->
<view style="text-align:center">{{ ' {{title}} ' }}</view>
<view> 点击左上角返回回到上级页面 </view>
```

```
// redirect.js navigator.js
Page({
  onLoad: function(options) {
    this.setData({
      title: options.title
    })
  }
})
```

