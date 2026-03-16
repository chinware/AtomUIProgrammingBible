# QRCode API 参考

## 属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `Value` | 二维码编码的文本内容 | `string` | — |
| `IsBordered` | 是否显示边框 | `bool` | `true` |
| `Color` | 二维码前景色 | `IBrush?` | — |
| `EccLevel` | 纠错等级 | `QRCodeEccLevel` | `M` |
| `Size` | 二维码尺寸（像素） | `int` | `160` |
| `IconSize` | 中心图标尺寸（像素） | `int` | `40` |
| `Icon` | 中心图标 | `IImage?` | — |
| `IconBgColor` | 图标背景色 | `IBrush?` | — |
| `Status` | 二维码当前状态 | `QRCodeStatus` | `Active` |
| `LoadingContent` | 加载中状态的自定义内容 | `object?` | — |
| `LoadingContentTemplate` | 加载中状态的内容模板 | `IDataTemplate?` | — |
| `ExpiredContent` | 已过期状态的自定义内容 | `object?` | — |
| `ExpiredContentTemplate` | 已过期状态的内容模板 | `IDataTemplate?` | — |
| `ScannedContent` | 已扫描状态的自定义内容 | `object?` | — |
| `ScannedContentTemplate` | 已扫描状态的内容模板 | `IDataTemplate?` | — |

## 事件

| 事件 | 说明 | 类型 |
|---|---|---|
| `RefreshRequested` | 用户请求刷新二维码时触发 | `EventHandler` |

## 枚举类型

### QRCodeEccLevel

二维码纠错等级，等级越高容错能力越强。

| 值 | 说明 |
|---|---|
| `L` | 低纠错等级，约 7% 容错率 |
| `M` | 中纠错等级，约 15% 容错率（默认） |
| `Q` | 较高纠错等级，约 25% 容错率 |
| `H` | 高纠错等级，约 30% 容错率 |

### QRCodeStatus

二维码显示状态。

| 值 | 说明 |
|---|---|
| `Active` | 活跃状态，正常显示二维码 |
| `Expired` | 已过期状态 |
| `Loading` | 加载中状态 |
| `Scanned` | 已扫描状态 |

## 类继承关系

```
TemplatedControl
  └── QRCode
```
