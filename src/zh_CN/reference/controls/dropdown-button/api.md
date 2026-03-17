# DropdownButton API 参考

## 属性

> `DropdownButton` 继承自 `Button`，因此同时拥有 Button 的所有属性（如 `ButtonType`、`Shape`、`SizeType`、`Icon`、`IsDanger` 等）。以下仅列出 DropdownButton 自身新增的属性。

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `DropdownFlyout` | 下拉菜单内容 | `MenuFlyout?` | `null` |
| `TriggerType` | 菜单触发方式 | `FlyoutTriggerType` | `Click` |
| `IsShowArrow` | 是否显示下拉菜单的箭头指示 | `bool` | `false` |
| `IsPointAtCenter` | 箭头是否指向锚点中心 | `bool` | `false` |
| `Placement` | 下拉菜单弹出位置 | `PlacementMode` | `BottomEdgeAlignedLeft` |
| `PlacementAnchor` | 弹出锚点位置 | `PopupAnchor` | - |
| `PlacementGravity` | 弹出方向 | `PopupGravity` | - |
| `MarginToAnchor` | 弹出菜单与锚点之间的间距 | `double` | `0` |
| `MouseEnterDelay` | 鼠标移入后延迟显示的时间（毫秒） | `int` | `0` |
| `MouseLeaveDelay` | 鼠标移出后延迟隐藏的时间（毫秒） | `int` | `0` |
| `IsShowOpenIndicator` | 是否显示展开指示器（下拉箭头图标） | `bool` | `true` |
| `OpenIndicator` | 自定义展开指示器图标 | `PathIcon?` | `null` |

## 事件

| 事件 | 说明 | 参数类型 |
|---|---|---|
| `MenuItemClicked` | 下拉菜单项被点击时触发 | `RoutedEventArgs` |

## 枚举类型

### FlyoutTriggerType

| 值 | 说明 |
|---|---|
| `Click` | 点击按钮时触发下拉菜单 |
| `Hover` | 鼠标悬停在按钮上时触发下拉菜单 |

### PlacementMode（常用值）

| 值 | 说明 |
|---|---|
| `BottomEdgeAlignedLeft` | 下方弹出，左对齐 |
| `Bottom` | 下方弹出，居中对齐 |
| `BottomEdgeAlignedRight` | 下方弹出，右对齐 |
| `TopEdgeAlignedLeft` | 上方弹出，左对齐 |
| `Top` | 上方弹出，居中对齐 |
| `TopEdgeAlignedRight` | 上方弹出，右对齐 |

## 继承的属性

DropdownButton 继承自 Button，以下为常用的继承属性：

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `ButtonType` | 按钮类型 | `ButtonType` | `Default` |
| `Shape` | 按钮形状 | `ButtonShape` | `Default` |
| `SizeType` | 按钮尺寸 | `SizeType` | `Middle` |
| `Icon` | 按钮图标 | `PathIcon?` | `null` |
| `IsDanger` | 是否为危险按钮 | `bool` | `false` |
| `IsGhost` | 是否为幽灵按钮 | `bool` | `false` |
| `IsLoading` | 是否处于加载状态 | `bool` | `false` |

## 相关组件

- [Button](../button/overview.md) — 基础按钮组件
- [SplitButton](../split-button/overview.md) — 组合按钮，主按钮 + 下拉操作
