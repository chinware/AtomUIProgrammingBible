# Drawer API 参考

## Drawer

`Drawer` 继承自 `Control`，用于创建从屏幕或容器边缘滑出的浮层面板。

### 属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `Content` | 抽屉的主体内容 | `object?` | - |
| `ContentTemplate` | 抽屉主体内容的数据模板 | `IDataTemplate?` | - |
| `IsOpen` | 抽屉是否处于打开状态（支持双向绑定） | `bool` | `false` |
| `Placement` | 抽屉的弹出方向 | `DrawerPlacement` | `Right` |
| `OpenOn` | 抽屉渲染的目标容器，设置后启用局部渲染模式 | `Control?` | - |
| `IsShowMask` | 是否显示遮罩层 | `bool` | `true` |
| `IsShowCloseButton` | 是否显示关闭按钮 | `bool` | `true` |
| `CloseWhenClickOnMask` | 点击遮罩层时是否关闭抽屉 | `bool` | `true` |
| `Title` | 抽屉标题 | `string` | - |
| `Footer` | 抽屉底部操作区域内容 | `object?` | - |
| `FooterTemplate` | 底部操作区域的数据模板 | `IDataTemplate?` | - |
| `Extra` | 抽屉头部右侧的额外操作区域内容 | `object?` | - |
| `ExtraTemplate` | 头部额外操作区域的数据模板 | `IDataTemplate?` | - |
| `SizeType` | 抽屉的预设尺寸，`Small` 为 378px，`Large` 为 736px | `CustomizableSizeType` | `Small` |
| `DialogSize` | 自定义抽屉尺寸 | `Dimension` | - |
| `PushOffsetPercent` | 推挤偏移百分比 | `double` | - |
| `IsMotionEnabled` | 是否启用开启/关闭动画 | `bool` | - |

### 事件

| 事件 | 说明 |
|---|---|
| `Opened` | 抽屉打开后触发 |
| `Closed` | 抽屉关闭后触发 |

## 枚举类型

### DrawerPlacement

| 值 | 说明 |
|---|---|
| `Left` | 从左侧滑出 |
| `Top` | 从顶部滑出 |
| `Right` | 从右侧滑出 |
| `Bottom` | 从底部滑出 |
