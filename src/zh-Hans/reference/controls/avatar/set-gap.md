# 内边距

字符型的头像，当字符串较长时，字体大小可以根据头像宽度自动调整，也可使用通过事件来设置字符距离左右两侧边界单位像素。

![AtomUI Avatar](./images/autoset.webp)

axaml文件：
```xaml
<StackPanel Orientation="Horizontal" Spacing="10">
    <atom:Avatar Background="{Binding AvatarBackground}"
                 Gap="{Binding AvatarGap}"
                 SizeType="Large"
                 Text="{Binding AvatarText}"/>
    <atom:Button Name="ChangeUserButton"
                 ButtonType="Default"
                 SizeType="Small"
                 VerticalAlignment="Center">
        ChangeUser
    </atom:Button>
    <atom:Button Name="ChangeGapButton"
                 ButtonType="Default"
                 SizeType="Small"
                 VerticalAlignment="Center">
        ChangeGap
    </atom:Button>
</StackPanel>
```

code-behind文件：
```csharp
using AtomUIGallery.ShowCases.ViewModels;
using Avalonia.ReactiveUI;
using ReactiveUI;
namespace AtomUIGallery.ShowCases.Views;

public partial class AvatarShowCase : ReactiveUserControl<AvatarViewModel>
{
    public AvatarShowCase()
    {
        InitializeComponent();
        this.WhenActivated(disposables =>
        {
            if (DataContext is AvatarViewModel viewModel)
            {
                ChangeUserButton.Click += viewModel.HandleChangeUserClicked;
                ChangeGapButton.Click  += viewModel.HandleChangeGapClicked;
            }
        });
    }
}
```

view-model文件：
```csharp
using System.Reactive.Disposables;
using ReactiveUI;

namespace AtomUIGallery.ShowCases.ViewModels;

public class AvatarViewModel : ReactiveObject, IRoutableViewModel, IActivatableViewModel
{
    public const string ID = "Avatar";
    public ViewModelActivator Activator { get; }
    public IScreen HostScreen { get; }

    public string UrlPathSegment { get; } = ID;

    private string? _avatarText;

    public string? AvatarText
    {
        get => _avatarText;
        set => this.RaiseAndSetIfChanged(ref _avatarText, value);
    }

    private double? _avatarGap;

    public double? AvatarGap
    {
        get => _avatarGap;
        set => this.RaiseAndSetIfChanged(ref _avatarGap, value);
    }

    private string? _avatarBackground;

    public string? AvatarBackground
    {
        get => _avatarBackground;
        set => this.RaiseAndSetIfChanged(ref _avatarBackground, value);
    }

    private int _textCurrentIndex = 0;
    private int _gapCurrentIndex = 0;

    private List<string> _userList;
    private List<string> _colorList;
    private List<double> _gapList;

    public AvatarViewModel(IScreen screen)
    {
        Activator  = new ViewModelActivator();
        HostScreen = screen;
        _userList  = ["U", "Lucy", "Tom", "Edward"];
        _colorList = ["#f56a00", "#7265e6", "#ffbf00", "#00a2ae"];
        _gapList   = [4, 3, 2, 1];
        this.WhenActivated((CompositeDisposable disposables) =>
        {
            SetupAvatarText();
            SetupAvatarGap();
        });
    }

    private void SetupAvatarText()
    {
        var index = (_textCurrentIndex++) % 4;
        AvatarText       = _userList[index];
        AvatarBackground = _colorList[index];
    }

    private void SetupAvatarGap()
    {
        var index = (_gapCurrentIndex++) % 4;
        AvatarGap = _gapList[index];
    }

    public void HandleChangeUserClicked(object? sender, EventArgs e)
    {
        SetupAvatarText();
    }

    public void HandleChangeGapClicked(object? sender, EventArgs e)
    {
        SetupAvatarGap();
    }
}
```