# 弹出方向

用户通过 `ListBox` 选择不同的位置（上/下/左/右）。

![AtomUI Drawer组件](./images/basic.webp)

```xaml
<Panel>
    <StackPanel Classes="ControllerPanel">
        <ListBox Classes="PlacementList"
                 Name="CustomPlacement"
                 ItemsSource="{utils:Enum atom:DrawerPlacement}"
                 SelectedIndex="2" />
        <atom:ToggleSwitch Content="Open" />
    </StackPanel>

    <atom:Drawer
        IsOpen="{Binding $parent[Panel].((Panel)Children[0]).((atom:ToggleSwitch)Children[1]).IsChecked}"
        Title="Basic Drawer"
        Placement="{Binding $parent[Panel].((Panel)Children[0]).((ListBox)Children[0]).SelectedItem}">
        <StackPanel Orientation="Vertical" Spacing="5">
            <atom:TextBlock Text="Some contents..." />
            <atom:TextBlock Text="Some contents..." />
            <atom:TextBlock Text="Some contents..." />
        </StackPanel>
    </atom:Drawer>
</Panel>
```