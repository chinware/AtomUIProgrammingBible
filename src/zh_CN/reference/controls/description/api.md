# Descriptions API 参考

## Descriptions

`Descriptions` 继承自 `TemplatedControl`，用于创建结构化的键值对描述列表。

### 属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `Header` | 描述列表的标题内容 | `object?` | `null` |
| `HeaderTemplate` | 标题内容的数据模板 | `IDataTemplate?` | `null` |
| `IsBordered` | 是否显示边框 | `bool` | `false` |
| `IsShowColon` | 是否在标签后显示冒号 | `bool` | `true` |
| `ColumnInfo` | 列数配置，支持响应式断点设置 | `DescriptionsMediaBreakInfo` | 3 列 |
| `Layout` | 布局方向，`Horizontal` 为横向，`Vertical` 为纵向 | `Orientation` | `Horizontal` |
| `SizeType` | 描述列表的尺寸，可选 `Small`、`Middle`、`Large` | `SizeType` | `Large` |
| `Extra` | 标题右侧的额外操作区域内容 | `object?` | `null` |
| `ExtraTemplate` | 额外操作区域的数据模板 | `IDataTemplate?` | `null` |
| `Items` | 描述项集合（XAML 内容属性） | `DescriptionItems` | - |
| `ItemsSource` | 描述项的数据源，用于数据绑定场景 | `IEnumerable?` | `null` |

## ColumnInfo 响应式配置

`ColumnInfo` 属性支持通过字符串设置响应式断点列数，格式为 `"xs: 1, sm: 2, md: 3, lg: 3, xl: 4, xxl: 4"`。

| 断点 | 说明 |
|---|---|
| `xs` | 超小屏幕 |
| `sm` | 小屏幕 |
| `md` | 中等屏幕 |
| `lg` | 大屏幕 |
| `xl` | 超大屏幕 |
| `xxl` | 超超大屏幕 |

## SizeType 枚举

| 值 | 说明 |
|---|---|
| `Small` | 小尺寸 |
| `Middle` | 中等尺寸 |
| `Large` | 大尺寸（默认） |
