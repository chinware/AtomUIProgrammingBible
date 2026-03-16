# LineEdit API 参考

## 类定义

```
LineEdit : TextBox
```

`LineEdit` 继承自 Avalonia 的 `TextBox`，在其基础上扩展了样式变体、状态反馈、前后缀和附加内容等能力。

## 属性

### LineEdit 扩展属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `StyleVariant` | 样式变体 | `InputControlStyleVariant` | `Outline` |
| `Status` | 校验状态 | `InputControlStatus` | `Default` |
| `SizeType` | 尺寸大小 | `SizeType` | `Middle` |
| `LeftAddOn` | 输入框左侧外部附加内容 | `object?` | `null` |
| `LeftAddOnTemplate` | 左侧附加内容的数据模板 | `IDataTemplate?` | `null` |
| `RightAddOn` | 输入框右侧外部附加内容 | `object?` | `null` |
| `RightAddOnTemplate` | 右侧附加内容的数据模板 | `IDataTemplate?` | `null` |
| `InnerLeftContentTemplate` | 输入框内部左侧内容的数据模板 | `IDataTemplate?` | `null` |
| `InnerRightContentTemplate` | 输入框内部右侧内容的数据模板 | `IDataTemplate?` | `null` |

### 继承自 TextBox 的常用属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `Text` | 输入框文本内容 | `string?` | `null` |
| `Watermark` | 占位提示文字 | `string?` | `null` |
| `InnerLeftContent` | 输入框内部左侧内容（前缀） | `object?` | `null` |
| `InnerRightContent` | 输入框内部右侧内容（后缀） | `object?` | `null` |
| `PasswordChar` | 密码遮蔽字符 | `char` | `'\0'` |
| `RevealPassword` | 是否明文显示密码 | `bool` | `false` |
| `IsEnableRevealButton` | 是否启用密码显示/隐藏切换按钮 | `bool` | `false` |
| `IsEnableClearButton` | 是否启用一键清除按钮 | `bool` | `false` |
| `IsReadOnly` | 是否只读 | `bool` | `false` |
| `IsEnabled` | 是否启用 | `bool` | `true` |
| `MaxLength` | 最大输入长度 | `int` | `0`（无限制） |

## 枚举类型

### InputControlStyleVariant

| 值 | 说明 |
|---|---|
| `Outline` | 描边样式（默认），带有边框的经典输入框外观 |
| `Filled` | 填充样式，带有背景色填充 |
| `Borderless` | 无边框样式，适用于特殊布局场景 |

### InputControlStatus

| 值 | 说明 |
|---|---|
| `Default` | 默认状态，无特殊颜色标识 |
| `Error` | 错误状态，以红色系呈现，用于校验失败场景 |
| `Warning` | 警告状态，以橙色系呈现，用于提示性校验 |

### SizeType

| 值 | 说明 |
|---|---|
| `Large` | 大尺寸 |
| `Middle` | 中等尺寸（默认） |
| `Small` | 小尺寸 |

## 相关组件

- [SearchEdit](getting-started.md#搜索输入框) — 内置搜索按钮的搜索输入框，继承自 LineEdit
- [NumberUpDown](../number-up-down/overview.md) — 数字输入框，带递增/递减按钮
