# 动态支持

### 设定loading

本质上是通过初始化 `Message` 类时设定 `type` 为 `MessageType.Loading`。

![AtomUI Message组件](./images/message-with-loading-indicator.webp)

axaml文件：
```xaml
<atom:Button ButtonType="Default"
             Click="ShowLoadingMessage">
    Display a loading indicator
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

参考本文档中code-behind文件中的 `ShowSequentialMessage` 方法即可，本质上是在初始化 `Message` 类的时候指定 `expiration` 与 `onClose`。

![AtomUI Message组件](./images/callback.webp)

```xaml
<atom:Button ButtonType="Default"
             Click="ShowSequentialMessage">
    Display a loading indicator
</atom:Button>
```