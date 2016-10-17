## 怎么获取用户输入

能够获取用户输入的组件，需要使用组件的属性`bindchange`将用户的输入内容同步到 AppService。

```
<input id="myInput" bindchange="bindChange" />
<checkbox id="myCheckbox" bindchange="bindChange" />
```

```
var inputContent = {}

Page({
  data: {
    inputContent: {}
  },
    bindChange: function(e) {
        inputContent[e.currentTarget.id] = e.detail.value
    }
})
```

## 为什么脚本内不能使用`window`等对象

页面的脚本逻辑在是在`JsCore`中运行，`JsCore`是一个没有窗口对象的环境，所以不能在脚本中使用`window`，也无法在脚本中操作组件

## 为什么 zepto/jquery 无法使用

zepto/jquery 会使用到`window`对象和`document`对象，所以无法使用。

## `wx.navigateTo`无法打开页面

一个应用同时只能打开5个页面，当已经打开了5个页面之后，`wx.navigateTo`不能正常打开新页面。请避免多层级的交互方式，或者使用[`wx.redirectTo`](/API/界面/导航.md)

## 样式表不支持级联选择器

WXSS支持以`.`开始的类选择器。如：

```
.normal_view {
  color: #000000;
  padding: 10px;
}
```

可以使用标签选择器，控制同一类组件的样式。如：使用input标签选择器控制`<input/>`的默认样式。

```
input {
  width: 100px;
}
```

## 本地资源无法通过 css 获取

`background-image`：可以使用网络图片，或者 base64，或者使用`<image/>`标签

## 如何修改窗口的背景色

使用 page 标签选择器，可以修改顶层节点的样式

```
page {
  display: block;
  min-height: 100%;
  background-color: red;
}
```

