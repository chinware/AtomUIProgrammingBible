# 快速入门

### 基础配置条件

* Nuget安装Avalonia
* Nuget安装AtomUI

### 基础用法

`ButtonSpinner` 继承自 `Spinner` 类，通过 `Spin` 事件处理递增/递减逻辑。

下面示例中点击上下箭头时，会获取当前诗句在整体诗歌中的偏移量，然后将偏移量根据不同操作做加法或减法，再根据新的偏移量值获取响应的诗句并展示到UI中。

![AtomUI ButtonSpinner组件](./images/basic.webp)

```xaml
<atom:ButtonSpinner>
    <atom:TextBlock
        HorizontalAlignment="Left"
        VerticalAlignment="Center"
        Text="床前明月光" />
</atom:ButtonSpinner>
```

### 大小尺寸

通过 `SizeType` 属性设置组件大小，可选值有 `Large`、`Middle`、`Small`。

![AtomUI ButtonSpinner组件](./images/size.webp)

```xaml
<StackPanel Orientation="Vertical" Spacing="10" Margin="0, 0, 20, 0">
    <atom:ButtonSpinner SizeType="Large">
        <atom:TextBlock
            HorizontalAlignment="Left"
            VerticalAlignment="Center"
            Text="床前明月光" />
    </atom:ButtonSpinner>
    <atom:ButtonSpinner SizeType="Middle">
        <atom:TextBlock
            HorizontalAlignment="Left"
            VerticalAlignment="Center"
            Text="床前明月光" />
    </atom:ButtonSpinner>
    <atom:ButtonSpinner SizeType="Small">
        <atom:TextBlock
            HorizontalAlignment="Left"
            VerticalAlignment="Center"
            Text="床前明月光" />
    </atom:ButtonSpinner>
</StackPanel>
```

### 多种变体

变体的作用在于更好地融入不同的 UI 设计风格，是视觉方向的属性。通过 `StyleVariant` 属性设置，可选值有 `Outline`、`Filled`、`Borderless`。

![AtomUI ButtonSpinner组件](./images/variants.webp)

```xaml
<StackPanel Orientation="Vertical" Spacing="10">
    <atom:ButtonSpinner StyleVariant="Outline">
        <atom:TextBlock
            HorizontalAlignment="Left"
            VerticalAlignment="Center"
            Text="床前明月光" />
    </atom:ButtonSpinner>
    <atom:ButtonSpinner StyleVariant="Filled">
        <atom:TextBlock
            HorizontalAlignment="Left"
            VerticalAlignment="Center"
            Text="床前明月光" />
    </atom:ButtonSpinner>
    <atom:ButtonSpinner StyleVariant="Borderless">
        <atom:TextBlock
            HorizontalAlignment="Left"
            VerticalAlignment="Center"
            Text="床前明月光" />
    </atom:ButtonSpinner>
</StackPanel>
```

### 禁用状态

将 `IsEnabled` 设为 `False` 即可禁用组件，禁用后用户无法与 Spinner 按钮交互。

![AtomUI ButtonSpinner组件](./images/disabled.png)

```xaml
<StackPanel Orientation="Vertical" Spacing="10">
    <atom:ButtonSpinner StyleVariant="Outline" IsEnabled="False">
        <atom:TextBlock
            HorizontalAlignment="Left"
            VerticalAlignment="Center"
            Text="床前明月光" />
    </atom:ButtonSpinner>
    <atom:ButtonSpinner StyleVariant="Filled" IsEnabled="False">
        <atom:TextBlock
            HorizontalAlignment="Left"
            VerticalAlignment="Center"
            Text="床前明月光" />
    </atom:ButtonSpinner>
    <atom:ButtonSpinner StyleVariant="Borderless" IsEnabled="False">
        <atom:TextBlock
            HorizontalAlignment="Left"
            VerticalAlignment="Center"
            Text="床前明月光" />
    </atom:ButtonSpinner>
</StackPanel>
```

### LeftAddOn / RightAddOn 附加内容

有时候需要在组件的左侧或者右侧添加附加内容，可以使用 `LeftAddOn` 和 `RightAddOn` 属性。

* `LeftAddOn` 表示组件左侧的附加区域，其值可以是一个图标，也可以是字符串。
* `RightAddOn` 表示组件右侧的附加区域，其值可以是一个图标，也可以是字符串。

附加内容位于组件外部，与主体区域视觉上有明显的分隔。

