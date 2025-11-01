# 风格切换

![AtomUI Menu组件](./images/switch-menu-type.webp)

axaml文件：
```axaml
<StackPanel Orientation="Vertical" Spacing="10">
    <StackPanel Orientation="Horizontal" Spacing="5">
        <atom:ToggleSwitch Name="ChangeModeSwitch" />
        <atom:TextBlock>Change Mode</atom:TextBlock>
        <atom:ToggleSwitch Margin="10, 0, 0, 0" Name="ChangeStyleSwitch" />
        <atom:TextBlock>Change Style</atom:TextBlock>
    </StackPanel>
    <atom:NavMenu Mode="{Binding Mode}" Width="300" Margin="0, 0, 0, 20" IsDarkStyle="{Binding IsDark}">
        <atom:NavMenuItem Header="Navigation One" Icon="{atom:IconProvider Kind=MailOutlined}" />
        <atom:NavMenuItem Header="Navigation Two" Icon="{atom:IconProvider Kind=AppstoreOutlined}"
                          IsEnabled="False" />
        <atom:NavMenuItem Header="Navigation Three - Submenu"
                          Icon="{atom:IconProvider Kind=SettingOutlined}">
            <atom:NavMenuItem Header="Item 1">
                <atom:NavMenuItem Header="Option 1" />
                <atom:NavMenuItem Header="Option 2" />
            </atom:NavMenuItem>

            <atom:NavMenuItem Header="Item 2">
                <atom:NavMenuItem Header="Option 3" />
                <atom:NavMenuItem Header="Option 4" />
            </atom:NavMenuItem>
        </atom:NavMenuItem>
        <atom:NavMenuItem Header="Navigation Four" />
    </atom:NavMenu>
</StackPanel>
```
