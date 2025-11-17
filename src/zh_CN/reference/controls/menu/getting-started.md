# 快速入门

### 基础配置条件

* Nuget安装Avalonia
* Nuget安装AtomUI

### 基础用法

`Message` 组件使用是需要基于一个现有的组件，比如 `Button` 组件。通过点击 `Button` 组件，会弹出一个 `Message` 组件。

本示例中，通过点击按钮后，`ShowSimpleMessage` 会继续处理后续流程；当然，更推荐使用 `Command` 来处理这个事件。

![AtomUI Message组件](./images/basic.webp)

axaml文件：
```axaml
<atom:Button ButtonType="Primary"
             Click="ShowSimpleMessage">
    Display normal message
</atom:Button>
```

code-behind文件：
```csharp
using AtomUI.Controls;
using AtomUIGallery.ShowCases.ViewModels;
using Avalonia;
using Avalonia.Controls;
using Avalonia.Interactivity;
using Avalonia.ReactiveUI;
using ReactiveUI;

namespace Your-NameSpace;

public partial class MessageShowCase : ReactiveUserControl<MessageViewModel>
{
    private WindowMessageManager? _messageManager;
    public MessageShowCase()
    {
        this.WhenActivated(disposables => { });
        InitializeComponent();
    }
    
    protected override void OnAttachedToVisualTree(VisualTreeAttachmentEventArgs e)
    {
        base.OnAttachedToVisualTree(e);
        var topLevel = TopLevel.GetTopLevel(this);
        _messageManager = new WindowMessageManager(topLevel)
        {
            MaxItems = 10
        };
    }

    private void ShowSimpleMessage(object? sender, RoutedEventArgs e)
    {
        _messageManager?.Show(new Message(
            "Hello, AtomUI/Avalonia!"
        ));
    }

    private void ShowInfoMessage(object? sender, RoutedEventArgs e)
    {
        _messageManager?.Show(new Message(
            type: MessageType.Information,
            content: "This is a information message."
        ));
    }

    private void ShowSuccessMessage(object? sender, RoutedEventArgs e)
    {
        _messageManager?.Show(new Message(
            type: MessageType.Success,
            content: "This is a success message."
        ));
    }

    private void ShowWarningMessage(object? sender, RoutedEventArgs e)
    {
        _messageManager?.Show(new Message(
            type: MessageType.Warning,
            content: "This is a warning message."
        ));
    }

    private void ShowErrorMessage(object? sender, RoutedEventArgs e)
    {
        _messageManager?.Show(new Message(
            type: MessageType.Error,
            content: "This is a error message."
        ));
    }

    private void ShowLoadingMessage(object? sender, RoutedEventArgs e)
    {
        _messageManager?.Show(new Message(
            type: MessageType.Loading,
            content: "Action in progress..."
        ));
    }

    private void ShowSequentialMessage(object? sender, RoutedEventArgs e)
    {
        _messageManager?.Show(new Message(
            type: MessageType.Loading,
            content: "Action in progress...",
            expiration: TimeSpan.FromSeconds(2.5),
            onClose: () =>
            {
                _messageManager?.Show(new Message(
                    type: MessageType.Success,
                    expiration: TimeSpan.FromSeconds(2.5),
                    content: "Loading finished",
                    onClose: () =>
                    {
                        _messageManager?.Show(new Message(
                            type: MessageType.Information,
                            expiration: TimeSpan.FromSeconds(2.5),
                            content: "Loading finished"
                        ));
                    }
                ));
            }
        ));
    }
}
```

view-model文件：
```csharp
using ReactiveUI;
namespace Your-NameSpace;
public class MessageViewModel : ReactiveObject, IRoutableViewModel
{
    public const string ID = "Message";
    
    public IScreen HostScreen { get; }
    
    public string UrlPathSegment { get; } = ID;

    public MessageViewModel(IScreen screen)
    {
        HostScreen = screen;
    }
}
```

### 样式设定

同上一个示例，你需要通过查看code-behind文件中的不同事件来设定不同样式的 `Message`。本质上是通过初始化 `Message` 类时设定 `type` 即可。

以下是可选的 `type` 值：
* MessageType.Information
* MessageType.Success
* MessageType.Warning
* MessageType.Error
* MessageType.Loading

![AtomUI Message组件](./images/types.webp)

```axaml
<StackPanel Orientation="Horizontal" Spacing="10">
    <atom:Button ButtonType="Default"
                 Click="ShowSuccessMessage">
        Success
    </atom:Button>
    <atom:Button ButtonType="Default"
                 Click="ShowInfoMessage">
        Info
    </atom:Button>
    <atom:Button ButtonType="Default"
                 Click="ShowWarningMessage">
        Warning
    </atom:Button>
    <atom:Button ButtonType="Default"
                 Click="ShowErrorMessage">
        Error
    </atom:Button>
</StackPanel>
```