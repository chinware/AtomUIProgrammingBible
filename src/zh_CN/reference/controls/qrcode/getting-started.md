# QRcode 快速入门

### 基础配置条件

* Nuget安装Avalonia
* Nuget安装AtomUI
* 文档末尾有公共view-model文件

### 基础用法

这是最基础的用法，其中的Binding部分请参考本页末尾的view-model文件内容。

![AtomUI QRcode组件](./images/basic.webp)

```xaml
<StackPanel Orientation="Vertical">
    <atom:QRCode Value="{Binding QRCodeInput}" />
    <atom:LineEdit Text="{Binding QRCodeInput}" Margin="0,20,0,0" />
    <ListBox>
        <ListBox.ItemTemplate></ListBox.ItemTemplate>
    </ListBox>
</StackPanel>
```

### 自定义图标

可以通过 `Avalonia` 的 `avares://` 为二维码指定一个icon。

![AtomUI QRcode组件](./images/with-icon.png)

```xaml
<atom:QRCode Value="https://atomui.net" Icon="avares://AtomUIGallery/Assets/ATOMUI-LOGO.png" />
```

### 内置状态

通过 `Status` 属性可以控制二维码的显示状态，根据 `MVVM` 原则，开发者需要将 `Status` 绑定到一个属性上。

![AtomUI QRcode组件](./images/status.webp)

```xaml
<atom:QRCode Value="https://atomui.net" Status="Loading" />
<atom:QRCode Value="https://atomui.net" Status="Expired" />
<atom:QRCode Value="https://atomui.net" Status="Scanned" />
```

### 设定纠错比例

![AtomUI QRcode组件](./images/ecc.webp)

```xaml
<StackPanel Orientation="Vertical" Spacing="10">
    <atom:QRCode Value="https://gw.alipayobjects.com/zos/rmsportal/KDpgvguMpGfqaHPjicRK.svg"
                 EccLevel="{Binding #EccLevel.SelectedItem}" />
    <atom:Segmented Name="EccLevel" ItemsSource="{Binding EccLevels}" />
</StackPanel>
```

### 公共文件

view-model文件：
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