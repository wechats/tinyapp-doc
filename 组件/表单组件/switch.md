#### switch

开关选择器。

| 属性名 | 类型 | 默认值 | 说明 |
| --- | --- | --- | --- |
| checked | Boolean | false | 是否选中 |
| type | String | switch | 样式，有效值：switch, checkbox |
| bindchange | EventHandle |  | checked改变时触发change事件，event.detail={ value:checked} |

```
<view class="body-view">
    <switch checked bindchange="switch1Change"/>
    <switch bindchange="switch2Change"/>
</view>
```

```
Page({
  switch1Change: function (e){
    console.log('switch1 发生 change 事件，携带值为', e.detail.value)
  },
  switch2Change: function (e){
    console.log('switch2 发生 change 事件，携带值为', e.detail.value)
  }
})
```

![](/image/pic/switch.png)

