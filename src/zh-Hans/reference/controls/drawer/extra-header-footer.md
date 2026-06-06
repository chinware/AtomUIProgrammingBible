# 自定义头部尾部

使用 `Drawer.Extra` 属性定义抽屉头部右侧的额外操作区域，使用 `Drawer.Footer` 属性定义抽屉底部操作区域，而 `Placement` 属性定义抽屉弹出时的方向。

![AtomUI Drawer组件](./images/extra-and-footer.webp)

axaml文件：
```xaml
<Panel>
    <StackPanel Classes="ControllerPanel">
        <ListBox Classes="PlacementList"
                 Name="ExtraAndFooter"
                 ItemsSource="{utils:Enum atom:DrawerPlacement}"
                 SelectedIndex="2" />
        <atom:ToggleSwitch Content="Open" />
    </StackPanel>
    <atom:Drawer
        IsOpen="{Binding $parent[Panel].((Panel)Children[0]).((atom:ToggleSwitch)Children[1]).IsChecked}"
        Title="Basic Drawer"
        Placement="{Binding $parent[Panel].((Panel)Children[0]).((ListBox)Children[0]).SelectedItem}">
        <atom:Drawer.Extra>
            <StackPanel Orientation="Horizontal" Spacing="10">
                <atom:Button>Cancel</atom:Button>
                <atom:Button ButtonType="Primary">Ok</atom:Button>
            </StackPanel>
        </atom:Drawer.Extra>
        <atom:Drawer.Footer>
            <StackPanel Orientation="Horizontal" Spacing="10">
                <atom:Button>Edit</atom:Button>
                <atom:Button ButtonType="Primary">Upload</atom:Button>
                <atom:Button ButtonType="Primary" IsDanger="True">Delete</atom:Button>
            </StackPanel>
        </atom:Drawer.Footer>
        <StackPanel Orientation="Vertical" Spacing="5">
            <atom:TextBlock Text="Some contents..." />
            <atom:TextBlock Text="Some contents..." />
            <atom:TextBlock Text="Some contents..." />
        </StackPanel>
    </atom:Drawer>
</Panel>
```