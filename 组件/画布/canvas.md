## canvas

画布。

| 属性名 | 类型 | 默认值 | 说明 |
| --- | --- | --- | --- |
| canvas-id | String |  | canvas 组件的唯一标识符 |
| binderror | EventHandle |  | 当发生错误时触发 error 事件，detail = {errMsg: 'something wrong'} |

**注：**

1. **canvas标签默认宽度300px、高度225px**
2. **同一页面中的 canvas-id 不可重复，如果使用一个已经出现过的 canvas-id，该 canvas 标签对应的画布将被隐藏并不再正常工作**

**示例代码：**[**下载**](/demo/api-canvas.zip)

```
<!-- canvas.wxml -->
<canvas style="width: 300px; height: 200px;" canvas-id="firstCanvas"></canvas>
<!-- 当使用绝对定位时，文档流后边的canvas的显示层级高于前边的canvas-->
<canvas style="width: 400px; height: 500px;" canvas-id="secondCanvas"></canvas>
<!-- 因为canvas-id与前一个canvas重复，该canvas不会显示，并会发送一个错误事件到AppService -->
<canvas style="width: 400px; height: 500px;" canvas-id="secondCanvas" binderror="canvasIdErrorCallback"></canvas>
```

```
// canvas.js
Page({
  canvasIdErrorCallback: function (e) {
    console.error(e.detail.errMsg)
  },
  onReady: function (e) {

    //使用wx.createContext获取绘图上下文context
    var context = wx.createContext()

    context.setStrokeStyle("#00ff00")
    context.setLineWidth(5)
    context.rect(0, 0, 200, 200)
    context.stroke()
    context.setStrokeStyle("#ff0000")
    context.setLineWidth(2)
    context.moveTo(160, 100)
    context.arc(100, 100, 60, 0, 2 * Math.PI, true)
    context.moveTo(140, 100)
    context.arc(100, 100, 40, 0, Math.PI, false)
    context.moveTo(85, 80)
    context.arc(80, 80, 5, 0, 2 * Math.PI, true)
    context.moveTo(125, 80)
    context.arc(120, 80, 5, 0, 2 * Math.PI, true)
    context.stroke()

    //调用wx.drawCanvas，通过canvasId指定在哪张画布上绘制，通过actions指定绘制行为
    wx.drawCanvas({
      canvasId: 'firstCanvas',
      actions: context.getActions() //获取绘图动作数组
    })
  }
})
```

相关api：[wx.createContext](/API/界面/绘图.md)、[wx.drawCanvas](/API/界面/绘图.md#wxdrawcanvas)

