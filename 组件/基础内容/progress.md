#### progress

进度条。

| 属性名 | 类型 | 默认值 | 说明 |
| --- | --- | --- | --- |
| percent | Float | 无 | 百分比0~100 |
| show-info | Boolean | false | 在进度条右侧显示百分比 |
| stroke-width | Number | 6 | 进度条线的宽度，单位px |
| color | Color | \#09BB07 | 进度条颜色 |
| active | Boolean | false | 进度条从左往右的动画 |

**示例：**

```
<progress percent="20" show-info />
<progress percent="40" stroke-width="12" />
<progress percent="60" color="pink" />
<progress percent="80" active />
```

![](/image/pic/progress.png)

