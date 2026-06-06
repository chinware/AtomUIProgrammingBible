# 多层级抽屉

在一级 `Drawer` 内部嵌套了另一个 `Drawer`（二级抽屉），二级抽屉初始处于关闭状态，通过按钮点击事件触发显示。二级抽屉通过 `Button.Click` 事件 `HandleOpenMultilevelLevelTwoDrawer`（参考gettting-started.md中的code-behind代码）方法控制开启

![AtomUI Drawer组件](./images/multi-level.webp)

axaml文件：
```xaml
<Panel>
    <StackPanel Height="120" Classes="ControllerPanel">
        <ListBox Classes="PlacementList"
                 ItemsSource="{utils:Enum atom:DrawerPlacement}"
                 SelectedIndex="2" />
        <atom:ToggleSwitch />
    </StackPanel>

    <atom:Drawer Title="First-level Drawer"
                  IsOpen="{Binding $parent[Panel].((Panel)Children[0]).((atom:ToggleSwitch)Children[1]).IsChecked}"
                  Placement="{Binding $parent[Panel].((Panel)Children[0]).((ListBox)Children[0]).SelectedItem}">
        <StackPanel Orientation="Vertical" Spacing="5">
            <atom:TextBlock Text="Some contents..." />
            <atom:TextBlock Text="Some contents..." />
            <atom:TextBlock Text="Some contents..." />
            <atom:Button ButtonType="Primary"
                         Click="HandleOpenMultilevelLevelTwoDrawer">
                Two-level drawer
            </atom:Button>
            <atom:Drawer Title="Two-level Drawer"
                          Name="MultiLevelDrawerLevelTwo">
                <StackPanel Orientation="Vertical" Spacing="5">
                    <atom:TextBlock Text="Some contents..." />
                    <atom:TextBlock Text="Some contents..." />
                    <atom:TextBlock Text="Some contents..." />
                </StackPanel>
            </atom:Drawer>
        </StackPanel>
    </atom:Drawer>
</Panel>
```