#### map

地图。

| 属性名 | 类型 | 默认值 | 说明 |
| --- | --- | --- | --- |
| longitude | Number |  | 中心经度 |
| latitude | Number |  | 中心纬度 |
| scale | Number | 16 | 缩放级别 |
| markers | Array |  | 标记点 |
| covers | Array |  | 覆盖物 |

##### 标记点

标记点用于在地图上显示标记的位置，不能自定义图标和样式

| 属性 | 说明 | 类型 | 必填 | 备注 |
| --- | --- | --- | --- | --- |
| latitude | 纬度 | Number | 是 | 浮点数，范围 -90 ~ 90 |
| longitude | 经度 | Number | 是 | 浮点数，范围 -180 ~ 180 |
| name | 标注点名 | String | 是 |  |
| desc | 标注点详细描述 | String | 否 |  |

##### 覆盖物

覆盖物用于在地图上显示自定义图标，可自定义图标和样式

| 属性 | 说明 | 类型 | 必填 | 备注 |
| --- | --- | --- | --- | --- |
| latitude | 纬度 | Number | 是 | 浮点数，范围 -90 ~ 90 |
| longitude | 经度 | Number | 是 | 浮点数，范围 -180 ~ 180 |
| iconPath | 显示的图标 | String | 是 | 项目目录下的图片路径，支持相对路径写法 |
| rotate | 旋转角度 | Number | 否 | 顺时针旋转的角度，范围 0 ~ 360，默认为 0 |

地图组件的经纬度必填, 如果不填经纬度则默认值是北京的经纬度。 标记点markers只能在初始化的时候设置，不支持动态更新。

**注意：**开发工具暂时不支持map组件。

**示例：**

```
<!-- map.wxml -->
<map longitude="113.324520" latitude="23.099994" markers="{{ '{{markers}}' }}" covers="{{ '{{covers}}' }}" style="width: 375px; height: 200px;"></map>
```

```
// map.js
Page({
  data: {
    markers: [{
      latitude: 23.099994,
      longitude: 113.324520,
      name: 'T.I.T 创意园',
      desc: '我现在的位置'
    }],
    covers: [{
      latitude: 23.099794,
      longitude: 113.324520,
      iconPath: '../images/car.png',
      rotate: 10
    }, {
      latitude: 23.099298,
      longitude: 113.324129,
      iconPath: '../images/car.png',
      rotate: 90
    }]
  }
})
```

