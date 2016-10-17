#### text

文本。

支持转义符"\"。

除了文本节点以外的其他节点都无法长按选中。

**示例：**

```
<view class="btn-area">
  <view class="body-view">
    <text>{{ '{{text}}' }}</text>
    <button bindtap="add">add line</button>
    <button bindtap="remove">remove line</button>
  </view>
</view>
```

```
var initData = 'this is first line\nthis is second line'
var extraLine = [];
Page({
  data: {
    text: initData
  },
  add: function(e) {
    extraLine.push('other line')
    this.setData({
      text: initData + '\n' + extraLine.join('\n')
    })
  },
  remove: function(e) {
    if (extraLine.length > 0) {
      extraLine.pop()
      this.setData({
        text: initData + '\n' + extraLine.join('\n')
      })
    }
  }
})

```

![](/image/pic/text.png)

