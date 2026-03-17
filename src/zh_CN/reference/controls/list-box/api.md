# ListBox API 参考

## 属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `IsItemSelectable` | 条目是否可被选中 | `bool` | `true` |
| `SizeType` | 组件的尺寸规格 | `SizeType` | — |
| `IsBorderless` | 是否启用无边框模式 | `bool` | `false` |
| `ItemHoverBg` | 条目悬停时的背景色 | `IBrush?` | `null` |
| `ItemSelectedBg` | 条目选中时的背景色 | `IBrush?` | `null` |
| `IsShowSelectedIndicator` | 是否显示选中指示器 | `bool` | `false` |
| `SelectedIndicator` | 选中指示器的图标模板 | `IconTemplate?` | `null` |
| `IsMotionEnabled` | 是否启用过渡动画 | `bool` | — |
| `EmptyIndicatorPadding` | 空状态指示器的内边距 | `Thickness` | — |
| `EmptyIndicator` | 空状态指示器的内容 | `object?` | `null` |
| `EmptyIndicatorTemplate` | 空状态指示器的数据模板 | `IDataTemplate?` | `null` |
| `IsShowEmptyIndicator` | 是否显示空状态指示器 | `bool` | `true` |
| `FilterHighlightForeground` | 过滤匹配文本的高亮前景色 | `IBrush?` | `null` |
| `ItemFilter` | 条目过滤器 | `IListBoxItemFilter?` | `null` |
| `ItemFilterValue` | 传递给过滤器的筛选值 | `object?` | `null` |
| `ItemFilterHighlightStrategy` | 过滤高亮策略 | `TextBlockHighlightStrategy` | `All` |
| `FilterResultCount` | 过滤结果数量（只读） | `int` | — |
| `IsFiltering` | 是否正在执行过滤（只读） | `bool` | — |

## 事件

| 事件 | 说明 | 参数类型 |
|---|---|---|
| `ItemClicked` | 条目被点击时触发 | `ListBoxItemClickedEventArgs` |

## 枚举类型

### SizeType

| 值 | 说明 |
|---|---|
| `Large` | 大尺寸 |
| `Middle` | 中等尺寸（默认） |
| `Small` | 小尺寸 |

### TextBlockHighlightStrategy

| 值 | 说明 |
|---|---|
| `All` | 高亮所有匹配项（默认） |

## 类继承关系

```
Avalonia.Controls.ListBox
  └── AtomUI.Controls.ListBox
```
