# API 参考

## Dialog

`Dialog` 继承自 `TemplatedControl`，是 AtomUI 中模态对话框的核心组件。

### 属性

| 属性 | 类型 | 默认值 | 说明 |
|------|------|--------|------|
| `Title` | `string?` | `null` | 对话框标题 |
| `TitleIcon` | `PathIcon?` | `null` | 标题栏图标 |
| `Content` | `object?` | `null` | 对话框内容 |
| `ContentTemplate` | `IDataTemplate?` | `null` | 内容的数据模板 |
| `IsOpen` | `bool` | `false` | 控制对话框的显示与隐藏 |
| `IsModal` | `bool` | `true` | 是否为模态对话框，为 `true` 时产生遮罩层 |
| `IsResizable` | `bool` | `false` | 是否允许调整窗口大小 |
| `IsClosable` | `bool` | `true` | 是否显示关闭按钮 |
| `IsMaximizable` | `bool` | `false` | 是否显示最大化按钮 |
| `IsMinimizable` | `bool` | `true` | 是否显示最小化按钮 |
| `IsDragMovable` | `bool` | `false` | 是否允许拖拽移动 |
| `IsLightDismissEnabled` | `bool` | `false` | 是否允许点击遮罩区域关闭对话框 |
| `HorizontalStartupLocation` | `DialogHorizontalAnchor` | `Custom` | 水平方向的初始位置 |
| `VerticalStartupLocation` | `DialogVerticalAnchor` | `Custom` | 垂直方向的初始位置 |
| `Topmost` | `bool` | `false` | 是否置顶显示 |
| `StandardButtons` | `DialogStandardButtons` | - | 标准按钮配置，如 `Ok`、`Cancel`、`Yes`、`No` 等 |
| `IsFooterVisible` | `bool` | `true` | 是否显示底部按钮区域 |
| `IsMotionEnabled` | `bool` | - | 是否启用动画效果 |
| `DialogHostType` | `DialogHostType` | `Overlay` | 对话框宿主类型 |
| `IsLoading` | `bool` | `false` | 是否显示整体加载状态 |
| `IsConfirmLoading` | `bool` | `false` | 是否在确认按钮上显示加载状态 |

### 事件

| 事件 | 事件参数 | 说明 |
|------|----------|------|
| `Opened` | `EventArgs` | 对话框打开后触发 |
| `Closed` | `EventArgs` | 对话框关闭后触发 |
| `Closing` | `CancelEventArgs` | 对话框关闭前触发，可通过设置 `Cancel = true` 阻止关闭 |
| `Accepted` | `EventArgs` | 用户点击接受类按钮时触发 |
| `Rejected` | `EventArgs` | 用户点击拒绝类按钮时触发 |
| `Finished` | `DialogFinishedEventArgs` | 对话框完成交互后触发 |
| `ButtonClicked` | `DialogButtonClickedEventArgs` | 任意按钮被点击时触发，可通过 `e.Handled = true` 阻止默认行为 |

## 枚举类型

### DialogHostType

对话框宿主类型。

| 值 | 说明 |
|----|------|
| `Window` | 以独立原生窗口形式显示 |
| `Overlay` | 以覆盖层形式显示在当前窗口内（默认） |

### DialogHorizontalAnchor

对话框水平方向初始位置。

| 值 | 说明 |
|----|------|
| `Left` | 左对齐 |
| `Center` | 水平居中 |
| `Right` | 右对齐 |
| `Custom` | 自定义位置（默认） |

### DialogVerticalAnchor

对话框垂直方向初始位置。

| 值 | 说明 |
|----|------|
| `Top` | 顶部对齐 |
| `Center` | 垂直居中 |
| `Bottom` | 底部对齐 |
| `Custom` | 自定义位置（默认） |
