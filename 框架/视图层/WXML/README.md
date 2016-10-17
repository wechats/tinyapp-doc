# WXML

WXML（WeiXin Markup Language）是框架设计的一套标签语言，结合[基础组件](/框架/视图层/组件.md)、[事件系统](事件.md)，可以构建出页面的结构。

用以下一些简单的例子来看看 WXML 具有什么能力：

### [数据绑定](数据绑定.md)

```
<!--wxml-->
<view>{{ "{{message}}" }}</view>
```

```
// page.js
Page({
  data: {
    message: 'Hello MINA!'
  }
})
```

### [列表渲染](列表渲染.md)

```
<!--wxml-->
<view wx:for="{{ '{{array}}' }}"> {{ '{{item}}' }} </view>
```

```
// page.js
Page({
  data: {
    array: [1, 2, 3, 4, 5]
  }
})
```

### [条件渲染](条件渲染.md)

```
<!--wxml-->
<view wx:if="{{ '{{view == \'WEBVIEW\'}}' }}"> WEBVIEW </view>
<view wx:elif="{{ '{{view == \'APP\'}}' }}"> APP </view>
<view wx:else="{{ '{{view == \'MINA\'}}' }}"> MINA </view>
```

```
// page.js
Page({
  data: {
    view: 'MINA'
  }
})
```

### [模板](模板.md)

```
<!--wxml-->
<template name="staffName">
  <view>
    FirstName: {{ '{{firstName}}' }}, LastName: {{ '{{lastName}}' }}
  </view>
</template>

<template is="staffName" data="{{ '{{...staffA}}' }}"></template>
<template is="staffName" data="{{ '{{...staffB}}' }}"></template>
<template is="staffName" data="{{ '{{...staffC}}' }}"></template>
```

```
// page.js
Page({
  data: {
    staffA: {firstName: 'Hulk', lastName: 'Hu'},
    staffB: {firstName: 'Shang', lastName: 'You'},
    staffC: {firstName: 'Gideon', lastName: 'Lin'}
  }
})
```

### [事件](事件.md)

```
<view bindtap="add"> {{ '{{count}}' }} </view>
```

```
Page({
  data: {
    count: 1
  },
  add: function(e) {
    this.setData({
      count: this.data.count + 1
    })
  }
})
```

具体的能力以及使用方式在以下章节查看：

[数据绑定](数据绑定.md)、[列表渲染](列表渲染.md)、[条件渲染](条件渲染.md)、[模板](模板.md)、[事件](事件.md)、[引用](引用.md)
