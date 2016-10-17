#### picker

滚动选择器，现支持三种选择器，通过mode来区分，分别是普通选择器，时间选择器，日期选择器，默认是普通选择器。

**普通选择器：mode = selector**

| 属性名 | 类型 | 默认值 | 说明 |
| --- | --- | --- | --- |
| range | Array | \[\] | mode为 selector 时，range 有效 |
| value | Number | 0 | mode为 selector 时，是数字，表示选择了 range 中的第几个，从0开始。 |
| bindchange | EventHandle |  | value改变时触发change事件，event.detail = {value: value} |

**时间选择器：mode = time**

| 属性名 | 类型 | 默认值 | 说明 |
| --- | --- | --- | --- |
| value | String |  | 表示选中的时间，格式为"hh:mm" |
| start | String |  | 表示有效时间范围的开始，字符串格式为"hh:mm" |
| end | String |  | 表示有效时间范围的结束，字符串格式为"hh:mm" |
| bindchange | EventHandle |  | value改变时触发change事件，event.detail = {value: value} |

**日期选择器：mode = date**

| 属性名 | 类型 | 默认值 | 说明 |
| --- | --- | --- | --- |
| value | String | 0 | 表示选中的日期，格式为"yyyy-MM-dd" |
| start | String |  | 表示有效日期范围的开始，字符串格式为"yyyy-MM-dd" |
| end | String |  | 表示有效日期范围的结束，字符串格式为"yyyy-MM-dd" |
| fields | String | day | 有效值year,month,day，表示选择器的粒度 |
| bindchange | EventHandle |  | value改变时触发change事件，event.detail = {value: value} |

**注意：**开发工具暂时只支持mode = selector。

**示例代码：**

```
<view class="section">
  <view class="section__title">地区选择器</view>
  <picker bindchange="bindPickerChange" value="{{ '{{index}}' }}" range="{{ '{{array}}' }}">
    <view class="picker">
      当前选择：{{array[index]}}
    </view>
  </picker>
</view>
<view class="section">
  <view class="section__title">时间选择器</view>
  <picker mode="time" value="{{ '{{time}}' }}" start="09:01" end="21:01" bindchange="bindTimeChange">
    <view class="picker">
      当前选择: {{time}}
    </view>
  </picker>
</view>

<view class="section">
  <view class="section__title">日期选择器</view>
  <picker mode="date" value="{{ '{{date}}' }}" start="2015-09-01" end="2017-09-01" bindchange="bindDateChange">
    <view class="picker">
      当前选择: {{date}}
    </view>
  </picker>
</view>
```

```
Page({
  data: {
    array: ['美国', '中国', '巴西', '日本'],
    index: 0,
    date: '2016-09-01',
    time: '12:01'
  },
  bindPickerChange: function(e) {
    console.log('picker发送选择改变，携带值为', e.detail.value)
    this.setData({
      index: e.detail.value
    })
  },
  bindDateChange: function(e) {
    this.setData({
      date: e.detail.value
    })
  },
  bindTimeChange: function(e) {
    this.setData({
      time: e.detail.value
    })
  }
})
```

![](/image/pic/picker.png)

