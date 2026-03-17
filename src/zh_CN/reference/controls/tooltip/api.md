# ToolTip API 参考

## ToolTip

提示组件，继承自 `ContentControl`，通过附加属性的方式为目标控件提供悬浮提示信息。

### 附加属性

| 属性名 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| `Tip` | `object?` | `null` | 提示内容，可以是文本字符串，也可以是任意控件 |
| `TipHostWidth` | `double` | `NaN` | 提示框的宽度，默认为 `NaN` 表示自动适应内容 |
| `IsOpen` | `bool` | `false` | 控制提示框是否处于打开状态 |
| `PresetColor` | `PresetColorType?` | `null` | 预设颜色类型，用于快速设置提示框的背景颜色 |
| `Color` | `Color?` | `null` | 自定义颜色，支持十六进制色值（如 `#f50`、`#2db7f5`） |
| `IsShowArrow` | `bool` | `true` | 是否显示箭头 |
| `IsPointAtCenter` | `bool` | `false` | 箭头是否指向目标控件的中心 |
| `Placement` | `PlacementMode` | `Top` | 提示框相对于目标控件的弹出位置 |
| `HorizontalOffset` | `double` | `0` | 提示框的水平偏移量 |
| `VerticalOffset` | `double` | `0` | 提示框的垂直偏移量 |
| `MarginToAnchor` | `double` | `4` | 提示框与锚点（目标控件）之间的间距 |
| `ShowDelay` | `int` | `400` | 鼠标悬停后延迟显示的时间，单位为毫秒 |
| `BetweenShowDelay` | `int` | `100` | 在多个提示之间快速切换时的延迟时间，单位为毫秒 |
| `ShowOnDisabled` | `bool` | `false` | 当目标控件处于禁用状态时是否仍然显示提示 |
| `ServiceEnabled` | `bool` | `true` | 是否启用 ToolTip 服务，设为 `false` 可完全禁用该控件的提示功能 |
| `CustomPopupPlacementCallback` | `CustomPopupPlacementCallback?` | `null` | 自定义弹出位置的回调函数，用于实现自定义定位逻辑 |

### 事件

| 事件名 | 事件参数类型 | 说明 |
|--------|-------------|------|
| `ToolTipOpening` | `CancelRoutedEventArgs` | 提示框即将打开时触发，可通过设置 `Cancel = true` 取消打开 |
| `ToolTipClosing` | `RoutedEventArgs` | 提示框即将关闭时触发 |

### PlacementMode 枚举

| 值 | 说明 |
|----|------|
| `Top` | 在目标控件上方居中显示（默认） |
| `Bottom` | 在目标控件下方居中显示 |
| `Left` | 在目标控件左侧居中显示 |
| `Right` | 在目标控件右侧居中显示 |
| `TopEdgeAlignedLeft` | 在目标控件上方、左对齐显示 |
| `TopEdgeAlignedRight` | 在目标控件上方、右对齐显示 |
| `BottomEdgeAlignedLeft` | 在目标控件下方、左对齐显示 |
| `BottomEdgeAlignedRight` | 在目标控件下方、右对齐显示 |
| `LeftEdgeAlignedTop` | 在目标控件左侧、顶部对齐显示 |
| `LeftEdgeAlignedBottom` | 在目标控件左侧、底部对齐显示 |
| `RightEdgeAlignedTop` | 在目标控件右侧、顶部对齐显示 |
| `RightEdgeAlignedBottom` | 在目标控件右侧、底部对齐显示 |

### PresetColorType 预设颜色

`PresetColor` 属性支持以下 13 种预设颜色：

`Blue`、`Red`、`Volcano`、`Orange`、`Gold`、`Yellow`、`Lime`、`Green`、`Cyan`、`GeekBlue`、`Purple`、`Pink`、`Magenta`
