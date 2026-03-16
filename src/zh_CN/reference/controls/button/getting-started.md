# Button 快速入门

## 前置条件

- NuGet 安装 `Avalonia`
- NuGet 安装 `AtomUI`

## 基础用法

通过 `ButtonType` 属性控制按钮的视觉风格。

![AtomUI Button 基础用法](./images/basic-button.webp)

```xaml
<atom:Button ButtonType="Primary">Primary Button</atom:Button>
<atom:Button>Default Button</atom:Button>
<atom:Button ButtonType="Dashed">Dashed Button</atom:Button>
<atom:Button ButtonType="Text">Text Button</atom:Button>
<atom:Button ButtonType="Link">Link Button</atom:Button>
```

| ButtonType | 说明 |
|---|---|
| `Primary` | 主要操作按钮，页面中建议只有一个 |
| `Default` | 默认按钮，用于次要操作 |
| `Dashed` | 虚线边框按钮，常用于添加操作 |
| `Text` | 文本按钮，无边框无背景，用于最轻量的操作 |
| `Link` | 链接按钮，类似超链接的视觉效果 |

## 按钮形状

通过 `Shape` 属性设置按钮的几何形状。

![AtomUI Button 形状](./images/button-shape.webp)

```xaml
<!-- 默认形状（圆角矩形） -->
<atom:Button ButtonType="Primary">Primary</atom:Button>

<!-- 胶囊形 -->
<atom:Button ButtonType="Primary" Shape="Round">Primary</atom:Button>

<!-- 圆形（适合纯图标按钮） -->
<atom:Button ButtonType="Primary" Shape="Circle"
             Icon="{atom:IconProvider Kind=SearchOutlined}" />
```

## 按钮尺寸

通过 `SizeType` 属性控制按钮大小，可选值为 `Large`、`Middle`（默认）、`Small`。

![AtomUI Button 尺寸](./images/button-size.webp)

```xaml
<atom:Button ButtonType="Primary" SizeType="Large">Large</atom:Button>
<atom:Button ButtonType="Primary">Middle（默认）</atom:Button>
<atom:Button ButtonType="Primary" SizeType="Small">Small</atom:Button>
```

配合数据绑定可实现动态切换尺寸：

```xaml
<atom:Button ButtonType="Primary" SizeType="{Binding ButtonSizeType}">
    Primary
</atom:Button>
```

## 图标按钮

通过 `Icon` 属性设置按钮图标，图标来源于 AtomUI 内置的 AntDesign 图标库。

![AtomUI Button 图标](./images/icon-button.webp)

```xaml
<!-- 图标 + 文字 -->
<atom:Button ButtonType="Primary" Icon="{atom:IconProvider Kind=SearchOutlined}">
    Search
</atom:Button>

<!-- 纯图标按钮（圆形） -->
<atom:Button ButtonType="Primary" Shape="Circle"
             Icon="{atom:IconProvider Kind=SearchOutlined}" />

<!-- 纯图标按钮（胶囊形） -->
<atom:Button ButtonType="Primary" Shape="Round"
             Icon="{atom:IconProvider Kind=SearchOutlined}" />
```

## 危险按钮

设置 `IsDanger="True"` 标识破坏性或不可逆操作，按钮会以红色系呈现。

![AtomUI Button 危险](./images/danger-button.webp)

```xaml
<atom:Button ButtonType="Primary" IsDanger="True">Delete</atom:Button>
<atom:Button ButtonType="Default" IsDanger="True">Remove</atom:Button>
<atom:Button ButtonType="Text" IsDanger="True">Delete</atom:Button>
<atom:Button ButtonType="Link" IsDanger="True">Delete</atom:Button>
```

## 幽灵按钮

设置 `IsGhost="True"` 使按钮背景透明，适用于深色或彩色背景。

![AtomUI Button 幽灵](./images/ghost-button.webp)

```xaml
<Border Background="rgb(190, 200, 200)" Padding="16">
    <WrapPanel>
        <atom:Button ButtonType="Primary" IsGhost="True">Primary</atom:Button>
        <atom:Button ButtonType="Default" IsGhost="True">Default</atom:Button>
        <atom:Button ButtonType="Primary" IsDanger="True" IsGhost="True">
            Danger
        </atom:Button>
    </WrapPanel>
</Border>
```

## 加载状态

设置 `IsLoading="True"` 显示加载动画，按钮在加载期间会自动禁用交互。适用于提交表单、发起请求等需要等待的场景。

![AtomUI Button 加载](./images/load-button.webp)

```xaml
<!-- 静态加载状态 -->
<atom:Button ButtonType="Primary" IsLoading="True">Loading</atom:Button>

<!-- 点击后动态切换加载状态 -->
<atom:Button ButtonType="Primary" Click="HandleLoadingBtnClick">
    Click me!
</atom:Button>
```

Code-behind 实现：

```csharp
public void HandleLoadingBtnClick(object? sender, RoutedEventArgs args)
{
    if (sender is Button button)
    {
        button.IsLoading = true;
        Dispatcher.UIThread.InvokeAsync(async () =>
        {
            await Task.Delay(TimeSpan.FromSeconds(3));
            button.IsLoading = false;
        });
    }
}
```

## 禁用状态

设置 `IsEnabled="False"` 禁用按钮，所有按钮类型均支持禁用态。

![AtomUI Button 禁用](./images/disabled-button.webp)

```xaml
<atom:Button ButtonType="Primary" IsEnabled="False">Primary (disabled)</atom:Button>
<atom:Button ButtonType="Default" IsEnabled="False">Default (disabled)</atom:Button>
<atom:Button ButtonType="Text" IsEnabled="False">Text (disabled)</atom:Button>
<atom:Button ButtonType="Link" IsEnabled="False">Link (disabled)</atom:Button>
```

## 块状按钮

设置 `HorizontalAlignment="Stretch"` 使按钮宽度撑满父容器，适用于移动端或表单场景。

![AtomUI Button 块状](./images/block-button.webp)

```xaml
<StackPanel Orientation="Vertical" Spacing="8">
    <atom:Button ButtonType="Primary" HorizontalAlignment="Stretch">
        Primary
    </atom:Button>
    <atom:Button ButtonType="Default" HorizontalAlignment="Stretch">
        Default
    </atom:Button>
</StackPanel>
```
