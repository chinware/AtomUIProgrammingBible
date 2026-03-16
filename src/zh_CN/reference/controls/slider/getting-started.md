# Slider 快速入门

### 基础配置条件

* Nuget安装Avalonia
* Nuget安装AtomUI

### 基础用法

通过 `Maximum` 和 `Minimum` 设置滑块的取值范围，通过 `Value` 设置初始值。`TickFrequency` 控制刻度间隔，`IsEnabled` 控制启用状态。

![AtomUI Slider组件](./images/basic.webp)

axaml文件：
```xaml
<StackPanel Orientation="Vertical" Spacing="20">
    <atom:Slider
        Maximum="100"
        Minimum="0"
        TickFrequency="5"
        IsEnabled="{Binding NormalEnabled}"
        Value="50" />

    <atom:Slider
        Maximum="100"
        Minimum="0"
        IsRangeMode="True"
        TickFrequency="5"
        IsEnabled="{Binding NormalEnabled}"
        RangeValue="20, 80" />
    <atom:Slider
        Maximum="100"
        Minimum="0"
        IsEnabled="{Binding NormalEnabled}"
        IsRangeMode="True"
        TickFrequency="5"
        Marks="{Binding SliderMarks}"
        RangeValue="20, 80" />

    <StackPanel Orientation="Horizontal" Spacing="2">
        <atom:TextBlock VerticalAlignment="Center">Enabled:</atom:TextBlock>
        <atom:ToggleSwitch VerticalAlignment="Center" SizeType="Small" IsChecked="{Binding NormalEnabled, Mode=TwoWay}" />
    </StackPanel>
</StackPanel>
```

view-model文件：
```csharp
using AtomUI.Controls;
using Avalonia.Collections;
using Avalonia.Media;
using ReactiveUI;
public class SliderViewModel : ReactiveObject, IRoutableViewModel
{
    public const string ID = "Slider";

    public IScreen HostScreen { get; }

    public string UrlPathSegment { get; } = ID;

    private AvaloniaList<SliderMark>? _sliderMarks;

    public AvaloniaList<SliderMark>? SliderMarks
    {
        get => _sliderMarks;
        set => this.RaiseAndSetIfChanged(ref _sliderMarks, value);
    }

    private bool _normalEnabled = true;

    public bool NormalEnabled
    {
        get => _normalEnabled;
        set => this.RaiseAndSetIfChanged(ref _normalEnabled, value);
    }

    public SliderViewModel(IScreen screen)
    {
        HostScreen  = screen;
        SliderMarks = new AvaloniaList<SliderMark>();
        SliderMarks.Add(new SliderMark("0°C", 0));
        SliderMarks.Add(new SliderMark("26°C", 26));
        SliderMarks.Add(new SliderMark("37°C", 37));
        SliderMarks.Add(new SliderMark("100°C", 100)
        {
            LabelFontWeight = FontWeight.Bold,
            LabelBrush      = new SolidColorBrush(Colors.Red)
        });
    }
}
```

### 范围模式

将 `IsRangeMode` 设置为 `True` 可启用范围模式，此时显示两个滑块。通过 `RangeValue` 设置范围的起始值和结束值，格式为 `"起始值, 结束值"`。

```xaml
<atom:Slider
    Maximum="100"
    Minimum="0"
    IsRangeMode="True"
    TickFrequency="5"
    RangeValue="20, 80" />
```

### 刻度标记

通过 `Marks` 属性绑定标记点数据，可在滑块轨道上显示自定义刻度标记。`Included` 属性控制标记点的高亮行为：

* `Included="True"`（默认）：处于选中范围内的标记点和轨道区域会高亮显示。
* `Included="False"`：所有标记点统一显示，不区分是否在选中范围内。

![AtomUI Slider组件](./images/gradruate.webp)

```xaml
<StackPanel Orientation="Vertical" Spacing="20">
    <atom:TextBlock FontWeight="Bold">included=true</atom:TextBlock>
    <atom:Slider
        Maximum="100"
        Minimum="0"
        TickFrequency="1"
        Marks="{Binding SliderMarks}"
        Value="20" />

    <atom:TextBlock FontWeight="Bold">included=false</atom:TextBlock>
    <atom:Slider
        Maximum="100"
        Minimum="0"
        TickFrequency="1"
        Marks="{Binding SliderMarks}"
        Included="False"
        Value="20" />
</StackPanel>
```

### 工具提示

通过 `IsSnapToTickEnabled` 启用刻度吸附，使滑块只能停在刻度点上。`ValueFormatTemplate` 用于自定义工具提示的数值显示格式。

![AtomUI Slider组件](./images/tooltips.webp)

```xaml
<atom:Slider
    Maximum="100"
    Minimum="0"
    TickFrequency="1"
    IsSnapToTickEnabled="True"
    ValueFormatTemplate="\{0\}%"
    Value="20" />
```

### 垂直方向

将 `Orientation` 设置为 `Vertical` 可使滑块以垂直方向显示。垂直模式下同样支持范围模式和刻度标记。

![AtomUI Slider组件](./images/vertical.webp)

```xaml
<StackPanel Orientation="Horizontal" Spacing="20" Height="300">
    <atom:Slider
        Maximum="100"
        Minimum="0"
        Orientation="Vertical"
        TickFrequency="1"
        Value="20" />
    <atom:Slider
        Maximum="100"
        Minimum="0"
        Orientation="Vertical"
        TickFrequency="5"
        IsRangeMode="True"
        RangeValue="20, 80"
        IsSnapToTickEnabled="True"
        Value="20" />

    <atom:Slider
        Maximum="100"
        Minimum="0"
        Orientation="Vertical"
        TickFrequency="1"
        Marks="{Binding SliderMarks}"
        Value="20" />

    <atom:Slider
        Maximum="100"
        Minimum="0"
        IsRangeMode="True"
        Orientation="Vertical"
        TickFrequency="5"
        Marks="{Binding SliderMarks}"
        RangeValue="20, 80" />
</StackPanel>
```
