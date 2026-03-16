# PopupConfirm API 参考

## 属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `Title` | 弹窗标题 | `string` | - |
| `ConfirmContent` | 弹窗确认内容 | `object?` | `null` |
| `ConfirmContentTemplate` | 自定义确认内容的数据模板 | `IDataTemplate?` | `null` |
| `OkText` | 确认按钮文字，未设置时使用本地化默认文案 | `string` | - |
| `CancelText` | 取消按钮文字，未设置时使用本地化默认文案 | `string` | - |
| `OkButtonType` | 确认按钮的类型 | `ButtonType` | `Primary` |
| `IsShowCancelButton` | 是否显示取消按钮 | `bool` | `true` |
| `Icon` | 自定义图标，可使用 AtomUI 图标库 | `PathIcon?` | `null` |
| `ConfirmStatus` | 确认框语义状态，影响图标配色 | `PopupConfirmStatus` | `Warning` |

## 事件

| 事件 | 说明 | 参数类型 |
|---|---|---|
| `Confirmed` | 点击确认按钮时触发 | `RoutedEventArgs` |
| `Cancelled` | 点击取消按钮时触发 | `RoutedEventArgs` |
| `PopupClick` | 弹窗按钮点击时触发 | `PopupConfirmClickEventArgs` |

## 枚举类型

### PopupConfirmStatus

| 值 | 说明 |
|---|---|
| `Info` | 信息状态，蓝色系图标 |
| `Warning` | 警告状态，黄色系图标 |
| `Error` | 错误状态，红色系图标 |

## 继承关系

`PopupConfirm` 继承自 `FlyoutHost`，因此还可使用 `FlyoutHost` 提供的属性，例如 `Placement`、`IsShowArrow`、`Trigger` 等来控制弹窗的弹出行为。
