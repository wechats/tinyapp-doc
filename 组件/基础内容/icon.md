#### icon

图标。

| 属性名 | 类型 | 默认值 | 说明 |
| --- | --- | --- | --- |
| type | String |  | icon的类型，有效值：success, success\_no\_circle, info, warn, waiting, cancel, download, search, clear |
| size | Number | 23 | icon的大小，单位px |
| color | Color |  | icon的颜色，同css的color |

**示例：**

```
<view class="group">
  <block wx:for="{{ '{{iconSize}}' }}">
    <icon type="success" size="{{ '{{item}}' }}"/>
  </block>
</view>

<view class="group">
  <block wx:for="{{ '{{iconType}}' }}">
    <icon type="{{ '{{item}}' }}" size="45"/>
  </block>
</view>


<view class="group">
  <block wx:for="{{ '{{iconColor}}' }}">
    <icon type="success" size="45" color="{{ '{{item}}' }}"/>
  </block>
</view>
```

```
Page({
  data: {
    iconSize: [20, 30, 40, 50, 60, 70],
    iconColor: [
      'red', 'orange', 'yellow', 'green', 'rgb(0,255,255)', 'blue', 'purple'
    ],
    iconType: [
      'success', 'info', 'warn', 'waiting', 'safe_success', 'safe_warn',
      'success_circle', 'success_no_circle', 'waiting_circle', 'circle', 'download',
      'info_circle', 'cancel', 'search', 'clear'
    ]
  }
})
```

![](/image/pic/icon.png)

