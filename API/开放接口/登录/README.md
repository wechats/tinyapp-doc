## wx.login\(OBJECT\)

调用接口获取**登录凭证（code）**进而换取用户登录态信息，包括用户的**唯一标识（openid）** 及本次登录的 **会话密钥（session\_key）**。**用户数据的加解密通讯**需要依赖会话密钥完成。

**OBJECT参数说明：**

| 参数名 | 类型 | 必填 | 说明 |
| --- | --- | --- | --- |
| success | Function | 否 | 接口调用成功的回调函数 |
| fail | Function | 否 | 接口调用失败的回调函数 |
| complete | Function | 否 | 接口调用结束的回调函数（调用成功、失败都会执行） |

**success返回参数说明：**

| 参数名 | 类型 | 说明 |
| --- | --- | --- |
| errMsg | String | 调用结果 |
| code | String | 用户允许登录后，回调内容会带上 code（有效期五分钟），开发者需要将 code 发送到开发者服务器后台，使用`code 换取 session_key` api，将 code 换成 openid 和 session\_key |

**示例代码：**

```
//app.js
App({
  onLaunch: function() {
    wx.login({
      success: function(res) {
        if (res.code) {
          //发起网络请求
          wx.request({
            url: 'https://test.com/onLogin',
            data: {
              code: res.code
            }
          })
        } else {
          console.log('获取用户登录态失败！' + res.errMsg)
        }
      }
    });
  }
})
```

### code 换取 session\_key

​ 这是一个 HTTP 接口，开发者服务器使用**登录凭证 code **获取 session\_key 和 openid。其中 session\_key 是对用户数据进行[加密签名](签名加密.md)的密钥。为了自身应用安全，**session\_key 不应该在网络上传输**。

**接口地址：**

```
https://api.weixin.qq.com/sns/jscode2session?appid=APPID&secret=SECRET&js_code=JSCODE&grant_type=authorization_code
```

**请求参数：**

| 参数 | 必填 | 说明 |
| --- | --- | --- |
| appid | 是 | 小程序唯一标识 |
| secret | 是 | 小程序的 app secret |
| js\_code | 是 | 登录时获取的 code |
| grant\_type | 是 | 填写为 authorization\_code |

**返回参数：**

| 参数 | 说明 |
| --- | --- |
| openid | 用户唯一标识 |
| session\_key | 会话密钥 |
| expires\_in | 会话有效期, 以秒为单位, 例如2592000代表会话有效期为30天 |

**返回说明：**

```
//正常返回的JSON数据包
{
      "openid": "OPENID",
      "session_key": "SESSIONKEY"
      "expires_in": 2592000
}
//错误时返回JSON数据包(示例为Code无效)
{
    "errcode": 40029,
    "errmsg": "invalid code"
}
```

## 登录时序图

![](/image/login.png)

