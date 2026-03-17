# SplitButton API 参考

> `SplitButton` 继承自 `ContentControl` 并实现了 `ICommandSource` 接口。

## 属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `Command` | 主按钮绑定的命令 | `ICommand?` | `null` |
| `CommandParameter` | 命令参数 | `object?` | `null` |
| `Flyout` | 下拉弹出内容 | `Flyout?` | `null` |
| `HotKey` | 快捷键 | `KeyGesture?` | `null` |
| `TriggerType` | 下拉菜单触发方式 | `FlyoutTriggerType` | `Click` |
| `IsShowArrow` | 是否显示弹出层箭头指示 | `bool` | `false` |
| `IsPointAtCenter` | 箭头是否指向锚点中心 | `bool` | `false` |
| `Placement` | 弹出层位置 | `PlacementMode` | - |
| `PlacementAnchor` | 弹出锚点位置 | `PopupAnchor` | - |
| `PlacementGravity` | 弹出方向 | `PopupGravity` | - |
| `GutterToFlyout` | 弹出层与按钮之间的间距 | `double` | `0` |
| `MouseEnterDelay` | 鼠标移入后延迟显示的时间（毫秒） | `int` | `0` |
| `MouseLeaveDelay` | 鼠标移出后延迟隐藏的时间（毫秒） | `int` | `0` |
| `SizeType` | 按钮尺寸 | `SizeType` | `Middle` |
| `Icon` | 主按钮图标 | `PathIcon?` | `null` |
| `OpenIndicator` | 自定义展开指示器图标 | `PathIcon?` | `null` |
| `IsDanger` | 是否为危险按钮（红色系） | `bool` | `false` |
| `IsPrimaryButtonType` | 是否为主要按钮样式 | `bool` | `false` |
| `IsMotionEnabled` | 是否启用过渡动画 | `bool` | `true` |
| `IsWaveSpiritEnabled` | 是否启用点击波纹效果 | `bool` | `true` |

## 事件

| 事件 | 说明 | 参数类型 |
|---|---|---|
| `Click` | 主按钮点击时触发 | `RoutedEventArgs` |

## 枚举类型

### FlyoutTriggerType

| 值 | 说明 |
|---|---|
| `Click` | 点击下拉按钮时触发菜单 |
| `Hover` | 鼠标悬停在下拉按钮上时触发菜单 |

### SizeType

| 值 | 说明 |
|---|---|
| `Large` | 大尺寸 |
| `Middle` | 中等尺寸（默认） |
| `Small` | 小尺寸 |

### PlacementMode（常用值）

| 值 | 说明 |
|---|---|
| `BottomEdgeAlignedLeft` | 下方弹出，左对齐 |
| `Bottom` | 下方弹出，居中对齐 |
| `BottomEdgeAlignedRight` | 下方弹出，右对齐 |
| `TopEdgeAlignedLeft` | 上方弹出，左对齐 |
| `Top` | 上方弹出，居中对齐 |
| `TopEdgeAlignedRight` | 上方弹出，右对齐 |

## 相关组件

- [Button](../button/overview.md) -- 基础按钮组件
- [DropdownButton](../dropdown-button/overview.md) -- 带下拉菜单的按钮
