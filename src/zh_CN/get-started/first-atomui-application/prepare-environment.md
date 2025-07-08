# 环境准备
我们文档使用的操作系统环境如下：

1. Ubuntu 24.04 操作系统
2. Avalonia 11.3.2
3. JetBrains Rider 2025.1.4

开发 IDE 我们强烈推荐 JetBrains Rider

JetBrains Rider IDE 自 2020.3 起内置对 Avalonia XAML 的支持，包括对 Avalonia 特定 XAML 功能和自定义代码检查的卓越支持。现在 Rider 可供个人免费使用，我们强烈推荐它作为 AtomUI 开发的主要 IDE，尤其推荐 macOS 和 Linux 开发者使用。

Rider 为 Avalonia 提供最完整、最精致的开发体验，其内置功能包括：

1. 高级 XAML 补全和导航
2. 丰富的代码分析和快速修复
3. 全面的调试工具
4. 内置性能分析

因为 .NET 和 Avalonia 的跨平台能力非常强，其他平台基本一样，我们就不在文章中赘述了。

AtomUI OSS 是 Avalonia 的控件库，所以我们为了快速创建项目结构，推荐安装 Avalonia Template

```bash
dotnet new install Avalonia.Templates
```

完成安装之后可以运行下面命名进行确认

```bash
dotnet new list
```

如果安装过程没有问题，您应该看到已安装的 Avalonia 模板：
```
Success: Avalonia.Templates::11.3.2 installed the following templates:
Template Name       Short Name                 Language  Tags
------------------  -------------------------  --------  -----------------------------------------
Avalonia .NET App   avalonia.app               [C#],F#   Desktop/Xaml/Avalonia/Windows/Linux/macOS
Avalonia .NET M...  avalonia.mvvm              [C#],F#   Desktop/Xaml/Avalonia/Windows/Linux/macOS
Avalonia Cross ...  avalonia.xplat             [C#],F#   Desktop/Xaml/Avalonia/Browser/Mobile     
Avalonia Resour...  avalonia.resource                    Desktop/Xaml/Avalonia/Windows/Linux/macOS
Avalonia Styles     avalonia.styles                      Desktop/Xaml/Avalonia/Windows/Linux/macOS
Avalonia Templa...  avalonia.templatedcontrol  [C#],F#   Desktop/Xaml/Avalonia/Windows/Linux/macOS
Avalonia UserCo...  avalonia.usercontrol       [C#],F#   Desktop/Xaml/Avalonia/Windows/Linux/macOS
Avalonia Window     avalonia.window            [C#],F#   Desktop/Xaml/Avalonia/Windows/Linux/macOS
```