# 为项目添加 AtomUI 控件

当目前为止，我们还没有使用任何 `AtomUI` 控件库的功能，我们需要引入 `AtomUI` 库
打开 `AtomUIProgressApp.csproj` 文件，引入 `AtomUI` 包

```xaml
<Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
        <OutputType>WinExe</OutputType>
        <TargetFramework>net9.0</TargetFramework>
        <Nullable>enable</Nullable>
        <BuiltInComInteropSupport>true</BuiltInComInteropSupport>
        <ApplicationManifest>app.manifest</ApplicationManifest>
        <AvaloniaUseCompiledBindingsByDefault>true</AvaloniaUseCompiledBindingsByDefault>
    </PropertyGroup>

    <ItemGroup>
        <PackageReference Include="AtomUI" Version="0.0.6-build.4"/>
        <PackageReference Include="Avalonia.Desktop" Version="11.3.2"/>
        <PackageReference Include="Avalonia.Diagnostics" Version="11.3.2">
            <IncludeAssets Condition="'$(Configuration)' != 'Debug'">None</IncludeAssets>
            <PrivateAssets Condition="'$(Configuration)' != 'Debug'">All</PrivateAssets>
        </PackageReference>
    </ItemGroup>
</Project>
```
增加 `AtomUI` 包引用后，我们需要启动他，您需要打开 `Program.cs` 文件， 将现有的代码修改成如下代码：

> [!NOTE]
> 我们这里主要是用代码注入了 `AtomUI` 相关的样式资源，大大简化了使用成本，开发者不需要在 `axaml` 文件中自己手动引入了资源了

```csharp
using Avalonia;
using System;
namespace AtomUIProgressApp;
class Program
{
    [STAThread]
    public static void Main(string[] args) => BuildAvaloniaApp()
        .StartWithClassicDesktopLifetime(args);
    public static AppBuilder BuildAvaloniaApp()
    {
        var builder = AppBuilder.Configure<App>()
            .UsePlatformDetect()
            .WithInterFont()
            .With(new Win32PlatformOptions())
            .LogToTrace();
        var themeBuilder = builder.CreateThemeManagerBuilder();
        themeBuilder.UseCultureInfo(new CultureInfo(LanguageCode.en_US));
        themeBuilder.UseTheme(ThemeManager.DEFAULT_THEME_ID);
        themeBuilder.UseOSSControls();
        return builder.UseAtomUI(themeBuilder);
    }
}
```

接下来，我们开始定义窗口本身，我们这个项目只要是在窗口上有两个进度条，然后有增加和减少进度两个按钮控制进度当前值，我们窗口定义在文件 `MainWindow.axaml` 中。

在代码中，如果要引入 `AtomUI` 控件库，我们需要引入 `AtomUI` 命名空间 `xmlns:atom="using:AtomUI.Controls"`，同时我们为了简化操作 `DataContext` 设置成了 `atom:Window` 本身。
可以看出 `AtomUI` 在使用上还是比较清晰的，唯一不同的就是需要带上我们自己的命名空间前缀 `atom`。
```xaml
<atom:Window xmlns="https://github.com/avaloniaui"
             xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
             xmlns:atom="using:AtomUI.Controls"
             xmlns:local="using:AtomUIProgressApp"
             x:Class="AtomUIProgressApp.MainWindow"
             Title="AtomUIProgressApp"
             Width="800"
             Height="600"
             x:DataType="local:MainWindow"
             WindowState="Normal"
             WindowStartupLocation="CenterScreen">
    <Panel>
        <StackPanel Orientation="Vertical" Spacing="10" HorizontalAlignment="Center" VerticalAlignment="Center">
            <atom:ProgressBar Value="{Binding ProgressValue}" Minimum="0" Maximum="100" 
                              HorizontalAlignment="Center"
                              Width="400"/>
            <atom:CircleProgress Value="{Binding ProgressValue}" Minimum="0" Maximum="100"
                                 HorizontalAlignment="Center"/>
            <StackPanel Orientation="Horizontal" Spacing="10" HorizontalAlignment="Center">
                <atom:Button Click="HandleSubBtnClicked">Sub</atom:Button>
                <atom:Button Click="HandleAddBtnClicked">Add</atom:Button>
            </StackPanel>
        </StackPanel>
    </Panel>
</atom:Window>
```
在文件 `MainWindow.axaml.cs` 中，我们定义一个显示当前进度值的属性和两个按钮的事件处理函数，代码非常简单，我们就不再赘述功能了，唯一需要注意的是我们这里将 `DataContext` 设置成了自身。

```csharp
using System;
using AtomUI.Controls;
using Avalonia;
using Avalonia.Interactivity;

namespace AtomUIProgressApp;

public partial class MainWindow : Window
{
    public static readonly StyledProperty<double> ProgressValueProperty =
        AvaloniaProperty.Register<MainWindow, double>(nameof(ProgressValue), 30);

    public double ProgressValue
    {
        get => GetValue(ProgressValueProperty);
        set => SetValue(ProgressValueProperty, value);
    }
    
    protected override Type StyleKeyOverride { get; } = typeof(Window);
    
    public MainWindow()
    {
        InitializeComponent();
        DataContext = this;
    }

    private void HandleAddBtnClicked(object? sender, RoutedEventArgs e)
    {
        var value = ProgressValue;
        value         += 10;
        ProgressValue =  Math.Min(value, 100);
    }
    
    private void HandleSubBtnClicked(object? sender, RoutedEventArgs e)
    {
        var value = ProgressValue;
        value         -= 10;
        ProgressValue =  Math.Max(value, 0);
    }
}
```

好见证奇迹的时刻到了，我们编译运行项目，您将看到下面的效果。

![AtomUIProgressApp](./images/atomui-progress-app-run.png)

好了，恭喜您已经完成了第一个 `AtomUI` 应用程序了， 我们快速开始教程就结束了，接下来该您继续探索 `AtomUI` 去创造属于您的无限可能的应用了。加油，开发者！