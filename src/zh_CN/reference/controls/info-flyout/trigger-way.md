# 触发方式

`Trigger` 属性决定了组件的触发方式，值有 `Hover` 和 `Click` 两种。

![AtomUI InfoFlyout组件](./images/trigger-way.webp)

```axaml
<StackPanel Orientation="Horizontal" Spacing="10">
    <atom:FlyoutHost Trigger="Hover">
        <atom:FlyoutHost.Flyout>
            <atom:Flyout>
                <TextBlock Width="200" Height="100" Padding="20">The most basic example.</TextBlock>
            </atom:Flyout>
        </atom:FlyoutHost.Flyout>
        <atom:Button>Hover me</atom:Button>
    </atom:FlyoutHost>
    <atom:FlyoutHost Trigger="Click">
        <atom:FlyoutHost.Flyout>
            <atom:Flyout>
                <TextBlock Width="200" Height="100" Padding="20">The most basic example.</TextBlock>
            </atom:Flyout>
        </atom:FlyoutHost.Flyout>
        <atom:Button>Click me</atom:Button>
    </atom:FlyoutHost>
</StackPanel>
```

