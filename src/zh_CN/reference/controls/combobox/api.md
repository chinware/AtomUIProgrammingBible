# ComboBox API 参考

## 属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `LeftAddOn` | 输入框外部左侧的附加内容 | `object?` | `null` |
| `LeftAddOnTemplate` | LeftAddOn 的数据模板 | `IDataTemplate?` | `null` |
| `RightAddOn` | 输入框外部右侧的附加内容 | `object?` | `null` |
| `RightAddOnTemplate` | RightAddOn 的数据模板 | `IDataTemplate?` | `null` |
| `ContentLeftAddOn` | 输入框内部左侧的前缀内容 | `object?` | `null` |
| `ContentLeftAddOnTemplate` | ContentLeftAddOn 的数据模板 | `IDataTemplate?` | `null` |
| `ContentRightAddOn` | 输入框内部右侧的后缀内容 | `object?` | `null` |
| `ContentRightAddOnTemplate` | ContentRightAddOn 的数据模板 | `IDataTemplate?` | `null` |
| `SizeType` | 组件的尺寸规格 | `SizeType` | `Middle` |
| `StyleVariant` | 组件的样式变体 | `InputControlStyleVariant` | `Outline` |
| `Status` | 组件的状态色 | `InputControlStatus` | `Default` |
| `IsAllowClear` | 是否显示清除按钮 | `bool` | `false` |
| `OptionFontSize` | 下拉选项的字体大小 | `double` | — |
| `IsMotionEnabled` | 是否启用过渡动画 | `bool` | `true` |
| `DropDownDisplayPageSize` | 下拉面板每页显示的选项数量 | `int` | `10` |

## 枚举类型

### SizeType

| 值 | 说明 |
|---|---|
| `Large` | 大尺寸 |
| `Middle` | 中等尺寸（默认） |
| `Small` | 小尺寸 |

### InputControlStyleVariant

| 值 | 说明 |
|---|---|
| `Outline` | 线框样式（默认） |
| `Filled` | 填充样式 |
| `Borderless` | 无边框样式 |

### InputControlStatus

| 值 | 说明 |
|---|---|
| `Default` | 默认状态（默认） |
| `Error` | 错误状态，显示红色边框 |
| `Warning` | 警告状态，显示橙色边框 |

## 类继承关系

```
Avalonia.Controls.ComboBox
  └── AtomUI.Controls.ComboBox
```
