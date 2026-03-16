# Badge API 参考

## CountBadge

计数徽标组件，继承自 `Control`，用于展示数字角标。

### 属性

| 属性名 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| `BadgeColor` | `string?` | `null` | 自定义徽标背景颜色，支持预设颜色名称和自定义色值（HEX、RGB、HSL 等格式） |
| `Count` | `int` | `0` | 显示的计数数字 |
| `DecoratedTarget` | `Control?` | `null` | 被装饰的目标控件，也可通过将目标控件作为子元素传入 |
| `Offset` | `Point` | `0,0` | 徽标相对于默认位置的偏移量 |
| `OverflowCount` | `int` | `99` | 数字溢出上限，超出时显示为 `{OverflowCount}+` |
| `ShowZero` | `bool` | `false` | 当 `Count` 为 0 时是否仍然显示徽标 |
| `Size` | `CountBadgeSize` | `Default` | 徽标尺寸大小 |
| `BadgeIsVisible` | `bool` | `true` | 控制徽标是否可见 |
| `IsMotionEnabled` | `bool` | - | 是否启用动画效果 |

### CountBadgeSize 枚举

| 值 | 说明 |
|----|------|
| `Default` | 默认尺寸 |
| `Small` | 小尺寸 |

---

## DotBadge

圆点徽标组件，继承自 `Control`，用于展示状态圆点或红点标记。

### 属性

| 属性名 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| `DotColor` | `string?` | `null` | 自定义圆点颜色，支持预设颜色名称（如 Pink、Red、Cyan 等）和自定义色值 |
| `Status` | `DotBadgeStatus?` | `null` | 圆点状态类型，设置后将使用对应状态的预定义颜色 |
| `Text` | `string?` | `null` | 状态圆点旁显示的说明文字，独立使用模式下有效 |
| `DecoratedTarget` | `Control?` | `null` | 被装饰的目标控件，也可通过将目标控件作为子元素传入 |
| `Offset` | `Point` | `0,0` | 圆点相对于默认位置的偏移量 |
| `BadgeIsVisible` | `bool` | `false` | 控制圆点是否可见 |
| `IsMotionEnabled` | `bool` | - | 是否启用动画效果 |

### DotBadgeStatus 枚举

| 值 | 说明 |
|----|------|
| `Default` | 默认状态（灰色） |
| `Success` | 成功状态（绿色） |
| `Processing` | 处理中状态（蓝色，带动画效果） |
| `Error` | 错误状态（红色） |
| `Warning` | 警告状态（黄色） |

### 预设颜色名称

DotBadge 的 `DotColor` 属性支持以下预设颜色名称：

`Pink`、`Red`、`Yellow`、`Orange`、`Cyan`、`Green`、`Blue`、`Purple`、`GeekBlue`、`Magenta`、`Volcano`、`Gold`、`Lime`

---

## RibbonBadge

缎带徽标组件，继承自 `Control`，用于在内容区域添加缎带样式的装饰标签。

### 属性

| 属性名 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| `RibbonColor` | `string?` | `null` | 自定义缎带颜色，支持预设颜色名称和自定义色值 |
| `DecoratedTarget` | `Control?` | `null` | 被装饰的目标控件，也可通过将目标控件作为子元素传入 |
| `Offset` | `Point` | `0,0` | 缎带相对于默认位置的偏移量 |
| `Text` | `string?` | `null` | 缎带上显示的文字内容 |
| `Placement` | `RibbonBadgePlacement` | `End` | 缎带放置位置 |
| `BadgeIsVisible` | `bool` | `false` | 控制缎带是否可见 |

### RibbonBadgePlacement 枚举

| 值 | 说明 |
|----|------|
| `Start` | 放置在左上角 |
| `End` | 放置在右上角（默认） |
