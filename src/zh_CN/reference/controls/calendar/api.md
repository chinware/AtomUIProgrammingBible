# Calendar API 参考

## 属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `FirstDayOfWeek` | 每周的起始日 | `DayOfWeek` | `Sunday` |
| `IsTodayHighlighted` | 是否高亮显示今天的日期 | `bool` | `true` |
| `HeaderBackground` | 日历头部区域的背景色 | `IBrush?` | `null` |
| `DisplayMode` | 日历的显示模式（月/年/十年） | `CalendarMode` | `Month` |
| `SelectionMode` | 日期选择模式 | `CalendarSelectionMode` | `SingleDate` |
| `SelectedDate` | 当前选中的日期（支持双向绑定） | `DateTime?` | `null` |
| `DisplayDate` | 当前显示的日期/月份（支持双向绑定） | `DateTime` | `DateTime.Today` |
| `DisplayDateStart` | 可显示的最早日期（支持双向绑定） | `DateTime?` | `null` |
| `DisplayDateEnd` | 可显示的最晚日期（支持双向绑定） | `DateTime?` | `null` |
| `IsMotionEnabled` | 是否启用过渡动画 | `bool` | `true` |

## 集合

| 属性 | 说明 | 类型 | 备注 |
|---|---|---|---|
| `SelectedDates` | 所有选中日期的集合 | `SelectedDatesCollection` | 只读 |

## 事件

| 事件 | 说明 | 参数类型 |
|---|---|---|
| `DisplayDateChanged` | 显示日期发生变化时触发 | `CalendarDateChangedEventArgs` |
| `DisplayModeChanged` | 显示模式发生变化时触发 | `CalendarModeChangedEventArgs` |

## 枚举类型

### CalendarMode

| 值 | 说明 |
|---|---|
| `Month` | 月视图，按天显示（默认） |
| `Year` | 年视图，按月显示 |
| `Decade` | 十年视图，按年显示 |

### CalendarSelectionMode

| 值 | 说明 |
|---|---|
| `SingleDate` | 只能选择单个日期（默认） |
| `SingleRange` | 可选择一段连续的日期范围 |
| `MultipleRange` | 可选择多段不连续的日期范围 |
| `None` | 禁止选择，日历仅用于展示 |

## 类继承关系

```
TemplatedControl
  └── Calendar
```

## 相关组件

- [DatePicker](../date-picker/overview.md) — 基于 Calendar 封装的弹出式日期选择器
