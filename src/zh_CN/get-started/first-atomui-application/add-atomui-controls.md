# 为项目添加 AtomUI 控件

当目前为止，我们还没有使用任何 AtomUI 控件库的功能，我们需要引入 AtomUI 库
打开 `AtomUIProgressApp.csproj` 文件，引入 AtomUI 包

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
        <PackageReference Include="AtomUI" Version="0.0.6-build.1"/>
        <PackageReference Include="Avalonia.Desktop" Version="11.3.2"/>
        <PackageReference Include="Avalonia.Fonts.Inter" Version="11.3.2"/>
        <PackageReference Include="Avalonia.Diagnostics" Version="11.3.2">
            <IncludeAssets Condition="'$(Configuration)' != 'Debug'">None</IncludeAssets>
            <PrivateAssets Condition="'$(Configuration)' != 'Debug'">All</PrivateAssets>
        </PackageReference>
    </ItemGroup>
</Project>
```
增加 AtomUI 包引用后，我们需要启动他，您需要打开 `Program.cs` 文件， 将现有的代码修改成如下代码：

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
            .LogToTrace();
        // 创建主题管理器构造对象
        var themeBuilder = builder.CreateThemeManagerBuilder();
        themeBuilder.UseCultureInfo(new CultureInfo(LanguageCode.en_US));
        themeBuilder.UseTheme(ThemeManager.DEFAULT_THEME_ID);
        themeBuilder.UseOSSControls(); // 添加 OSS 控件库
        
        return builder.UseAtomUI(themeBuilder);
    }
}
```