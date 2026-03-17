# TabControl API 参考

## BaseTabControl（基类）

`TabControl` 和 `CardTabControl` 均继承自 `BaseTabControl`，以下属性对两者通用。

### 属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `SizeType` | 标签页尺寸 | `SizeType` | `Middle` |
| `TabStripPlacement` | 标签栏位置 | `Dock` | `Top` |
| `TabAlignmentCenter` | 标签栏是否居中对齐 | `bool` | `false` |
| `IsTabClosable` | 是否允许关闭标签页 | `bool` | `false` |
| `IsShowAddTabButton` | 是否显示添加标签按钮 | `bool` | `false` |
| `IsTabAutoHideCloseButton` | 鼠标未悬停时是否自动隐藏关闭按钮 | `bool` | `false` |
| `ItemsSource` | 标签页数据源（继承自基类） | `IEnumerable` | `null` |
| `ItemTemplate` | 标签页内容模板（继承自基类） | `IDataTemplate?` | `null` |
| `SelectedIndex` | 当前选中标签的索引（继承自基类） | `int` | `0` |
| `SelectedItem` | 当前选中的标签项（继承自基类） | `object?` | `null` |

## TabControl

线条风格的选项卡组件，继承自 `BaseTabControl`，无额外属性。

## CardTabControl

卡片风格的选项卡组件，继承自 `BaseTabControl`，无额外属性。

## TabItem

选项卡子项组件，用于定义每个标签页的标题、图标和内容。

### 属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `Header` | 标签标题文本 | `object?` | `null` |
| `Icon` | 标签图标 | `PathIcon?` | `null` |
| `IsEnabled` | 是否启用该标签（继承自基类） | `bool` | `true` |
| `IsClosable` | 是否允许关闭该标签（覆盖全局设置） | `bool` | `true` |
| `Content` | 标签页内容（继承自基类） | `object?` | `null` |

## 枚举类型

### SizeType

| 值 | 说明 |
|---|---|
| `Large` | 大尺寸 |
| `Middle` | 中等尺寸（默认） |
| `Small` | 小尺寸 |

### Dock（TabStripPlacement）

| 值 | 说明 |
|---|---|
| `Top` | 标签栏位于顶部（默认） |
| `Bottom` | 标签栏位于底部 |
| `Left` | 标签栏位于左侧 |
| `Right` | 标签栏位于右侧 |

## 事件

| 事件 | 说明 | 参数类型 |
|---|---|---|
| `SelectionChanged` | 切换标签页时触发 | `SelectionChangedEventArgs` |
| `AddTabButtonClick` | 点击添加标签按钮时触发 | `RoutedEventArgs` |
| `TabClosing` | 标签页关闭前触发 | `TabClosingEventArgs` |
