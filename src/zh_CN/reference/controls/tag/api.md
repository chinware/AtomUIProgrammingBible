# Tag API 参考

## Tag

标签组件，继承自 `TemplatedControl`，用于标记和分类。

### 属性

| 属性名 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| `TagColor` | `string?` | `null` | 标签颜色，支持 13 种预设颜色名称（如 `magenta`、`red`、`volcano` 等）、5 种状态颜色名称（`success`、`info`、`error`、`warning`、`default`）以及自定义十六进制色值（如 `#f50`） |
| `IsClosable` | `bool` | `false` | 是否显示关闭按钮 |
| `Bordered` | `bool` | `true` | 是否显示边框 |
| `Icon` | `PathIcon?` | `null` | 标签左侧的自定义图标 |
| `CloseIcon` | `PathIcon?` | `null` | 自定义关闭按钮图标，仅在 `IsClosable` 为 `true` 时有效 |
| `TagText` | `string?` | `null` | 标签显示的文本内容 |

### 事件

| 事件名 | 事件参数类型 | 说明 |
|--------|------------|------|
| `Closed` | `RoutedEventArgs` | 关闭标签时触发的事件 |

---

## TagStatus 枚举

定义标签的状态类型。

| 值 | 说明 |
|----|------|
| `Success` | 成功状态 |
| `Info` | 信息状态 |
| `Error` | 错误状态 |
| `Warning` | 警告状态 |

### 预设颜色名称

`TagColor` 属性支持以下 13 种预设颜色名称：

`magenta`、`red`、`volcano`、`orange`、`gold`、`lime`、`green`、`cyan`、`blue`、`geekblue`、`purple`

此外还支持 5 种状态颜色名称：

`success`、`info`、`error`、`warning`、`default`
