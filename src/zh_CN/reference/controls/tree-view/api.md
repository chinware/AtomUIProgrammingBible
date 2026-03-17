# TreeView API 参考

## TreeView

`TreeView` 继承自 `AvaloniaTreeView`，用于以层级结构展示和操作树形数据。

### 属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `IsAutoExpandParent` | 自动展开父节点 | `bool` | `true` |
| `IsDraggable` | 是否启用节点拖拽排序 | `bool` | `false` |
| `IsShowIcon` | 是否显示节点图标 | `bool` | `false` |
| `IsShowLine` | 是否显示节点间的连接线 | `bool` | `false` |
| `IsDefaultExpandAll` | 是否默认展开所有节点 | `bool` | `false` |
| `NodeHoverMode` | 节点悬停高亮模式 | `TreeItemHoverMode` | `Default` |
| `SwitcherExpandIcon` | 自定义切换器展开图标 | `IconTemplate?` | `null` |
| `SwitcherCollapseIcon` | 自定义切换器收起图标 | `IconTemplate?` | `null` |
| `SwitcherRotationIcon` | 自定义切换器旋转图标 | `IconTemplate?` | `null` |
| `SwitcherLoadingIcon` | 自定义切换器加载中图标 | `IconTemplate?` | `null` |
| `SwitcherLeafIcon` | 自定义切换器叶节点图标 | `IconTemplate?` | `null` |
| `IsShowLeafIcon` | 是否显示叶节点图标 | `bool` | `false` |
| `IsSwitcherRotation` | 是否启用切换器旋转动画 | `bool` | `true` |
| `IsSelectable` | 节点是否可选中 | `bool` | `true` |
| `IsCheckStrictly` | 勾选节点时是否严格遵循父子不关联模式 | `bool` | `false` |
| `IsMotionEnabled` | 是否启用展开/收起动画 | `bool` | - |
| `ToggleType` | 节点切换类型（无、复选框、单选） | `ItemToggleType` | `None` |
| `DataLoader` | 异步数据加载器，用于按需加载子节点数据 | `ITreeItemNodeLoader?` | `null` |
| `Filter` | 节点过滤器 | `ITreeItemFilter?` | `null` |
| `FilterValue` | 过滤条件的值 | `object?` | `null` |
| `FilterHighlightStrategy` | 过滤高亮策略 | `TreeFilterHighlightStrategy` | `All` |
| `FilterHighlightForeground` | 过滤匹配文本的高亮前景色 | `IBrush?` | `null` |
| `EmptyIndicator` | 空状态指示器内容 | `object?` | `null` |
| `EmptyIndicatorTemplate` | 空状态指示器模板 | `IDataTemplate?` | `null` |
| `IsShowEmptyIndicator` | 是否在无数据时显示空状态指示器 | `bool` | `true` |

## 枚举类型

### TreeItemHoverMode

节点悬停高亮模式。

| 值 | 说明 |
|---|---|
| `Default` | 默认悬停效果 |
| `Block` | 块状高亮，悬停时高亮整个节点块区域 |
| `WholeLine` | 整行高亮，悬停时高亮节点所在的整行 |

### TreeFilterHighlightStrategy

节点过滤高亮策略，支持 `[Flags]` 标记，可组合使用。

| 值 | 说明 |
|---|---|
| `HighlightedMatch` | 高亮匹配的文本部分 |
| `HighlightedWhole` | 高亮匹配节点的整个文本 |
| `BoldedMatch` | 加粗匹配的文本部分 |
| `ExpandPath` | 自动展开匹配节点的路径 |
| `HideUnMatched` | 隐藏未匹配的节点 |
| `All` | 以上所有策略的组合 |

### ItemToggleType

节点切换控件类型。

| 值 | 说明 |
|---|---|
| `None` | 不显示切换控件 |
| `CheckBox` | 显示复选框，支持多选 |
| `Radio` | 显示单选按钮，支持单选 |
