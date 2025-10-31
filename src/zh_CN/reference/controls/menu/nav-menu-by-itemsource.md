# 动态产生菜单子项目

![AtomUI Menu组件](./images/generate-nav-menuitem-by-itemsource.png)

axaml文件：
```axaml
<atom:NavMenu Mode="Inline" ItemsSource="{Binding NavMenuItems}"
              x:DataType="viewModels:MenuViewModel">
    <atom:NavMenu.ItemTemplate>
        <TreeDataTemplate ItemsSource="{Binding Children}">
            <atom:TextBlock Text="{Binding Header}" />
        </TreeDataTemplate>
    </atom:NavMenu.ItemTemplate>
</atom:NavMenu>
```
