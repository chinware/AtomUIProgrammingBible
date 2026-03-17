# Carousel 快速入门

## 前置条件

- NuGet 安装 `Avalonia`
- NuGet 安装 `AtomUI`
- 本页文档末尾有公共样式代码与公共 code-behind 代码

## 基础用法

最简单的轮播组件用法，使用 `CarouselPage` 作为每一页的容器。通过 `SelectedIndex` 属性可设置默认显示的页面。

![AtomUI Carousel组件](./images/basic.webp)

```xaml
<atom:Carousel SelectedIndex="2">
    <atom:CarouselPage>1</atom:CarouselPage>
    <atom:CarouselPage>2</atom:CarouselPage>
    <atom:CarouselPage>3</atom:CarouselPage>
    <atom:CarouselPage>4</atom:CarouselPage>
</atom:Carousel>
```

## 分页指示器位置

通过 `PaginationPosition` 属性指定分页指示器的位置，支持 `Top`、`Bottom`、`Left`、`Right` 四个方向。

![AtomUI Carousel组件](./images/position.webp)

```xaml
<StackPanel Orientation="Vertical" Spacing="20">
    <StackPanel Orientation="Horizontal" Spacing="5">
        <atom:TextBlock VerticalAlignment="Center">Pagination Position:</atom:TextBlock>
        <atom:OptionButtonGroup ButtonStyle="Outline" Name="PositionOptionGroup">
            <atom:OptionButton>Top</atom:OptionButton>
            <atom:OptionButton IsChecked="True">Bottom</atom:OptionButton>
            <atom:OptionButton>Left</atom:OptionButton>
            <atom:OptionButton>Right</atom:OptionButton>
        </atom:OptionButtonGroup>
    </StackPanel>

    <atom:Carousel PaginationPosition="{Binding PaginationPosition}">
        <atom:CarouselPage>1</atom:CarouselPage>
        <atom:CarouselPage>2</atom:CarouselPage>
        <atom:CarouselPage>3</atom:CarouselPage>
        <atom:CarouselPage>4</atom:CarouselPage>
    </atom:Carousel>

</StackPanel>
```

## 自动轮播

将 `IsAutoPlay` 设为 `True` 即可开启自动轮播。`IsInfinite` 默认为 `True`，表示播放到最后一页后会自动跳转回第一页继续循环；设为 `False` 则在最后一页停止。通过 `AutoPlaySpeed` 属性可控制每页的停留时间，默认为 3000 毫秒。

![AtomUI Carousel组件](./images/auto-play.webp)

```xaml
<atom:Carousel IsAutoPlay="True" IsInfinite="False">
    <atom:CarouselPage>1</atom:CarouselPage>
    <atom:CarouselPage>2</atom:CarouselPage>
    <atom:CarouselPage>3</atom:CarouselPage>
    <atom:CarouselPage>4</atom:CarouselPage>
</atom:Carousel>
```

## 淡入淡出效果

`TransitionEffect` 属性用于设置页面切换的过渡效果，支持 `Scroll`（滚动，默认）和 `Fade`（淡入淡出）两种效果。

![AtomUI Result组件](./images/fade-in.webp)

```xaml
<atom:Carousel TransitionEffect="Fade">
    <atom:CarouselPage Background="#B3001B">1</atom:CarouselPage>
    <atom:CarouselPage Background="#255C99">2</atom:CarouselPage>
    <atom:CarouselPage Background="#262626">3</atom:CarouselPage>
    <atom:CarouselPage Background="#CCAD8F">4</atom:CarouselPage>
</atom:Carousel>
```

## 导航箭头

将 `IsShowNavButtons` 设为 `True`，可在轮播区域两侧显示左右切换箭头，方便用户手动翻页。

![AtomUI Carousel组件](./images/with-arrow.webp)

```xaml
<StackPanel Orientation="Vertical" Spacing="10">
    <atom:Carousel IsShowNavButtons="True">
        <atom:CarouselPage>1</atom:CarouselPage>
        <atom:CarouselPage>2</atom:CarouselPage>
        <atom:CarouselPage>3</atom:CarouselPage>
        <atom:CarouselPage>4</atom:CarouselPage>
    </atom:Carousel>
    <atom:Carousel PaginationPosition="Left" IsShowNavButtons="True" IsInfinite="False">
        <atom:CarouselPage>1</atom:CarouselPage>
        <atom:CarouselPage>2</atom:CarouselPage>
        <atom:CarouselPage>3</atom:CarouselPage>
        <atom:CarouselPage>4</atom:CarouselPage>
    </atom:Carousel>
</StackPanel>
```

## 播放进度展示

当自动轮播开启时，`IsShowTransitionProgress` 属性可以在分页指示器上展示当前页面的播放进度条，直观地告知用户页面切换的剩余时间。

![AtomUI Carousel组件](./images/progress-dot.webp)

```xaml
<StackPanel Orientation="Vertical" Spacing="10">
    <atom:Carousel IsShowTransitionProgress="True" IsAutoPlay="True">
        <atom:CarouselPage>1</atom:CarouselPage>
        <atom:CarouselPage>2</atom:CarouselPage>
        <atom:CarouselPage>3</atom:CarouselPage>
        <atom:CarouselPage>4</atom:CarouselPage>
    </atom:Carousel>
</StackPanel>
```

## 公共文件

样式代码：
```xaml
<gallery:ShowCasePanel.Styles>
    <Style Selector="atom|Carousel">
        <Setter Property="Background" Value="#364d79" />
        <Setter Property="Foreground" Value="#fff" />
        <Setter Property="Height" Value="160" />
    </Style>
    <Style Selector="atom|CarouselPage">
        <Setter Property="HorizontalContentAlignment" Value="Center" />
        <Setter Property="VerticalContentAlignment" Value="Center" />
        <Setter Property="FontWeight" Value="Bold" />
    </Style>
</gallery:ShowCasePanel.Styles>
```

code-behind 文件：
```csharp
using System.Reactive.Disposables;
using AtomUI.Desktop.Controls;
using AtomUIGallery.ShowCases.ViewModels;
using ReactiveUI;
using ReactiveUI.Avalonia;

namespace AtomUIGallery.ShowCases.Views;

public partial class CarouselShowCase : ReactiveUserControl<CarouselViewModel>
{
    public CarouselShowCase()
    {
        this.WhenActivated(disposables =>
        {
            PositionOptionGroup.OptionCheckedChanged += HandlePositionOptionChanged;
            disposables.Add(Disposable.Create(() => PositionOptionGroup.OptionCheckedChanged -= HandlePositionOptionChanged));
        });
        InitializeComponent();
    }

    public void HandlePositionOptionChanged(object? sender, OptionCheckedChangedEventArgs args)
    {
        if (DataContext is CarouselViewModel viewModel)
        {
            if (args.Index == 0)
            {
                viewModel.PaginationPosition = CarouselPaginationPosition.Top;
            }
            else if (args.Index == 1)
            {
                viewModel.PaginationPosition = CarouselPaginationPosition.Bottom;
            }
            else if (args.Index == 2)
            {
                viewModel.PaginationPosition = CarouselPaginationPosition.Left;
            }
            else
            {
                viewModel.PaginationPosition = CarouselPaginationPosition.Right;
            }
        }

    }
}
```
