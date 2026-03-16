# ButtonSpinner API 参考

## 属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `AllowSpin` | 是否允许通过 Spinner 按钮触发 Spin 事件 | `bool` | `true` |
| `ShowButtonSpinner` | 是否显示 Spinner 按钮 | `bool` | `true` |
| `ButtonSpinnerLocation` | Spinner 按钮的显示位置 | `ButtonSpinnerLocation` | `Right` |
| `LeftAddOn` | 组件左侧附加内容 | `object?` | `null` |
| `LeftAddOnTemplate` | 左侧附加内容的数据模板 | `IDataTemplate?` | `null` |
| `RightAddOn` | 组件右侧附加内容 | `object?` | `null` |
| `RightAddOnTemplate` | 右侧附加内容的数据模板 | `IDataTemplate?` | `null` |
| `InnerLeftContent` | 组件内部左侧前缀内容 | `object?` | `null` |
| `InnerLeftContentTemplate` | 内部左侧前缀内容的数据模板 | `IDataTemplate?` | `null` |
| `InnerRightContent` | 组件内部右侧后缀内容 | `object?` | `null` |
| `InnerRightContentTemplate` | 内部右侧后缀内容的数据模板 | `IDataTemplate?` | `null` |
| `SizeType` | 组件尺寸 | `SizeType` | `Middle` |
| `StyleVariant` | 样式变体 | `InputControlStyleVariant` | `Outline` |
| `Status` | 状态颜色 | `InputControlStatus` | `Default` |
| `IsButtonSpinnerFloatable` | Spinner 按钮是否可浮动 | `bool` | `false` |
| `IsMotionEnabled` | 是否启用过渡动画 | `bool` | `true` |
| `IsEnabled` | 是否启用（继承自基类） | `bool` | `true` |
| `Content` | 组件内容（继承自基类） | `object?` | `null` |

## 事件

| 事件 | 说明 | 参数类型 |
|---|---|---|
| `Spin` | 用户点击递增/递减按钮时触发 | `SpinEventArgs` |

## 枚举类型

### ButtonSpinnerLocation

| 值 | 说明 |
|---|---|
| `Left` | Spinner 按钮显示在组件左侧 |
| `Right` | Spinner 按钮显示在组件右侧（默认） |

### SizeType

| 值 | 说明 |
|---|---|
| `Large` | 大尺寸 |
| `Middle` | 中等尺寸（默认） |
| `Small` | 小尺寸 |

### InputControlStyleVariant

| 值 | 说明 |
|---|---|
| `Outline` | 带边框样式（默认） |
| `Filled` | 填充背景样式 |
| `Borderless` | 无边框样式 |

### InputControlStatus

| 值 | 说明 |
|---|---|
| `Default` | 默认状态 |
| `Error` | 错误状态，红色系 |
| `Warning` | 警告状态，橙色系 |

### SpinDirection

| 值 | 说明 |
|---|---|
| `Increase` | 递增方向（点击上箭头） |
| `Decrease` | 递减方向（点击下箭头） |

## 相关组件

- [Button](../button/overview.md) -- 基础按钮组件
