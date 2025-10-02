# 属性集合

| 属性 | 说明         |                                           类型                                            |           默认值            |
|:----:|:-----------|:---------------------------------------------------------------------------------------:|:------------------------:|
| `Command` | 命令绑定       |                                       `ICommand?`                                       |          `null`          |
| `CommandParameter` | 命令参数       |                                        `object?`                                        |          `null`          |
| `Flyout` | 弹出菜单内容     |                                        `Flyout?`                                        |          `null`          |
| `HotKey` | 快捷键        |                                      `KeyGesture?`                                      |          `null`          |
| `TriggerType` | Flyout触发方式 |                            `FlyoutTriggerType : Hover,Click`                            |         `Click`          |
| `IsShowArrow` | 是否显示箭头     |                                         `bool`                                          |         `False`          |
| `IsPointAtCenter` | 弹出菜单是否居中对齐 |                                         `bool`                                          |         `false`          |
| `Placement` | 弹出菜单位置模式   |              `PlacementMode`，参考 `Avalonia.Controls` 下的 `PlacementMode` 枚举               | `BottomEdgeAlignedRight` |
| `PlacementAnchor` | 弹出锚点       |  `PopupAnchor` ，参考 `Avalonia.Controls.Primitives.PopupPositioning` 下的 `PopupAnchor` 枚举  |    `PopupAnchor.None`    |
| `PlacementGravity` | 弹出吸附方向     | `PopupGravity` ，参考 `Avalonia.Controls.Primitives.PopupPositioning` 下的 `PopupGravity` 枚举 |   `PopupGravity.None`    |
| `MarginToAnchor` | 弹出与锚点的边距   |                                        `double`                                         |          `0.0`           |
| `MouseEnterDelay` | 鼠标移入延迟     |                                          `int`                                          |          `200`           |
| `MouseLeaveDelay` | 鼠标移出延迟     |                                          `int`                                          |          `200`           |
| `IsShowIndicator` | 是否显示指示器    |                                         `bool`                                          |         `False`          |
| `SizeType` | 尺寸类型       |                             `SizeType : Large,Middle,Small`                             |         `Medium`         |
| `Icon` | 主按钮图标      |                                         `Icon?`                                         |          `null`          |
| `FlyoutButtonIcon` | 副按钮图标      |                                         `Icon?`                                         |   `EllipsisOutlined()`   |
| `IsDanger` | 是否危险样式     |                                         `bool`                                          |         `False`          |
| `IsPrimaryButtonType` | 是否主按钮样式    |                                         `bool`                                          |         `False`          |
| `IsMotionEnabled` | 是否启用动效     |                                         `bool`                                          |          `True`          |
| `IsWaveSpiritEnabled` | 是否启用水波动画   |                                         `bool`                                          |          `True`          |