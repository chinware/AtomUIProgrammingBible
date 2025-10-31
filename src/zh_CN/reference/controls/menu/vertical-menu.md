# 垂直菜单

![AtomUI Menu组件](./images/vertical-nav-menu.webp)

axaml文件：
```axaml
<atom:NavMenu Mode="Vertical" Width="300" Margin="0, 0, 0, 20">
    <atom:NavMenuItem Header="Navigation One" Icon="{atom:IconProvider Kind=MailOutlined}" />
    <atom:NavMenuItem Header="Navigation Two" Icon="{atom:IconProvider Kind=AppstoreOutlined}"
                      IsEnabled="False" />
    <atom:NavMenuItem Header="Navigation Three - Submenu" Icon="{atom:IconProvider Kind=SettingOutlined}">
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
```

![AtomUI Menu组件](./images/inline-menu.webp)

axaml文件：
```axaml
<atom:NavMenu Mode="Inline" Width="300" Margin="0, 0, 0, 20">
    <atom:NavMenuItem Header="Navigation One" Icon="{atom:IconProvider Kind=MailOutlined}" />
    <atom:NavMenuItem Header="Navigation Two" Icon="{atom:IconProvider Kind=AppstoreOutlined}"
                      IsEnabled="False" />
    <atom:NavMenuItem Header="Navigation Three - Submenu" Icon="{atom:IconProvider Kind=SettingOutlined}">
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
```