![AtomUI ButtonSpinner组件](./images/pre-post-tab.webp)

```xaml
<StackPanel Orientation="Vertical" Spacing="10">
    <atom:ButtonSpinner
        LeftAddOn="http://"
        RightAddOn=".com"
        Width="400"
        HorizontalAlignment="Left">
        <atom:TextBlock
            HorizontalAlignment="Left"
            VerticalAlignment="Center"
            Text="床前明月光" />
    </atom:ButtonSpinner>

    <atom:ButtonSpinner
        RightAddOn="{atom:IconProvider Kind=SettingOutlined}"
        Width="400"
        HorizontalAlignment="Left">
        <atom:TextBlock
            HorizontalAlignment="Left"
            VerticalAlignment="Center"
            Text="床前明月光" />
    </atom:ButtonSpinner>

    <atom:ButtonSpinner
        LeftAddOn="http://"
        Width="400"
        HorizontalAlignment="Left"
        InnerRightContent=".com">
        <atom:TextBlock
            HorizontalAlignment="Left"
            VerticalAlignment="Center"
            Text="床前明月光" />
    </atom:ButtonSpinner>
</StackPanel>
```

### InnerLeftContent / InnerRightContent 前缀与后缀

前后缀与上面的 LeftAddOn / RightAddOn 不同，它们位于组件内部，是输入区域的一部分。

* `InnerLeftContent` 位于组件内部的左侧，作为内部前缀。
* `InnerRightContent` 位于组件内部的右侧，作为内部后缀。

两者的区别在于：`InnerLeftContent` / `InnerRightContent` 更趋向于输入框内部的补充信息，而 `LeftAddOn` / `RightAddOn` 更趋向于输入框外部的装饰。

![AtomUI ButtonSpinner组件](./images/prefix-suffix.webp)

```xaml
<StackPanel Orientation="Vertical" Spacing="10">

    <atom:ButtonSpinner
        InnerLeftContent="{atom:IconProvider Kind=UserOutlined, NormalFilledColor=#D7D7D7}"
        InnerRightContent="{atom:IconProvider Kind=InfoCircleOutlined, NormalFilledColor=#8C8C8C}"
        Width="400"
        HorizontalAlignment="Left">
        <atom:TextBlock
            HorizontalAlignment="Left"
            VerticalAlignment="Center"
            Text="床前明月光" />
    </atom:ButtonSpinner>

    <atom:ButtonSpinner
        InnerLeftContent="￥"
        InnerRightContent="RMB"
        Width="400"
        HorizontalAlignment="Left">
        <atom:TextBlock
            HorizontalAlignment="Left"
            VerticalAlignment="Center"
            Text="床前明月光" />
    </atom:ButtonSpinner>

    <atom:ButtonSpinner
        InnerLeftContent="￥" InnerRightContent="RMB" IsEnabled="False"
        Width="400"
        HorizontalAlignment="Left">
        <atom:TextBlock
            HorizontalAlignment="Left"
            VerticalAlignment="Center"
            Text="床前明月光" />
    </atom:ButtonSpinner>

</StackPanel>
```

### 状态颜色

`Status` 属性可以设定组件的状态颜色，用于向用户传达明确的意图。可选值有 `Default`、`Error`、`Warning`。

![AtomUI ButtonSpinner组件](./images/status.png)

