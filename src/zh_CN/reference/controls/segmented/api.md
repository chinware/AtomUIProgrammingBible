# Segmented API

### 类定义

```
Segmented : SelectingItemsControl
```

### 属性

| 属性 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| SizeType | 控件尺寸，可选值为 `Large`、`Middle`、`Small` | `SizeType` | `Middle` |
| IsExpanding | 是否开启 Block 模式，开启后所有选项等分宽度并占满父容器 | `bool` | `false` |
| IsMotionEnabled | 是否启用切换过渡动画 | `bool` | `true` |

### SegmentedItem

`SegmentedItem` 为 `Segmented` 的子项组件，用于定义每个选项。

| 属性 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| Content | 选项的文字内容 | `object` | - |
| Icon | 选项的图标 | `PathIcon` | - |
| IsEnabled | 是否启用该选项 | `bool` | `true` |
