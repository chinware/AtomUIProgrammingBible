# QRCode 快速入门

## 前置条件

- NuGet 安装 `Avalonia`
- NuGet 安装 `AtomUI`
- 本页文档末尾有公共 ViewModel 代码

## 基础用法

最基础的用法，通过 `Value` 属性设置二维码内容。配合输入框可实现动态生成二维码。

![AtomUI QRcode组件](./images/basic.webp)

```xaml
<StackPanel Orientation="Vertical">
    <atom:QRCode Value="{Binding QRCodeInput}" />
    <atom:LineEdit Text="{Binding QRCodeInput}" Margin="0,20,0,0" />
</StackPanel>
```

## 自定义图标

通过 `Icon` 属性为二维码中心设置自定义图标，支持 Avalonia 的 `avares://` 资源路径。

![AtomUI QRcode组件](./images/with-icon.png)

```xaml
<atom:QRCode Value="https://atomui.net" Icon="avares://AtomUIGallery/Assets/ATOMUI-LOGO.png" />
```

## 内置状态

通过 `Status` 属性控制二维码的显示状态。支持 `Loading`（加载中）、`Expired`（已过期）、`Scanned`（已扫描）三种非活跃状态。根据 MVVM 原则，建议将 `Status` 绑定到 ViewModel 属性。

![AtomUI QRcode组件](./images/status.webp)

```xaml
<atom:QRCode Value="https://atomui.net" Status="Loading" />
<atom:QRCode Value="https://atomui.net" Status="Expired" />
<atom:QRCode Value="https://atomui.net" Status="Scanned" />
```

## 自定义状态内容

通过 `LoadingContent`、`ExpiredContent`、`ScannedContent` 属性可以自定义各状态下显示的界面内容，允许开发者针对业务需求定制状态展示。也可以使用对应的 `DataTemplate` 属性（`LoadingContentTemplate`、`ExpiredContentTemplate`、`ScannedContentTemplate`）进行模板化定制。

![AtomUI QRcode组件](./images/custom-status.png)

```xaml
<WrapPanel ItemSpacing="20" LineSpacing="20" Orientation="Horizontal">
    <atom:QRCode Value="https://atomui.net" Status="Loading">
        <atom:QRCode.LoadingContent>
            <StackPanel Orientation="Vertical" HorizontalAlignment="Center" VerticalAlignment="Center">
                <atom:Spin IsSpinning="True" HorizontalAlignment="Center"/>
                <atom:TextBlock>Loading...</atom:TextBlock>
            </StackPanel>
        </atom:QRCode.LoadingContent>
    </atom:QRCode>
    <atom:QRCode Value="https://atomui.net" Status="Expired">
        <atom:QRCode.ExpiredContent>
            <StackPanel Orientation="Vertical" HorizontalAlignment="Center" VerticalAlignment="Center">
                <StackPanel Orientation="Horizontal" HorizontalAlignment="Center"
                            VerticalAlignment="Center" Spacing="5">
                    <antdicons:CloseCircleFilled FillBrush="Red" Width="16" Height="16" />
                    <atom:TextBlock HorizontalAlignment="Center" VerticalAlignment="Center">二维码过期</atom:TextBlock>
                </StackPanel>
                <atom:Button HorizontalAlignment="Center"
                             Icon="{antdicons:AntDesignIconProvider Kind=ReloadOutlined}" ButtonType="Link">
                    点击刷新
                </atom:Button>
            </StackPanel>
        </atom:QRCode.ExpiredContent>
    </atom:QRCode>
    <atom:QRCode Value="https://atomui.net" Status="Scanned">
        <atom:QRCode.ScannedContent>
            <StackPanel Orientation="Horizontal" HorizontalAlignment="Center"
                        VerticalAlignment="Center"
                        Spacing="5">
                <antdicons:CheckCircleFilled FillBrush="Green" Width="16" Height="16" />
                <atom:TextBlock HorizontalAlignment="Center" VerticalAlignment="Center">已扫描</atom:TextBlock>
            </StackPanel>
        </atom:QRCode.ScannedContent>
    </atom:QRCode>
</WrapPanel>
```

## 纠错等级

通过 `EccLevel` 属性设置二维码的纠错等级，支持 `L`、`M`、`Q`、`H` 四个等级。纠错等级越高，二维码的容错能力越强，但信息密度也越高。

![AtomUI QRcode组件](./images/ecc.webp)

```xaml
<StackPanel Orientation="Vertical" Spacing="10">
    <atom:QRCode Value="https://gw.alipayobjects.com/zos/rmsportal/KDpgvguMpGfqaHPjicRK.svg"
                 EccLevel="{Binding #EccLevel.SelectedItem}" />
    <atom:Segmented Name="EccLevel" ItemsSource="{Binding EccLevels}" />
</StackPanel>
```

