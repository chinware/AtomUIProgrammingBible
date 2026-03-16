# 快速入门

### 基础配置条件

* Nuget安装Avalonia
* Nuget安装AtomUI

### 基本用法

最基础的面包屑导航用法。通过声明多个 `atom:BreadcrumbItem` 构建路径层级。`NavigateContext` 属性用于在路径节点上携带开发者自定义的扩展数据，供导航事件使用。

![AtomUI Breadcrumb组件](./images/basic.png)

```xaml
<StackPanel>
    <atom:Breadcrumb>
        <atom:BreadcrumbItem>Home</atom:BreadcrumbItem>
        <atom:BreadcrumbItem NavigateContext="#">Application Center</atom:BreadcrumbItem>
        <atom:BreadcrumbItem NavigateContext="#">Application List</atom:BreadcrumbItem>
        <atom:BreadcrumbItem>An Application</atom:BreadcrumbItem>
    </atom:Breadcrumb>
</StackPanel>
```

### 带图标的面包屑

通过设定 `atom:BreadcrumbItem` 的 `Icon` 属性可在路径节点中显示图标。图标来源于 AtomUI 的内置图标库，使用 `IconProvider` 标记扩展指定图标类型。

![AtomUI Breadcrumb组件](./images/with-icon.png)

```xaml
<StackPanel>
    <atom:Breadcrumb>
        <atom:BreadcrumbItem Icon="{atom:IconProvider Kind=HomeOutlined}"></atom:BreadcrumbItem>
        <atom:BreadcrumbItem Icon="{atom:IconProvider Kind=UserOutlined}" NavigateContext="#">Application List</atom:BreadcrumbItem>
        <atom:BreadcrumbItem>Application</atom:BreadcrumbItem>
    </atom:Breadcrumb>
</StackPanel>
```

### 自定义分隔符（全局）

通过给 `atom:Breadcrumb` 组件的 `Separator` 属性设定一个值，可以统一修改整个面包屑导航条中的分隔符样式。

![AtomUI Breadcrumb组件](./images/configure-separator.png)

```xaml
<StackPanel>
    <atom:Breadcrumb Separator=">">
        <atom:BreadcrumbItem>Home</atom:BreadcrumbItem>
        <atom:BreadcrumbItem NavigateContext="#">Application Center</atom:BreadcrumbItem>
        <atom:BreadcrumbItem NavigateContext="#">Application List</atom:BreadcrumbItem>
        <atom:BreadcrumbItem>An Application</atom:BreadcrumbItem>
    </atom:Breadcrumb>
</StackPanel>
```

### 自定义分隔符（单项）

在某些场景下仅需修改面包屑导航条中某一项的分隔符，此时可以通过给对应 `atom:BreadcrumbItem` 的 `Separator` 属性设定值来单独修改。

![AtomUI Breadcrumb组件](./images/configuire-single-separator.png)

```xaml
<StackPanel>
    <atom:Breadcrumb>
        <atom:BreadcrumbItem Separator=":">Location</atom:BreadcrumbItem>
        <atom:BreadcrumbItem NavigateContext="#">Application Center</atom:BreadcrumbItem>
        <atom:BreadcrumbItem NavigateContext="#">Application List</atom:BreadcrumbItem>
        <atom:BreadcrumbItem>An Application</atom:BreadcrumbItem>
    </atom:Breadcrumb>
</StackPanel>
```

### 路径参数与导航事件

通过 `NavigateContext` 属性可以在路径节点上携带任意自定义参数。当用户点击路径节点时，`NavigateRequest` 事件会被触发，开发者可以在事件处理函数中获取被点击节点的 `NavigateContext` 值来执行相应的导航逻辑。

![AtomUI Breadcrumb组件](./images/with-param.png)

```xaml
<StackPanel>
    <atom:Breadcrumb NavigateRequest="HandleNavigateRequest">
        <atom:BreadcrumbItem>Users</atom:BreadcrumbItem>
        <atom:BreadcrumbItem NavigateContext="Param(1)">Param</atom:BreadcrumbItem>
    </atom:Breadcrumb>
</StackPanel>
```

事件处理代码：

```csharp
private void HandleNavigateRequest(object? sender, BreadcrumbNavigateEventArgs eventArgs)
{
    _messageManager?.Show(new Message(
        $"Navigate context: {eventArgs.BreadcrumbItem.NavigateContext}"
    ));
}
```

### 通过 ItemTemplate 动态生成

通过 `ItemTemplate` 属性配合 `ItemsSource` 绑定，可以以 MVVM 方式动态生成面包屑导航条。这是最常用的使用方式，便于通过数据驱动来动态修改导航路径。

![AtomUI Breadcrumb组件](./images/generate.png)

XAML 文件：

```xaml
<StackPanel>
    <atom:Breadcrumb ItemsSource="{Binding BreadcrumbItems}"
                     x:DataType="viewModels:BreadcrumbViewModel">
        <atom:Breadcrumb.ItemTemplate>
            <DataTemplate>
                <TextBlock Text="{Binding Content}"/>
            </DataTemplate>
        </atom:Breadcrumb.ItemTemplate>
    </atom:Breadcrumb>
</StackPanel>
```

Code-behind 文件：

```csharp
using AtomUI.Controls;
using AtomUI.Controls.Primitives;
using AtomUIGallery.ShowCases.ViewModels;
using Avalonia;
using Avalonia.Controls;
using Avalonia.ReactiveUI;
using ReactiveUI;

public partial class BreadcrumbShowCase : ReactiveUserControl<BreadcrumbViewModel>
{
    private WindowMessageManager? _messageManager;
    public BreadcrumbShowCase()
    {
        InitializeComponent();
        this.WhenActivated(disposables =>
        {
            if (DataContext is BreadcrumbViewModel viewModel)
            {
                viewModel.BreadcrumbItems = [
                    new BreadcrumbItemData()
                    {
                        Separator = ":",
                        Content = "Location"
                    },
                    new BreadcrumbItemData()
                    {
                        NavigateContext = "#",
                        Content = "Application Center"
                    },
                    new BreadcrumbItemData()
                    {
                        NavigateContext = "#",
                        Content         = "Application List"
                    },
                    new BreadcrumbItemData()
                    {
                        Content         = "An Application"
                    }
                ];
            }
        });
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

    private void HandleNavigateRequest(object? sender, BreadcrumbNavigateEventArgs eventArgs)
    {
        _messageManager?.Show(new Message(
            $"Navigate context: {eventArgs.BreadcrumbItem.NavigateContext}"
        ));
    }
}
```

ViewModel 文件：

```csharp
using AtomUI.Controls;
using ReactiveUI;

public class BreadcrumbViewModel : ReactiveObject, IRoutableViewModel
{
    public const string ID = "Breadcrumb";

    public IScreen HostScreen { get; }

    public string UrlPathSegment { get; } = ID;

    private List<BreadcrumbItemData> _breadcrumbItems = [];

    public List<BreadcrumbItemData> BreadcrumbItems
    {
        get => _breadcrumbItems;
        set => this.RaiseAndSetIfChanged(ref _breadcrumbItems, value);
    }

    public BreadcrumbViewModel(IScreen screen)
    {
        HostScreen = screen;
    }
}
```
