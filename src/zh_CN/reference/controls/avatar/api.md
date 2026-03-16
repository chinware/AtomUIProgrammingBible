# Avatar API 参考

## Avatar

`Avatar` 继承自 `TemplatedControl`，用于展示用户头像。

### 属性

| 属性名 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| `Gap` | `double` | `4.0` | 文字头像距离左右两侧边界的像素值 |
| `Icon` | `PathIcon?` | `null` | 设置图标类型的头像图标 |
| `BitmapSrc` | `IImage?` | `null` | 设置位图类型的头像图片源 |
| `Src` | `string?` | `null` | 设置图片类型的头像资源路径（支持 SVG 等格式） |
| `Text` | `string?` | `null` | 设置文字类型的头像显示文本 |
| `SizeType` | `CustomizableSizeType` | `Middle` | 预设头像尺寸，可选值为 `Large`、`Middle`、`Small` |
| `Size` | `double` | `NaN` | 自定义头像尺寸（像素），设置后将覆盖 `SizeType` 的效果 |
| `Shape` | `AvatarShape` | `Circle` | 头像形状，可选值为 `Circle`（圆形）、`Square`（方形） |
| `IsMotionEnabled` | `bool` | - | 是否启用过渡动画 |

### 枚举类型

#### AvatarShape

| 值 | 说明 |
|----|------|
| `Circle` | 圆形头像 |
| `Square` | 方形头像 |

#### CustomizableSizeType

| 值 | 说明 |
|----|------|
| `Large` | 大尺寸 |
| `Middle` | 中等尺寸（默认） |
| `Small` | 小尺寸 |

## AvatarGroup

`AvatarGroup` 用于将多个 `Avatar` 组合展示为头像组。

### 常用属性

| 属性名 | 类型 | 说明 |
|--------|------|------|
| `MaxDisplayCount` | `int` | 最大显示头像数量，超出部分将折叠显示 |
| `SizeType` | `CustomizableSizeType` | 统一设置组内头像尺寸 |
| `Shape` | `AvatarShape` | 统一设置组内头像形状 |
| `FoldInfoAvatarForeground` | `IBrush` | 折叠提示头像的前景色 |
| `FoldInfoAvatarBackground` | `IBrush` | 折叠提示头像的背景色 |
| `FoldAvatarFlyoutTriggerType` | - | 折叠头像弹出层的触发方式（如 `Click`） |
