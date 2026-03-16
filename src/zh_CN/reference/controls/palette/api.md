# Palette API 参考

## ColorPicker 属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `Format` | 颜色格式 | `ColorFormat` | `Hex` |
| `TriggerType` | 弹出面板触发方式 | `FlyoutTriggerType` | `Click` |
| `IsShowArrow` | 是否显示弹出面板箭头 | `bool` | `false` |
| `IsPointAtCenter` | 箭头是否指向触发器中心 | `bool` | `false` |
| `Placement` | 弹出面板的方向 | `PlacementMode` | `Bottom` |
| `IsAlphaEnabled` | 是否启用 Alpha 透明度通道 | `bool` | `false` |
| `IsFormatEnabled` | 是否允许用户切换颜色格式 | `bool` | `false` |
| `IsShowText` | 是否在触发器上显示颜色值文本 | `bool` | `false` |
| `IsClearEnabled` | 是否允许清除已选颜色 | `bool` | `false` |
| `SizeType` | 组件尺寸 | `SizeType` | `Middle` |
| `IsMotionEnabled` | 是否启用过渡动画 | `bool` | `true` |
| `EmptyColorText` | 未选择颜色时的提示文本 | `string` | — |
| `IsPaletteGroupEnabled` | 是否启用预设色板 | `bool` | `false` |
| `PaletteGroup` | 预设色板分组 | `List<ColorPickerPalette>?` | `null` |
| `StyleVariant` | 样式变体 | `InputControlStyleVariant` | — |
| `Status` | 控件状态 | `InputControlStatus` | — |

## 事件

| 事件 | 说明 | 参数类型 |
|---|---|---|
| `ValueChanged` | 颜色值发生变化时触发（包括拖动过程中） | `EventArgs` |
| `ValueSelected` | 用户最终确认选择颜色时触发 | `EventArgs` |

## 枚举类型

### ColorFormat

| 值 | 说明 |
|---|---|
| `Hex` | 十六进制格式，如 `#1890FF` |
| `Rgb` | RGB 格式，如 `rgb(24, 144, 255)` |
| `Hsb` | HSB 格式（色相、饱和度、亮度） |

### SizeType

| 值 | 说明 |
|---|---|
| `Large` | 大尺寸 |
| `Middle` | 中等尺寸（默认） |
| `Small` | 小尺寸 |

### FlyoutTriggerType

| 值 | 说明 |
|---|---|
| `Click` | 点击触发弹出面板 |
| `Hover` | 悬停触发弹出面板 |

## 继承关系

```
Control → AbstractColorPicker → ColorPicker
```

## 相关组件

- [Button](../button/overview.md) — 按钮组件
- [LineEdit](../line-edit/overview.md) — 输入框组件
