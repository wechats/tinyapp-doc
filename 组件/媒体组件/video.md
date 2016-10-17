#### video

视频。

| 属性名 | 类型 | 默认值 | 说明 |
| --- | --- | --- | --- |
| src | String |  | 要播放视频的资源地址 |
| binderror | EventHandle |  | 当发生错误时触发error事件，event.detail = {errMsg: 'something wrong'} |

video标签认宽度300px、高度225px，设置宽高需要通过wxss设置width和height。

**示例代码：**

```
<view class="section tc">
  <video src="http://wxsnsdy.tc.qq.com/105/20210/snsdyvideodownload?filekey=30280201010421301f0201690402534804102ca905ce620b1241b726bc41dcff44e00204012882540400&bizid=1023&hy=SH&fileparam=302c020101042530230204136ffd93020457e3c4ff02024ef202031e8d7f02030f42400204045a320a0201000400" binderror="videoErrorCallback"></video>
</view>

<view class="section tc">
  <video src="{{ '{{src}}' }}"></video>
  <view class="btn-area">
    <button bindtap="bindButtonTap">获取视频</button>
  </view>
</view>
```

```
Page({
    data: {
        src: ''
    },
    bindButtonTap: function() {
        var that = this
        wx.chooseVideo({
            sourceType: ['album', 'camera'],
            maxDuration: 60,
            camera: ['front','back'],
            success: function(res) {
                that.setData({
                    src: res.tempFilePath
                })
            }
        })
    },
    videoErrorCallback: function(e) {
      console.log('视频错误信息:')
      console.log(e.detail.errMsg)
    }
})
```

![](/image/pic/video.png)

