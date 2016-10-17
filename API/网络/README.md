每个微信小程序需要事先设置一个通讯域名，小程序可以跟指定的域名与进行网络通信。包括普通 HTTPS 请求（wx.request）、 WebSocket 通信（wx.connectSocket）、上传文件（wx.uploadFile）和下载文件（wx.downloadFile\)。

**网络API列表：**

| API说明 | |
| --- | --- |
| [wx.request](/API/网络/发起请求.md) | 发起网络请求 |
| [wx.uploadFile](/API/网络/上传、下载.md#wxuploadfileobject) | 上传文件 |
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