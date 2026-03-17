# NumericUpDown API

### 概述

`NumericUpDown` 继承自 `Avalonia.Controls.NumericUpDown`，在原生控件基础上扩展了样式、状态、前后缀等能力。

### 属性

| 属性名 | 类型 | 默认值 | 说明 |
| --- | --- | --- | --- |
| Value | decimal? | - | 当前数值 |
| Minimum | decimal? | - | 最小值 |
| Maximum | decimal? | - | 最大值 |
| Increment | decimal | 1 | 每次递增/递减的步长 |
| SizeType | SizeType | Middle | 控件尺寸，可选 Large、Middle、Small |
| StyleVariant | InputControlStyleVariant | Outline | 样式变体，可选 Outline、Filled、Borderless |
| Status | InputControlStatus | Normal | 状态色，可选 Normal、Error、Warning |
| PlaceholderText | string? | null | 水印占位文本 |
| PlaceholderForeground | IBrush? | null | 水印文本前景色 |
| IsAllowClear | bool | false | 是否显示一键清除按钮 |
| ClearIcon | PathIcon? | null | 自定义清除按钮图标 |
| LeftAddOn | object? | null | 输入框左侧的前置标签，可以是字符串或图标 |
| LeftAddOnTemplate | IDataTemplate? | null | 左侧前置标签的数据模板 |
| RightAddOn | object? | null | 输入框右侧的后置标签，可以是字符串或图标 |
| RightAddOnTemplate | IDataTemplate? | null | 右侧后置标签的数据模板 |
| InnerLeftContentTemplate | IDataTemplate? | null | 输入框内部左侧前缀的数据模板 |
| InnerRightContentTemplate | IDataTemplate? | null | 输入框内部右侧后缀的数据模板 |
| StringMode | bool | false | 字符串模式，启用后可通过 StringValue 获取高精度数值的字符串表示 |
| StringValue | string? | null | 字符串模式下的数值字符串 |
| Keyboard | bool | true | 是否允许通过键盘上下键调整数值 |
| MouseWheel | bool | true | 是否允许通过鼠标滚轮调整数值 |
| IsMotionEnabled | bool | true | 是否启用动画效果 |
| IsEnabled | bool | true | 是否启用控件（继承自基类） |

### 样式变体

| 变体 | 说明 |
| --- | --- |
| Outline | 带边框的默认样式 |
| Filled | 填充背景样式 |
| Borderless | 无边框样式 |

### 尺寸

| 尺寸 | 说明 |
| --- | --- |
| Large | 大尺寸 |
| Middle | 中尺寸（默认） |
| Small | 小尺寸 |

### 状态色

| 状态 | 说明 |
| --- | --- |
| Normal | 默认状态 |
| Error | 错误状态，边框显示为红色 |
| Warning | 警告状态，边框显示为橙色 |
