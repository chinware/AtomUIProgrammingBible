# Separator API 参考

## Separator

`Separator` 继承自 `Avalonia.Controls.Separator`，用于在内容之间添加分隔线。

### 属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `Title` | 分隔线中显示的文字内容 | `string?` | `null` |
| `TitlePosition` | 文字在分隔线中的位置 | `SeparatorTitlePosition` | `Center` |
| `TitleColor` | 文字颜色 | `IBrush?` | `null` |
| `LineColor` | 线条颜色 | `IBrush?` | `null` |
| `Orientation` | 分隔线的方向 | `Orientation` | - |
| `OrientationMargin` | 文字与分隔线边缘的距离 | `double` | `NaN` |
| `Variant` | 线条变体样式 | `SeparatorVariant` | `Solid` |
| `LineWidth` | 线条宽度 | `double` | `1` |
| `IsPlain` | 是否使用纯文本样式（无额外字体装饰） | `bool` | `false` |
| `SizeType` | 分隔线间距大小，可选 `Small`、`Middle`、`Large` | `SizeType` | - |

## 枚举类型

### SeparatorTitlePosition

| 值 | 说明 |
|---|---|
| `Left` | 文字位于分隔线左侧 |
| `Right` | 文字位于分隔线右侧 |
| `Center` | 文字位于分隔线中间 |

### SeparatorVariant

| 值 | 说明 |
|---|---|
| `Solid` | 实线样式 |
| `Dotted` | 点线样式 |
| `Dashed` | 虚线样式 |
