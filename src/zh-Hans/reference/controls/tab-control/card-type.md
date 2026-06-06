# 卡片形式

如果需要卡片样式的 `TabControl`，可以使用 `atom:CardTabControl` 组件。

![AtomUI TabControl组件](./images/card-type.webp)

```xaml
<StackPanel Orientation="Vertical" Spacing="20">
    <atom:CardTabControl>
        <atom:TabItem Header="Tab 1" Icon="{atom:IconProvider Kind=AppleOutlined}">Content of Tab Pane 1</atom:TabItem>
        <atom:TabItem Header="Tab 2" Icon="{atom:IconProvider Kind=AndroidOutlined}">Content of Tab Pane 2</atom:TabItem>
        <atom:TabItem Header="Tab 3" Icon="{atom:IconProvider Kind=WechatOutlined}">Content of Tab Pane 3</atom:TabItem>
    </atom:CardTabControl>
</StackPanel>
```
