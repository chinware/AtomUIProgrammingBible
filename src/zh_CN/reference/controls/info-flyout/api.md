# Flyout API

### 类定义

```
Flyout : PopupFlyoutBase
```

`Flyout` 继承自 `PopupFlyoutBase`，是气泡浮层的核心控件，负责承载弹出层的内容与样式配置。

### 属性

| 属性名 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| IsShowArrow | `bool` | `false` | 是否显示箭头指示器。设置为 `true` 时，浮层将带有一个指向触发元素的箭头 |
| MaskShadows | `BoxShadows` | - | 浮层的遮罩阴影效果，用于为弹出面板添加阴影以增强视觉层次 |
| IsPointAtCenter | `bool` | `false` | 箭头是否指向触发元素的中心。仅在 `IsShowArrow` 为 `true` 时生效 |
| Content | `object` | - | 浮层的显示内容，可以是任意控件或数据对象 |
| FlyoutPresenterTheme | `ControlTheme?` | `null` | 浮层面板的自定义主题，用于覆盖默认的弹出层外观样式 |

### FlyoutHost 常用属性

`Flyout` 通常配合 `FlyoutHost` 使用，以下为 `FlyoutHost` 的常用属性：

| 属性名 | 类型 | 说明 |
|--------|------|------|
| Trigger | `FlyoutTriggerType` | 触发方式，可选值为 `Hover`（悬停触发）和 `Click`（点击触发） |
| Placement | `PlacementMode` | 弹出方向，支持 12 种位置，如 `Top`、`Bottom`、`Left`、`Right` 及各边缘对齐变体 |
| IsShowArrow | `bool` | 是否显示箭头（可在 Host 层级设置，会传递给内部 Flyout） |
| IsPointAtCenter | `bool` | 箭头是否指向中心（可在 Host 层级设置） |
| Flyout | `PopupFlyoutBase` | 附加属性，用于定义飞出层内容 |
