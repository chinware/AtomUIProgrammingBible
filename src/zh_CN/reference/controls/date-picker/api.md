# DatePicker API 参考

## 属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `SelectedDateTime` | 当前选中的日期时间（支持双向绑定，带验证） | `DateTime?` | `null` |
| `DefaultDateTime` | 默认日期时间（带验证） | `DateTime?` | `null` |
| `Format` | 日期时间的显示格式字符串 | `string?` | `null` |
| `IsShowTime` | 是否显示时间选择面板（时、分、秒） | `bool` | `false` |
| `IsNeedConfirm` | 是否需要用户点击确认按钮才提交选择 | `bool` | `false` |
| `IsShowNow` | 是否在面板中显示"此刻"快捷按钮 | `bool` | `true` |
| `ClockIdentifier` | 时钟制式（12 小时制或 24 小时制） | `ClockIdentifierType` | `HourClock12` |

## 方法

| 方法 | 说明 |
|---|---|
| `Clear()` | 清除当前选中的日期时间，将值置空 |
| `Reset()` | 将选中的日期时间重置为 `DefaultDateTime` 的值 |

## 枚举类型

### ClockIdentifierType

| 值 | 说明 |
|---|---|
| `HourClock12` | 12 小时制（默认），时间显示包含 AM/PM |
| `HourClock24` | 24 小时制，时间以 0-23 小时格式显示 |

## 类继承关系

```
InfoPickerInput
  └── DatePicker
```

## 相关组件

- [Calendar](../calendar/overview.md) — 日历面板组件，DatePicker 内部基于此组件构建
