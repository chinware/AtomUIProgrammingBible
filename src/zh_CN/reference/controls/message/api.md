# Message API

### MessageCard

`MessageCard` 继承自 `TemplatedControl`，是消息提示的核心控件，用于渲染单条消息卡片。

### MessageType 枚举

| 枚举值 | 说明 |
| --- | --- |
| `Information` | 信息提示，用于一般性通知 |
| `Success` | 成功提示，用于操作成功后的反馈 |
| `Warning` | 警告提示，用于潜在风险的提醒 |
| `Error` | 错误提示，用于操作失败后的反馈 |
| `Loading` | 加载状态，用于异步操作进行中的提示 |

### 属性

| 属性名 | 类型 | 默认值 | 说明 |
| --- | --- | --- | --- |
| `MessageType` | `MessageType` | `MessageType.Information` | 消息类型，决定消息的图标与样式 |
| `Icon` | `PathIcon?` | `null` | 自定义图标，设置后将覆盖 `MessageType` 对应的默认图标 |
| `Message` | `string` | `string.Empty` | 消息文本内容 |
| `IsMotionEnabled` | `bool` | `true` | 是否启用消息出现和关闭时的动画效果 |
| `IsClosed` | `bool` | `false` | 消息是否已关闭 |

### 事件

| 事件名 | 事件参数类型 | 说明 |
| --- | --- | --- |
| `MessageClosed` | `RoutedEventArgs` | 消息关闭时触发的路由事件 |
