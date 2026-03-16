# Button API 参考

## 属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `ButtonType` | 按钮类型 | `ButtonType` | `Default` |
| `Shape` | 按钮形状 | `ButtonShape` | `Default` |
| `SizeType` | 按钮尺寸 | `SizeType` | `Middle` |
| `Icon` | 按钮图标 | `PathIcon?` | `null` |
| `IsDanger` | 是否为危险按钮（红色系） | `bool` | `false` |
| `IsGhost` | 是否为幽灵按钮（透明背景） | `bool` | `false` |
| `IsLoading` | 是否处于加载状态 | `bool` | `false` |
| `IsEnabled` | 是否启用（继承自基类） | `bool` | `true` |
| `IsMotionEnabled` | 是否启用过渡动画 | `bool` | `true` |
| `IsWaveSpiritEnabled` | 是否启用点击波纹效果 | `bool` | `true` |
| `Command` | 绑定的命令（继承自基类） | `ICommand?` | `null` |
| `CommandParameter` | 命令参数（继承自基类） | `object?` | `null` |
| `HotKey` | 快捷键（继承自基类） | `KeyGesture?` | `null` |
| `Content` | 按钮内容/文本（继承自基类） | `object?` | `null` |

## 事件

| 事件 | 说明 | 参数类型 |
|---|---|---|
| `Click` | 按钮点击时触发 | `RoutedEventArgs` |

## 枚举类型

### ButtonType

| 值 | 说明 |
|---|---|
| `Default` | 默认按钮，带边框和白色背景 |
| `Primary` | 主要按钮，实心填充，用于强调主操作 |
| `Dashed` | 虚线边框按钮，常用于添加操作 |
| `Text` | 文本按钮，无边框无背景 |
| `Link` | 链接按钮，呈现为超链接样式 |

### ButtonShape

| 值 | 说明 |
|---|---|
| `Default` | 默认圆角矩形 |
| `Circle` | 圆形，适合纯图标按钮 |
| `Round` | 胶囊形（大圆角） |

### SizeType

| 值 | 说明 |
|---|---|
| `Large` | 大尺寸 |
| `Middle` | 中等尺寸（默认） |
| `Small` | 小尺寸 |

## 伪类（Pseudo Classes）

Button 支持以下伪类用于自定义样式：

| 伪类 | 说明 |
|---|---|
| `:primary` | ButtonType 为 Primary 时 |
| `:default` | ButtonType 为 Default 时 |
| `:dashed` | ButtonType 为 Dashed 时 |
| `:text` | ButtonType 为 Text 时 |
| `:link` | ButtonType 为 Link 时 |
| `:danger` | IsDanger 为 true 时 |
| `:loading` | IsLoading 为 true 时 |
| `:icononly` | 按钮仅包含图标无文字时 |

## 相关组件

- [DropdownButton](../dropdown-button/overview.md) — 带下拉菜单的按钮
- [SplitButton](../split-button/overview.md) — 组合按钮，主按钮 + 下拉操作
- [ButtonSpinner](../button-spinner/overview.md) — 带递增/递减按钮的输入框
