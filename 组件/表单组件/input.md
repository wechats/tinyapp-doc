#### input

输入框。

| 属性名 | 类型 | 默认值 | 说明 |
| --- | --- | --- | --- |
| value | String |  | 输入框的内容 |
| type | String | text | input 的类型，有效值：text, number, idcard, digit, time, date |
| password | Boolean | false | 是否是密码类型 |
| placeholder | String |  | 输入框为空时占位符 |
| placeholder-style | String |  | 指定 placeholder 的样式 |
| placeholder-class | String | input-placeholder | 指定 placeholder 的样式类 |
| disabled | Boolean | false | 是否禁用 |
| maxlength | Number | 140 | 最大输入长度，设置为0的时候不限制最大长度 |
| auto-focus | Boolean | false | 自动聚焦，拉起键盘。页面中只能有一个 `<input/>` 设置 auto-focus 属性 |
| focus | Boolean | false | 获取焦点（开发工具暂不支持） |
| bindchange | EventHandle |  | 输入框失去焦点时，触发 bindchange 事件，event.detail = {value: value} |
| bindinput | EventHandle |  | 除了date/time类型外的输入框，当键盘输入时，触发input事件，event.detail = {value: value}，处理函数可以直接 return 一个字符串，将替换输入框的内容。 |
| bindfocus | EventHandle |  | 输入框聚焦时触发，event.detail = {value: value} |
| bindblur | EventHandle |  | 输入框失去焦点时触发，event.detail = {value: value} |

**示例代码：**

```
<!--input.wxml-->
<view class="section">
  <input placeholder="这是一个可以自动聚焦的input" auto-focus/>
</view>
<view class="section">
  <input placeholder="这个只有在按钮点击的时候才聚焦" focus="{{ '{{focus}}' }}" />
  <view class="btn-area">
    <button bindtap="bindButtonTap">使得输入框获取焦点</button>
  </view>
</view>
<view class="section">
  <input  maxlength="10" placeholder="最大输入长度10" />
</view>
<view class="section">
  <view class="section__title">你输入的是：{{ '{{inputValue}}' }}</view>
  <input  bindinput="bindKeyInput" placeholder="输入同步到view中"/>
</view>
<view class="section">
  <input  bindinput="bindReplaceInput" placeholder="连续的两个1会变成2" />
</view>
<view class="section">
  <input  bindinput="bindHideKeyboard" placeholder="输入123自动收起键盘" />
</view>
<view class="section">
  <input password type="number" />
</view>
<view class="section">
  <input password type="text" />
</view>
<view class="section">
  <input type="digit" placeholder="带小数点的数字键盘"/>
</view>
<view class="section">
  <input type="idcard" placeholder="身份证输入键盘" />
</view>
<view class="section">
  <input placeholder-style="color:red" placeholder="占位符字体是红色的" />
</view>
```

```
//input.js
Page({
  data: {
    focus: false,
    inputValue: ''
  },
  bindButtonTap: function() {
    this.setData({
      focus: Date.now()
    })
  },
  bindKeyInput: function(e) {
    this.setData({
      inputValue: e.detail.value
    })
  },
  bindReplaceInput: function(e) {
    var value = e.detail.value
    var pos = e.detail.cursor
    if(pos != -1){
      //光标在中间
      var left = e.detail.value.slice(0,pos)
      //计算光标的位置
      pos = left.replace(/11/g,'2').length
    }

    //直接返回对象，可以对输入进行过滤处理，同时可以控制光标的位置
    return {
      value: value.replace(/11/g,'2'),
      cursor: pos
    }

    //或者直接返回字符串,光标在最后边
    //return value.replace(/11/g,'2'),
  },
  bindHideKeyboard: function(e) {
    if (e.detail.value === '123') {
      //收起键盘
      wx.hideKeyboard()
    }
  }
})
```

![](/image/pic/input.png)

