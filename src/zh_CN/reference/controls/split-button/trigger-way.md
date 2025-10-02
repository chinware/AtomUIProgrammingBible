# 触发方式

分裂按钮的触发方式由 `TriggerType` 确定，一共有Click和Hover两个值；默认为Click。

![AtomUI SplitButton组件](./images/trigger-split-button.webp)

```axaml
<StackPanel>
    <atom:SplitButton TriggerType="Hover">
        Hover Me
        <atom:SplitButton.Flyout>
            <atom:MenuFlyout>
                <atom:MenuItem Header="Cut" InputGesture="Ctrl+X"
                               Icon="{atom:IconProvider Kind=ScissorOutlined}" />
                <atom:MenuItem Header="Copy" InputGesture="Ctrl+C"
                               Icon="{atom:IconProvider Kind=CopyOutlined}" />
                <atom:MenuItem Header="Delete" InputGesture="Ctrl+D"
                               Icon="{atom:IconProvider Kind=DeleteOutlined}" />
            </atom:MenuFlyout>
        </atom:SplitButton.Flyout>
    </atom:SplitButton>
    
    <atom:SplitButton FlyoutButtonIcon="{atom:IconProvider Kind=UserOutlined}" TriggerType="Click">
        Click Me
        <atom:SplitButton.Flyout>
            <atom:MenuFlyout>
                <atom:MenuItem Header="Cut" InputGesture="Ctrl+X"
                               Icon="{atom:IconProvider Kind=ScissorOutlined}" />
                <atom:MenuItem Header="Copy" InputGesture="Ctrl+C"
                               Icon="{atom:IconProvider Kind=CopyOutlined}" />
                <atom:MenuItem Header="Delete" InputGesture="Ctrl+D"
                               Icon="{atom:IconProvider Kind=DeleteOutlined}" />
            </atom:MenuFlyout>
        </atom:SplitButton.Flyout>
    </atom:SplitButton>
</StackPanel>
```