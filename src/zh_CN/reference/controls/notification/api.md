# Notification API 参考

## NotificationCard

`NotificationCard` 继承自 `ContentControl`，是通知消息的视觉载体，用于展示单条通知内容。

### 属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `NotificationType` | 通知类型，决定图标和配色方案 | `NotificationType` | `Information` |
| `Title` | 通知标题 | `string` | `""` |
| `Icon` | 自定义图标，为空时根据 NotificationType 显示内置图标 | `PathIcon?` | `null` |
| `IsShowProgress` | 是否显示关闭倒计时进度条 | `bool` | `false` |
| `Expiration` | 自动关闭的等待时间，设置为 `TimeSpan.Zero` 则永不自动关闭 | `TimeSpan?` | `null` |
| `IsMotionEnabled` | 是否启用动画效果 | `bool` | `true` |
| `IsClosed` | 通知是否已关闭 | `bool` | `false` |

### 事件

| 事件 | 说明 | 参数类型 |
|---|---|---|
| `NotificationClosed` | 通知关闭时触发 | `RoutedEventArgs` |

## 枚举类型

### NotificationType

| 值 | 说明 |
|---|---|
| `Information` | 信息通知，蓝色系 |
| `Success` | 成功通知，绿色系 |
| `Warning` | 警告通知，黄色系 |
| `Error` | 错误通知，红色系 |

## WindowNotificationManager

`WindowNotificationManager` 用于管理通知的显示、位置和生命周期。

### 常用属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `MaxItems` | 最大同时显示的通知数量 | `int` | `5` |
| `Position` | 通知弹出位置 | `NotificationPosition` | `TopRight` |
| `IsPauseOnHover` | 鼠标悬停时是否暂停自动关闭倒计时 | `bool` | `true` |

### NotificationPosition

| 值 | 说明 |
|---|---|
| `TopLeft` | 左上角 |
| `TopCenter` | 顶部居中 |
| `TopRight` | 右上角 |
| `BottomLeft` | 左下角 |
| `BottomCenter` | 底部居中 |
| `BottomRight` | 右下角 |
