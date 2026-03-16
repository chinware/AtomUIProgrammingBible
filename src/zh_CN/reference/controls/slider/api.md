# Slider API

### 类定义

```
Slider : RangeBase
```

`Slider` 继承自 `RangeBase`，提供滑动输入功能，支持单值选取和范围选取。

### 属性

| 属性名 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| Orientation | `Orientation` | `Horizontal` | 滑块方向，可选 `Horizontal` 或 `Vertical` |
| IsDirectionReversed | `bool` | `false` | 是否反转滑块方向 |
| IsSnapToTickEnabled | `bool` | `false` | 是否启用刻度吸附，启用后滑块只能停在刻度点上 |
| TickFrequency | `double` | `0` | 刻度间隔，设置刻度点的间距 |
| RangeValue | `SliderRangeValue` | - | 范围模式下的取值，包含起始值和结束值 |
| IsRangeMode | `bool` | `false` | 是否启用范围模式，启用后显示双滑块 |
| Marks | `List<SliderMark>?` | `null` | 刻度标记列表，用于在轨道上显示自定义标记 |
| ValueFormatTemplate | `string` | `"{0:0}"` | 工具提示的数值格式化模板 |
| Included | `bool` | `true` | 是否高亮显示选中范围内的标记点和轨道 |
| IsMotionEnabled | `bool` | `true` | 是否启用运动动画 |
| IsWaveAnimationEnabled | `bool` | `true` | 是否启用波浪动画 |

> 继承自 `RangeBase` 的常用属性：`Minimum`、`Maximum`、`Value`、`SmallChange`、`LargeChange`。

### 结构体

#### SliderRangeValue

`record struct`，用于表示范围模式下的取值区间。

| 字段名 | 类型 | 说明 |
|--------|------|------|
| StartValue | `double` | 范围起始值 |
| EndValue | `double` | 范围结束值 |

#### SliderMark

`record`，用于定义刻度标记的显示信息。

| 字段名 | 类型 | 说明 |
|--------|------|------|
| Label | `string` | 标记文本 |
| Value | `double` | 标记对应的数值位置 |
| LabelBrush | `IBrush?` | 标记文本颜色 |
| LabelFontStyle | `FontStyle?` | 标记文本字体样式 |
| LabelFontWeight | `FontWeight?` | 标记文本字体粗细 |
