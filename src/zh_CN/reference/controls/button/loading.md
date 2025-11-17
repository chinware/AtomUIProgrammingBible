# Loading状态

`Loading` 状态可以显著提升用户在等待时的体验与视觉感受，这个特性是由 `IsLoading` 属性来决定的，开发者可以重点参考下面示例中的点击事件与 `IsLoading` 的结合使用方式。

`HandleLoadingBtnClick` 事件可以参考快速入门中的Code Behind代码。

![AtomUI Button组件](./images/load-button.webp)

```axaml
<StackPanel HorizontalAlignment="Stretch" Orientation="Vertical" Margin="10">
    <WrapPanel>
        <atom:Button ButtonType="Primary" IsLoading="True">Loading</atom:Button>
        <atom:Button ButtonType="Primary" SizeType="Small" IsLoading="True">Loading</atom:Button>
        <atom:Button ButtonType="Primary" IsLoading="True" Icon="{atom:IconProvider Kind=PoweroffOutlined}" />
    </WrapPanel>
    
    <WrapPanel>
        <atom:Button ButtonType="Primary" Click="HandleLoadingBtnClick">Click me!</atom:Button>
        <atom:Button ButtonType="Primary"
                     Click="HandleLoadingBtnClick"
                     Icon="{atom:IconProvider Kind=PoweroffOutlined}">
            Click me!
        </atom:Button>
        <atom:Button ButtonType="Primary"
                     Click="HandleLoadingBtnClick"
                     Icon="{atom:IconProvider Kind=PoweroffOutlined}" />
    </WrapPanel>
</StackPanel>
```