# TimePicker API 参考

## 属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `SelectedTime` | 当前选中的时间（支持双向绑定） | `TimeSpan?` | `null` |
| `DefaultTime` | 默认时间 | `TimeSpan?` | `null` |
| `IsNeedConfirm` | 是否需要用户点击确认按钮才提交选择 | `bool` | `false` |
| `IsShowNow` | 是否在面板中显示"此刻"快捷按钮 | `bool` | `true` |
| `MinuteIncrement` | 分钟选择器的步进间隔，取值范围 1-59 | `int` | `1` |
| `SecondIncrement` | 秒钟选择器的步进间隔，取值范围 1-59 | `int` | `1` |
| `ClockIdentifier` | 时钟制式（12 小时制或 24 小时制） | `ClockIdentifierType` | `HourClock12` |

## 枚举类型

### ClockIdentifierType

| 值 | 说明 |
|---|---|
| `HourClock12` | 12 小时制（默认），时间显示包含 AM/PM |
| `HourClock24` | 24 小时制，时间以 0-23 小时格式显示 |

## 类继承关系

```
InfoPickerInput
  └── TimePicker
```

## 相关组件

- [RangeTimePicker](./getting-started.md#时间范围选择器) — 时间范围选择器，用于选择起止时间
