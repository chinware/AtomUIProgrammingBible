# ToggleSwitch API 参考

## ToggleSwitch

开关切换组件，继承自 `ToggleButton`，用于在两种状态之间进行切换。

### 属性

| 属性名 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| `GrooveBackground` | `IBrush?` | `null` | 自定义开关轨道的背景色 |
| `OnContent` | `object?` | `null` | 开启状态下显示的内容，支持文本或图标 |
| `OnContentTemplate` | `IDataTemplate?` | `null` | 开启状态内容的数据模板 |
| `OffContent` | `object?` | `null` | 关闭状态下显示的内容，支持文本或图标 |
| `OffContentTemplate` | `IDataTemplate?` | `null` | 关闭状态内容的数据模板 |
| `SizeType` | `SizeType` | `Middle` | 组件尺寸大小 |
| `IsLoading` | `bool` | `false` | 是否处于加载状态，加载中时开关不可操作 |
| `IsMotionEnabled` | `bool` | - | 是否启用动画效果 |
| `IsWaveSpiritEnabled` | `bool` | - | 是否启用波纹效果 |
| `KnobSize` | `Size` | - | 自定义滑块（旋钮）的大小 |

> 继承自 `ToggleButton` 的常用属性如 `IsChecked`、`IsEnabled`、`Command` 等同样适用，此处不再重复列出。

### SizeType 枚举

| 值 | 说明 |
|----|------|
| `Large` | 大尺寸 |
| `Middle` | 中等尺寸（默认） |
| `Small` | 小尺寸 |
