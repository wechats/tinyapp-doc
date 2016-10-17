# API

框架提供丰富的微信原生API，可以方便的调起微信提供的能力，如获取用户信息，本地存储，支付功能等。

**说明：**

* wx.on 开头的 API 是监听某个事件发生的API接口，接受一个 CALLBACK 函数作为参数。当该事件触发时，会调用 CALLBACK 函数。

* 如未特殊约定，其他 API 接口都接受一个OBJECT作为参数。

* OBJECT中可以指定`success`, `fail`, `complete`来接收接口调用结果。

| 参数名类型必填说明 | | | |
| --- | --- | --- | --- |
| success | Function | 否 | 接口调用成功的回调函数 |
| fail | Function | 否 | 接口调用失败的回调函数 |
| complete | Function | 否 | 接口调用结束的回调函数（调用成功、失败都会执行） |

**API列表：**
**网络 API 列表：**

| API说明 | |
| --- | --- |
| [wx.request](/API/网络/发起请求.md) | 发起网络请求 |
| [wx.uploadFile](/API/网络/上传、下载.md#wxuploadfileobject) | 上传文件 |
| [wx.downloadFile](/API/网络/上传、下载.md#wxdownloadfileobject) | 下载文件 |
| [wx.connectSocket](/API/网络/WebSocket.md#wxconnectsocketobject) | 创建 WebSocket 连接 |
| [wx.onSocketOpen](/API/网络/WebSocket.md#wxonsocketopencallback) | 监听 WebSocket 打开 |
| [wx.onSocketError](/API/网络/WebSocket.md#wxonsocketerrorcallback) | 监听 WebSocket 错误 |
| [wx.sendSocketMessage](/API/网络/WebSocket.md#wxsendsocketmessageobject) | 发送 WebSocket 消息 |
| [wx.onSocketMessage](/API/网络/WebSocket.md#wxonsocketmessagecallback) | 接受 WebSocket 消息 |
| [wx.closeSocket](/API/网络/WebSocket.md#wxclosesocket) | 关闭 WebSocket 连接 |
| [wx.onSocketClose](/API/网络/WebSocket.md#wxonsocketclosecallback) | 监听 WebSocket 关闭 |
**媒体 API 列表：**
| API说明 | |
| --- | --- |
| [wx.chooseImage](/API/媒体/图片.md#wxchooseimageobject) | 从相册选择图片，或者拍照 |
| [wx.previewImage](/API/媒体/图片.md#wxpreviewimageobject) | 预览图片 |
| [wx.startRecord](/API/媒体/录音.md#wxstartrecordobject) | 开始录音 |
| [wx.stopRecord](/API/媒体/录音.md#wxstoprecord) | 结束录音 |
| [wx.playVoice](/API/媒体/音频播放控制.md#wxplayvoice) | 播放语音 |
| [wx.pauseVoice](/API/媒体/音频播放控制.md#wxpausevoice) | 暂停播放语音 |
| [wx.stopVoice](/API/媒体/音频播放控制.md#wxstopvoice) | 结束播放语音 |
| [wx.getBackgroundAudioPlayerState](/API/媒体/音乐播放控制.md#wxgetbackgroundaudioplayerstateobject) | 获取音乐播放状态 |
| [wx.playBackgroundAudio](/API/媒体/音乐播放控制.md#wxplaybackgroundaudioobject) | 播放音乐 |
| [wx.pauseBackgroundAudio](/API/媒体/音乐播放控制.md#wxpausebackgroundaudio) | 暂停播放音乐 |
| [wx.seekBackgroundAudio](/API/媒体/音乐播放控制.md#wxstopbackgroundaudio) | 控制音乐播放进度 |
| [wx.stopBackgroundAudio](/API/媒体/音乐播放控制.md#wxstopbackgroundaudio) | 停止播放音乐 |
| [wx.onBackgroundAudioPlay](/API/媒体/音乐播放控制.md#wxonbackgroundaudioplaycallback) | 监听音乐开始播放 |
| [wx.onBackgroundAudioPause](/API/媒体/音乐播放控制.md#wxonbackgroundaudiopausecallback) | 监听音乐暂停 |
| [wx.onBackgroundAudioStop](/API/媒体/音乐播放控制.md#wxonbackgroundaudiostopcallback) | 监听音乐结束 |
| [wx.chooseVideo](/API/媒体/视频.md) | 从相册选择视频，或者拍摄 |
| [wx.saveFile](/API/媒体/文件.md) | 保存文件 |

**数据 API 列表：**

| API说明 | |
| --- | --- |
| [wx.getStorage](/API/数据.md#wxgetstorageobject) | 获取本地数据缓存 |
| [wx.setStorage](/API/数据.md#wxsetstorageobject) | 设置本地数据缓存 |
| [wx.clearStorage](/API/数据.md#wxclearstorageobject) | 清理本地数据缓存 |

**位置 API 列表：**

| API说明 | |
| --- | --- |
| [wx.getLocation](/API/位置.md#wxgetlocationobject) | 获取当前位置 |
| [wx.openLocation](/API/位置.md#wxopenlocationobject) | 打开内置地图 |

**设备 API 列表：**

| API说明 | |
| --- | --- |
| [wx.getNetworkType](/API/设备.md#wxgetnetworktypeobject) | 获取网络类型 |
| [wx.getSystemInfo](/API/设备.md#wxgetsysteminfoobject) | 获取系统信息 |
| [wx.onAccelerometerChange](/API/设备.md#wxonaccelerometerchangecallback) | 监听重力感应数据 |
| [wx.onCompassChange](/API/设备.md#wxoncompasschangecallback) | 监听罗盘数据 |

**界面 API 列表：**

| API说明 | |
| --- | --- |
| [wx.setNavigationBarTitle](/API/界面/设置导航条.md#wxsetnavigationbartitleobject) | 设置当前页面标题 |
| [wx.showNavigationBarLoading](/API/界面/设置导航条.md#wxshownavigationbarloading) | 显示导航条加载动画 |
| [wx.hideNavigationBarLoading](/API/界面/设置导航条.md#wxhidenavigationbarloading) | 隐藏导航条加载动画 |
| [wx.navigateTo](/API/界面/导航.md#wxnavigatetoobject) | 新窗口打开页面 |
| [wx.redirectTo](/API/界面/导航.md#wxredirecttoobject) | 原窗口打开页面 |
| [wx.navigateBack](/API/界面/导航.md#wxnavigateback) | 退回上一个页面 |
| [wx.createAnimation](/API/界面/动画.md) | 动画 |
| [wx.createContext](/API/界面/绘图.md#wxcreatecontext) | 创建绘图上下文 |
| [wx.drawCanvas](/API/界面/绘图.md#wxdrawcanvasobject) | 绘图 |
| [wx.hideKeyboard](/API/界面/其他.md#wxhidekeyboard) | 隐藏键盘 |
| [wx.stopPullDownRefresh](/API/界面/其他.md#wxstoppulldownrefresh) | 停止下拉刷新动画 |

**开放接口：**

| API说明 | |
| --- | --- |
| [wx.login](/API/开放接口/登录/README.md) | 登录 |
| [wx.getUserInfo](/API/开放接口/用户信息.md#wxgetuserinfoobject) | 获取用户信息 |
| [wx.requestPayment](/API/开放接口/微信支付.md#wxrequestpaymentobject) | 发起微信支付 |
