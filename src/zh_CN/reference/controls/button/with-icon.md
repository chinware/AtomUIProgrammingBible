# AtomUI Button自定义图标

按钮的图标由 `Icon` 属性决定，而 `Icon` 也是由 `AtomUI` 提供的基础组件，详情参考 `Icon` 章节。

![AtomUI Button组件](./images/icon-button.webp)

```axaml
<StackPanel>
    <atom:Button ButtonType="Primary" 
                 Shape="Circle" 
                 Icon="{atom:IconProvider Kind=SearchOutlined}" />
    <atom:Button ButtonType="Primary" 
                 Shape="Round"
                 Icon="{atom:IconProvider Kind=SearchOutlined}">Search</atom:Button>
    <atom:Button ButtonType="Default" 
                 Shape="Circle" 
                 Icon="{atom:IconProvider Kind=SearchOutlined}" />
    <atom:Button ButtonType="Default" 
                 Shape="Round" 
                 Icon="{atom:IconProvider Kind=SearchOutlined}">Search</atom:Button>
    <atom:Button ButtonType="Text" 
                 Shape="Default" 
                 Icon="{atom:IconProvider Kind=SearchOutlined}">Search</atom:Button>
    <atom:Button ButtonType="Link" 
                 Shape="Default" 
                 Icon="{atom:IconProvider Kind=SearchOutlined}">Search</atom:Button>
</StackPanel>
```