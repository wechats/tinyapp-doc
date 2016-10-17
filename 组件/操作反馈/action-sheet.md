#### action-sheet

从屏幕底部出现的菜单表。

| 属性名 | 类型 | 默认值 | 说明 |
| --- | --- | --- | --- |
| bindchange | EventHandle |  | 点击背景或 action-sheet-cancel 按钮时触发 change 事件，不携带数据 |

#### action-sheet-item

底部菜单表的子选项。

#### action-sheet-cancel

底部菜单表的取消按钮，和`<action-sheet-item/>`的区别是，点击它会触发`<action-sheet/>`的`change`事件，并且外观上会同它上面的内容间隔开来。

**示例代码：**

```
<button type="default" bindtap="actionSheetTap">弹出action sheet</button>
<action-sheet hidden="{{ '{{actionSheetHidden}}' }}" bindchange="actionSheetChange">
  <block wx:for="{{ '{{actionSheetItems}}' }}">
    <action-sheet-item class="item" bindtap="bindItemTap" data-name="{{ '{{item}}' }}">{{item}}</action-sheet-item>
  </block>
  <action-sheet-cancel class="cancel">取消</action-sheet-cancel>
</action-sheet>
```

```
Page({
  data:{
    actionSheetHidden: true,
    actionSheetItems: ['item1', 'item2', 'item3', 'item4']
  },
  actionSheetTap: function(e) {
    this.setData({
      actionSheetHidden: !this.data.actionSheetHidden
    })
  },
  actionSheetChange: function(e) {
    this.setData({
      actionSheetHidden: !this.data.actionSheetHidden
    })
  },
  bindItemTap:function(e){
    console.log('tap ' + e.currentTarget.dataset.name)
  }
})
```

![](/image/pic/action-sheet.png)