```xaml
<StackPanel Orientation="Vertical" Spacing="10" Margin="0, 0, 20, 0">
    <atom:ButtonSpinner
        Status="Error"
        Width="400"
        HorizontalAlignment="Left">
        <atom:TextBlock
            HorizontalAlignment="Left"
            VerticalAlignment="Center"
            Text="床前明月光" />
    </atom:ButtonSpinner>
    <atom:ButtonSpinner
        Status="Warning"
        Width="400"
        HorizontalAlignment="Left">
        <atom:TextBlock
            HorizontalAlignment="Left"
            VerticalAlignment="Center"
            Text="床前明月光" />
    </atom:ButtonSpinner>

    <atom:ButtonSpinner
        Status="Error"
        Width="400"
        InnerLeftContent="{atom:IconProvider Kind=ClockCircleOutlined}"
        HorizontalAlignment="Left">
        <atom:TextBlock
            HorizontalAlignment="Left"
            VerticalAlignment="Center"
            Text="床前明月光" />
    </atom:ButtonSpinner>

    <atom:ButtonSpinner
        Status="Warning"
        Width="400"
        InnerLeftContent="{atom:IconProvider Kind=ClockCircleOutlined}"
        HorizontalAlignment="Left">
        <atom:TextBlock
            HorizontalAlignment="Left"
            VerticalAlignment="Center"
            Text="床前明月光" />
    </atom:ButtonSpinner>

    <atom:ButtonSpinner
        Status="Error"
        Width="400"
        InnerLeftContent="{atom:IconProvider Kind=ClockCircleOutlined}"
        HorizontalAlignment="Left"
        StyleVariant="Filled">
        <atom:TextBlock
            HorizontalAlignment="Left"
            VerticalAlignment="Center"
            Text="床前明月光" />
    </atom:ButtonSpinner>

    <atom:ButtonSpinner
        Status="Warning"
        Width="400"
        InnerLeftContent="{atom:IconProvider Kind=ClockCircleOutlined}"
        HorizontalAlignment="Left"
        StyleVariant="Filled">
        <atom:TextBlock
            HorizontalAlignment="Left"
            VerticalAlignment="Center"
            Text="床前明月光" />
    </atom:ButtonSpinner>


    <atom:ButtonSpinner
        Status="Error"
        Width="400"
        InnerLeftContent="{atom:IconProvider Kind=ClockCircleOutlined}"
        HorizontalAlignment="Left"
        StyleVariant="Borderless">
        <atom:TextBlock
            HorizontalAlignment="Left"
            VerticalAlignment="Center"
            Text="床前明月光" />
    </atom:ButtonSpinner>

    <atom:ButtonSpinner
        Status="Warning"
        Width="400"
        InnerLeftContent="{atom:IconProvider Kind=ClockCircleOutlined}"
        HorizontalAlignment="Left"
        StyleVariant="Borderless">
        <atom:TextBlock
            HorizontalAlignment="Left"
            VerticalAlignment="Center"
            Text="床前明月光" />
    </atom:ButtonSpinner>

</StackPanel>
```

### Spin 事件处理

`ButtonSpinner` 通过 `Spin` 事件响应用户的递增/递减操作。以下是一个完整的事件处理示例。

code-behind文件：
```csharp
using AtomUIGallery.ShowCases.ViewModels;
using Avalonia.Controls;
using Avalonia.LogicalTree;
using Avalonia.ReactiveUI;
using Avalonia.VisualTree;
using ReactiveUI;
using ButtonSpinner = AtomUI.Controls.ButtonSpinner;

public partial class ButtonSpinnerShowCase : ReactiveUserControl<ButtonSpinnerViewModel>
{
    public ButtonSpinnerShowCase()
    {
        this.WhenActivated(disposables =>
        {
            BindSpinHandleRecursively(this);
        });
        InitializeComponent();
    }

    private void BindSpinHandleRecursively(Control control)
    {
        if (control is ButtonSpinner spinner)
        {
            if (DataContext is ButtonSpinnerViewModel viewModel)
            {
                spinner.Spin += viewModel.HandleSpin;
            }
        }
        else
        {
            foreach (var item in control.GetVisualChildren())
            {
                if (item is Control childControl)
                {
                    BindSpinHandleRecursively(childControl);
                }
            }
        }
    }
}
```

view-model文件：
```csharp
using Avalonia.Controls;
using ReactiveUI;
using ButtonSpinner = AtomUI.Controls.ButtonSpinner;

public class ButtonSpinnerViewModel : ReactiveObject, IRoutableViewModel
{
    public const string ID = "ButtonSpinner";

    public IScreen HostScreen { get; }

    public string UrlPathSegment { get; } = ID;

    public ButtonSpinnerViewModel(IScreen screen)
    {
        HostScreen = screen;
    }

    public void HandleSpin(object? sender, SpinEventArgs e)
    {
        if (sender is ButtonSpinner buttonSpinner)
        {
            if (buttonSpinner.Content is TextBlock textBlock)
            {
                var value = Array.IndexOf(_spinnerItems, textBlock.Text);
                if (e.Direction == SpinDirection.Increase)
                {
                    value++;
                }
                else
                {
                    value--;
                }

                if (value < 0)
                {
                    value = _spinnerItems.Length - 1;
                }
                else if (value >= _spinnerItems.Length)
                {
                    value = 0;
                }

                textBlock.Text = _spinnerItems[value];
            }
        }
    }

    private readonly string[] _spinnerItems =
    {
        "床前明月光",
        "疑是地上霜",
        "举头望明月",
        "低头思故乡"
    };
}
```
