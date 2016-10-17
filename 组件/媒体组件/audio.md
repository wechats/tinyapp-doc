#### audio

音频。

| 属性名 | 类型 | 默认值 | 说明 |
| --- | --- | --- | --- |
| action | Object |  | 控制音频的播放、暂停，播放速率、播放进度的对象，有 method 和 data 两个参数 |
| src | String |  | 要播放音频的资源地址 |
| loop | Boolean | false | 是否循环播放 |
| controls | Boolean | true | 是否显示默认控件 |
| poster | String |  | 默认控件上的音频封面的图片资源地址，如果 controls 属性值为 false 则设置 poster 无效 |
| name | String | 未知音频 | 默认控件上的音频名字，如果 controls 属性值为 false 则设置 name 无效 |
| author | String | 未知作者 | 默认控件上的作者名字，如果 controls 属性值为 false 则设置 author 无效 |
| binderror | EventHandle |  | 当发生错误时触发 error 事件，detail = {errMsg: MediaError.code} |
| bindplay | EventHandle |  | 当开始/继续播放时触发play事件 |
| bindpause | EventHandle |  | 当暂停播放时触发 pause 事件 |
| bindratechange | EventHandle |  | 当播放速率改变时触发 ratechange 事件 |
| bindtimeupdate | EventHandle |  | 当播放进度改变时触发 timeupdate 事件，detail = {currentTime, duration} |
| bindended | EventHandle |  | 当播放到末尾时触发 ended 事件 |

**MediaError.code**

| 返回错误码 | 描述 |
| --- | --- |
| MEDIA\_ERR\_ABORTED | 获取资源被用户禁止 |
| MEDIA\_ERR\_NETWORD | 网络错误 |
| MEDIA\_ERR\_DECODE | 解码错误 |
| MEDIA\_ERR\_SRC\_NOT\_SUPPOERTED | 不合适资源 |

**Action**

| method | 描述 | data |
| --- | --- | --- |
| play | 播放 |  |
| pause | 暂停 |  |
| setPlaybackRate | 调整速度 | 倍速 |
| setCurrentTime | 设置当前时间 | 播放时间 |

**示例代码：**

action的method属性只能是`play`、`pause`、`setPlaybackRate`、`setCurrentTime`，用法如下：

```
<!-- 循环播放 -->
<audio poster="{{ '{{poster}}' }}" name="{{ '{{name}}' }}" author="{{ '{{author}}' }}" src="{{ '{{src}}' }}" action="{{ '{{action}}' }}" controls loop></audio>

<button type="primary" bindtap="audioPlay">播放</button>
<button type="primary" bindtap="audioPause">暂停</button>
<button type="primary" bindtap="audioPlaybackRateSpeedUp">调为2倍速</button>
<button type="primary" bindtap="audioPlaybackRateNormal">调为1倍速</button>
<button type="primary" bindtap="audioPlaybackRateSlowDown">调为0.5倍速</button>
<button type="primary" bindtap="audio14">设置当前播放时间为14秒</button>
<button type="primary" bindtap="audioStart">回到开头</button>
```

```
// app-service
Page({
  data: {
    poster: 'http://y.gtimg.cn/music/photo_new/T002R300x300M000003rsKF44GyaSk.jpg?max_age=2592000',
    name: '此时此刻',
    author: '许巍',
    src: 'http://ws.stream.qqmusic.qq.com/M500001VfvsJ21xFqb.mp3?guid=ffffffff82def4af4b12b3cd9337d5e7&uin=346897220&vkey=6292F51E1E384E06DCBDC9AB7C49FD713D632D313AC4858BACB8DDD29067D3C601481D36E62053BF8DFEAF74C0A5CCFADD6471160CAF3E6A&fromtag=46',
  },
  audioPlay: function () {
    this.setData({
      action: {
        method: 'play'
      }
    })
  },
  audioPause: function () {
    this.setData({
      action: {
        method: 'pause'
      }
    })
  },
  audioPlaybackRateSpeedUp: function () {
    this.setData({
      action: {
        method: 'setPlaybackRate',
        data: 2
      }
    })
  },
  audioPlaybackRateNormal: function () {
    this.setData({
      action: {
        method: 'setPlaybackRate',
        data: 1
      }
    })
  },
  audioPlaybackRateSlowDown: function () {
    this.setData({
      action: {
        method: 'setPlaybackRate',
        data: 0.5
      }
    })
  },
  audio14: function () {
    this.setData({
      action: {
        method: 'setCurrentTime',
        data: 14
      }
    })
  },
  audioStart: function () {
    this.setData({
      action: {
        method: 'setCurrentTime',
        data: 0
      }
    })
  }
})
```

![](/image/pic/audio.png)

