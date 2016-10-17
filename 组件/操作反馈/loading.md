#### loading

加载提示。

**示例代码：**

```
<view class="body-view">
  <loading hidden="{{ '{{hidden}}' }}" bindchange="loadingChange">
    加载中...
  </loading>
  <button type="default" bindtap="loadingTap">点击弹出loading</button>
</view>
```

```
Page({
  data: {
    hidden: true
  },
  loadingChange: function () {
    this.setData({
      hidden: true
    })
  },
  loadingTap: function () {
    this.setData({
      hidden: false
    })

    var that = this
    setTimeout(function () {
      that.setData({
        hidden: true
      })
    }, 1500)
  }
})
```

![](/image/pic/loading.png)

