# Calendar 快速入门

## 前置条件

- NuGet 安装 `Avalonia`
- NuGet 安装 `AtomUI`

## 基础用法

最基础最小配置化的日历组件，默认以月视图展示，选择模式为单选。

![AtomUI Calendar组件](./images/basic.webp)

```xaml
<StackPanel>
    <atom:Calendar />
</StackPanel>
```

## 显示模式

通过 `DisplayMode` 属性控制日历的视图粒度，支持 `Month`（月视图）、`Year`（年视图）和 `Decade`（十年视图）。

```xaml
<!-- 月视图（默认） -->
<atom:Calendar DisplayMode="Month" />

<!-- 年视图 -->
<atom:Calendar DisplayMode="Year" />

<!-- 十年视图 -->
<atom:Calendar DisplayMode="Decade" />
```

## 选择模式

通过 `SelectionMode` 属性控制日期选择行为。

```xaml
<!-- 单日期选择（默认） -->
<atom:Calendar SelectionMode="SingleDate" />

<!-- 单范围选择 -->
<atom:Calendar SelectionMode="SingleRange" />

<!-- 多范围选择 -->
<atom:Calendar SelectionMode="MultipleRange" />

<!-- 禁止选择（仅展示） -->
<atom:Calendar SelectionMode="None" />
```

| SelectionMode | 说明 |
|---|---|
| `SingleDate` | 只能选择单个日期（默认） |
| `SingleRange` | 可选择一段连续的日期范围 |
| `MultipleRange` | 可选择多段不连续的日期范围 |
| `None` | 禁止选择，日历仅用于展示 |

## 绑定选中日期

通过 `SelectedDate` 属性绑定当前选中的日期，支持双向绑定。

```xaml
<atom:Calendar SelectedDate="{Binding MySelectedDate}" />
```

对应的 ViewModel：

```csharp
public class MyViewModel : ViewModelBase
{
    private DateTime? _mySelectedDate;
    public DateTime? MySelectedDate
    {
        get => _mySelectedDate;
        set => this.RaiseAndSetIfChanged(ref _mySelectedDate, value);
    }
}
```

## 限制可选日期范围

通过 `DisplayDateStart` 和 `DisplayDateEnd` 属性约束用户可浏览和选择的日期范围。

```xaml
<!-- 只允许选择 2024 年的日期 -->
<atom:Calendar DisplayDateStart="2024-01-01"
               DisplayDateEnd="2024-12-31" />
```

## 设置每周起始日

通过 `FirstDayOfWeek` 属性自定义每周的起始日。

```xaml
<!-- 以周一作为每周第一天 -->
<atom:Calendar FirstDayOfWeek="Monday" />
```

## 今日高亮

默认情况下日历会高亮显示当天日期，可通过 `IsTodayHighlighted` 属性关闭。

```xaml
<!-- 关闭今日高亮 -->
<atom:Calendar IsTodayHighlighted="False" />
```

## 控制显示日期

通过 `DisplayDate` 属性设置日历初始显示的月份，支持双向绑定。

```xaml
<!-- 初始显示 2025 年 6 月 -->
<atom:Calendar DisplayDate="2025-06-01" />
```

## 自定义头部背景

通过 `HeaderBackground` 属性自定义日历头部区域的背景色。

```xaml
<atom:Calendar HeaderBackground="#E6F4FF" />
```

## 事件处理

监听 `DisplayDateChanged` 和 `DisplayModeChanged` 事件，响应用户的浏览操作。

```xaml
<atom:Calendar DisplayDateChanged="OnDisplayDateChanged"
               DisplayModeChanged="OnDisplayModeChanged" />
```

Code-behind 实现：

```csharp
private void OnDisplayDateChanged(object? sender, CalendarDateChangedEventArgs e)
{
    // e.AddedDate — 新的显示日期
    // e.RemovedDate — 旧的显示日期
}

private void OnDisplayModeChanged(object? sender, CalendarModeChangedEventArgs e)
{
    // e.NewMode — 新的显示模式
    // e.OldMode — 旧的显示模式
}
```

## 作为 DatePicker 基础控件

`Calendar` 是 `DatePicker` 的核心子组件。在大多数业务场景中，推荐直接使用 [DatePicker](../date-picker/overview.md) 获得弹出式日期选择体验。如需完全自定义日期选择交互，则可以基于 `Calendar` 自行封装。