## 自定义尺寸

通过 `Size` 属性控制二维码整体尺寸，通过 `IconSize` 属性控制中心图标大小。

![AtomUI QRcode组件](./images/zoom.webp)

```xaml
<StackPanel Orientation="Vertical">
    <StackPanel Orientation="Horizontal" Spacing="10" Margin="0,0,0,16">
        <atom:Button Icon="{antdicons:AntDesignIconProvider Kind=MinusOutlined}" Command="{Binding SmallerCommand}">Smaller</atom:Button>
        <atom:Button Icon="{antdicons:AntDesignIconProvider Kind=PlusOutlined}" Command="{Binding LargerCommand}">Larger</atom:Button>
    </StackPanel>
    <atom:QRCode Value="https://atomui.net" Icon="avares://AtomUIGallery/Assets/ATOMUI-LOGO.png"
                 Size="{Binding Size}" IconSize="{Binding IconSize}" />
</StackPanel>
```

## 自定义颜色

通过 `Color` 属性自定义二维码前景色，也可以通过 `Background` 属性设置背景色。

![AtomUI QRcode组件](./images/custom-color.png)

```xaml
<StackPanel Orientation="Horizontal" Spacing="10">
    <atom:QRCode Value="https://atomui.net"
                 Color="{DynamicResource {x:Static atom:SharedTokenKey.ColorSuccessText}}" />
    <atom:QRCode Value="https://atomui.net"
                 Color="{DynamicResource {x:Static atom:SharedTokenKey.ColorInfoText}}"
                 Background="{DynamicResource {x:Static atom:SharedTokenKey.ColorBgLayout}}" />
</StackPanel>
```

## 气泡二维码

结合 AtomUI 的 `FlyoutHost` 组件，可以实现鼠标悬停时弹出二维码气泡的功能。设置 `IsBordered="False"` 可以去掉二维码边框，使其在气泡中显示更加美观。

![AtomUI QRcode组件](./images/hover.webp)

```xaml
<atom:FlyoutHost Trigger="Hover">
    <atom:FlyoutHost.Flyout>
        <atom:Flyout>
            <atom:QRCode Value="https://atomui.net" IsBordered="False" />
        </atom:Flyout>
    </atom:FlyoutHost.Flyout>
    <atom:Button ButtonType="Primary">Hover me</atom:Button>
</atom:FlyoutHost>
```

## 公共文件

ViewModel 文件：
```csharp
using System.Reactive;
using AtomUI.Controls;
using AtomUI.Desktop.Controls;
using ReactiveUI;

namespace AtomUIGallery.ShowCases.ViewModels;

public class QRCodeViewModel : ReactiveObject, IRoutableViewModel
{
    public static TreeNodeKey ID = "QRCode";

    public IScreen HostScreen { get; }

    public string UrlPathSegment { get; } = ID.ToString();
    private const double MinSize = 48;
    private const double MaxSize = 300;

    private string _qrCodeInput = "https://atomui.net";

    public string QRCodeInput
    {
        get => _qrCodeInput;
        set => this.RaiseAndSetIfChanged(ref _qrCodeInput, value);
    }

    private int _size = 160;

    public int Size
    {
        get => _size;
        set => this.RaiseAndSetIfChanged(ref _size, value);
    }

    private readonly ObservableAsPropertyHelper<int> _iconSize;

    public int IconSize => _iconSize.Value;

    private List<QRCodeEccLevel> _eccLevels = [];

    public List<QRCodeEccLevel> EccLevels
    {
        get => _eccLevels;
        set => this.RaiseAndSetIfChanged(ref _eccLevels, value);
    }

    public ReactiveCommand<Button, Unit> SmallerCommand { get; }
    public ReactiveCommand<Button, Unit> LargerCommand { get; }

    public QRCodeViewModel(IScreen screen)
    {
        HostScreen = screen;
        var smallerCanExecute = this.WhenAnyValue(x => x.Size, size => size > MinSize);
        var largerCanExecute  = this.WhenAnyValue(x => x.Size, size => size < MaxSize);
        SmallerCommand = ReactiveCommand.Create<Button>(_ => { Size -= 10; }, smallerCanExecute);
        LargerCommand  = ReactiveCommand.Create<Button>(_ => { Size += 10; }, largerCanExecute);
        EccLevels =
        [
            QRCodeEccLevel.L,
            QRCodeEccLevel.M,
            QRCodeEccLevel.Q,
            QRCodeEccLevel.H
        ];
        _iconSize = this.WhenAnyValue(x => x.Size, size => size / 4).ToProperty(this, x => x.IconSize);
    }
}
```
