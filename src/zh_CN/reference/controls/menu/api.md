# Menu API 参考

## Menu

`AtomUI.Controls.Menu` 继承自 `Avalonia.Controls.Menu`

### 属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `SizeType` | 菜单尺寸 | `SizeType` | `Middle` |
| `IsMotionEnabled` | 是否启用过渡动画 | `bool` | `true` |
| `DisplayPageSize` | 弹出菜单每页显示的最大项数，超出后可滚动 | `int` | `10` |
| `ShouldUseOverlayLayer` | 是否使用 OverlayLayer 渲染弹出层 | `bool` | `false` |

---

## MenuItem

`AtomUI.Controls.MenuItem` 继承自 `Avalonia.Controls.MenuItem`

### 属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `Icon` | 菜单项图标 | `PathIcon?` | `null` |
| `SizeType` | 菜单项尺寸 | `SizeType` | `Middle` |
| `DisplayPageSize` | 子菜单每页显示的最大项数 | `int` | `10` |
| `Header` | 菜单项显示文本（继承自基类） | `object?` | `null` |
| `InputGesture` | 快捷键（继承自基类） | `KeyGesture?` | `null` |
| `IsEnabled` | 是否启用（继承自基类） | `bool` | `true` |
| `ToggleType` | 切换类型，支持 Radio 和 CheckBox | `MenuItemToggleType` | `None` |
| `GroupName` | Radio 模式下的分组名称 | `string?` | `null` |
| `IsChecked` | 是否选中（ToggleType 不为 None 时有效） | `bool` | `false` |

### 事件

| 事件 | 说明 | 参数类型 |
|---|---|---|
| `IsCheckStateChanged` | 选中状态变化时触发 | `RoutedEventArgs` |
| `Click` | 菜单项点击时触发（继承自基类） | `RoutedEventArgs` |

---

## 枚举类型

### SizeType

| 值 | 说明 |
|---|---|
| `Large` | 大尺寸 |
| `Middle` | 中等尺寸（默认） |
| `Small` | 小尺寸 |

### MenuItemToggleType

| 值 | 说明 |
|---|---|
| `None` | 默认，不可切换 |
| `Radio` | 单选模式，同一 GroupName 下互斥 |
| `CheckBox` | 多选模式，可独立勾选 |

---

## 相关组件

- [NavMenu](./getting-started.md#垂直导航菜单) -- 导航菜单，支持水平、垂直、内嵌模式
- [ContextMenu](./getting-started.md#右键菜单contextmenu) -- 右键上下文菜单
- [MenuFlyout](./getting-started.md#右键菜单menuflyout) -- 浮出式菜单
- [DropdownButton](../dropdown-button/overview.md) -- 带下拉菜单的按钮
