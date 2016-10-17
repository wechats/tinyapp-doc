# 基础组件

框架为开发者提供了一系列基础组件，开发者可以通过组合这些基础组件进行快速开发。

什么是组件：

* 组件是视图层的基本组成单元。

* 组件自带一些功能与微信风格的样式。

* 一个组件通常包括`开始标签`和`结束标签`，`属性`用来修饰这个组件，`内容`在两个标签之内。

 ```

 <tagname property="value">

 Content goes here ...

 </tagename>

 ```

 **注意：所有组件与属性都是小写，以连字符**`-`**连接**

### 属性类型

| 类型 | 描述 | 注解 |
| --- | --- | --- |
| Boolean | 布尔值 | 组件写上该属性，不管该属性等于什么，其值都为`true`，只有组件上没有写该属性时，属性值才为`false`。如果属性值为变量，变量的值会被转换为Boolean类型 |
| Number | 数字 | `1`, `2.5` |
| String | 字符串 | `"string"` |
| Array | 数组 | `[ 1, "string" ]` |
| Object | 对象 | `{ key: value }` |
| EventHandler | 事件处理函数名 | `"handlerName"` 是 [Page](/框架/逻辑层/注册页面.md)中定义的事件处理函数名 |
| Any | 任意属性 | - |

### 共同属性类型

所有组件都有的属性：

| 属性名 | 类型 | 描述 | 注解 |
| --- | --- | --- | --- |
| id | String | 组件的唯一标示 | 保持整个页面唯一 |
| class | String | 组件的样式类 | 在对应的 WXSS 中定义的样式类 |
| style | String | 组件的内联样式 | 可以动态设置的内联样式 |
| hidden | Boolean | 组件是否显示 | 所有组件默认显示 |
| data-\* | Any | 自定义属性 | 组件上触发的事件时，会发送给事件处理函数 |
| bind\* / catch\* | EventHandler | 组件的事件 | 详见[事件](/框架/视图层/WXML/事件.md) |

### 特殊属性

几乎所有组件都有各自定义的属性，可以对该组件的功能或样式进行修饰，请参考各个[组件](/组件/README.md#组件列表)的定义。

### 组件列表

基础组件分为以下八大类：

**视图容器\(View Container\)：**

| 组件名 | 说明 |
| --- | --- |
| [view](/组件/视图容器/view.md) | 视图容器 |
| [scroll-view](/组件/视图容器/scroll-view.md) | 可滚动视图容器 |
| [swiper](/组件/视图容器/swiper.md) | 滑块视图容器 |

**基础内容\(Basic Content\)：**

| 组件名 | 说明 |
| --- | --- |
| [icon](/组件/基础内容/icon.md) | 图标 |
| [text](/组件/基础内容/text.md) | 文字 |
| [progress](/组件/基础内容/progress.md) | 进度条 |

**表单\(Form\)：**

| 标签名 | 说明 |
| --- | --- |
| [button](/组件/表单组件/button.md) | 按钮 |
| [form](/组件/表单组件/form.md) | 表单 |
| [input](/组件/表单组件/input.md) | 输入框 |
| [checkbox](/组件/表单组件/checkbox.md) | 多项选择器 |
| [radio](/组件/表单组件/radio.md) | 单项选择器 |
| [picker](/组件/表单组件/picker.md) | 列表选择器 |
| [slider](/组件/表单组件/slider.md) | 滚动选择器 |
| [switch](/组件/表单组件/switch.md) | 开关选择器 |
| [label](/组件/表单组件/label.md) | 标签 |

**操作反馈\(Interaction\)：**

| 组件名 | 说明 |
| --- | --- |
| [action-sheet](/组件/操作反馈/action-sheet.md) | 上拉菜单 |
| [modal](/组件/操作反馈/modal.md) | 模态弹窗 |
| [toast](/组件/操作反馈/toast.md) | 消息提示框 |
| [loading](/组件/操作反馈/loading.md) | 加载提示符 |

**导航\(Navigation\)：**

| 组件名 | 说明 |
| --- | --- |
| [navigator](/组件/导航/navigator.md) | 应用链接 |

**多媒体\(Media\)：**

| 组件名 | 说明 |
| --- | --- |
| [audio](/组件/媒体组件/audio.md) | 音频 |
| [image](/组件/媒体组件/image.md) | 图片 |
| [video](/组件/媒体组件/video.md) | 视频 |

**地图\(Map\)：**

| 组件名 | 说明 |
| --- | --- |
| [map](/组件/地图/map.md) | 地图 |

**画布\(Canvas\)：**

| 组件名 | 说明 |
| --- | --- |
| [canvas](/组件/画布/canvas.md) | 画布 |
