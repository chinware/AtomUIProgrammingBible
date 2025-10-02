# 幽灵按钮

按钮的幽灵属性由 `IsGhost` 属性决定，一共有True和False两个值；默认为False。

![AtomUI Button组件](./images/ghost-button.webp)

```axaml
<StackPanel>
    <atom:Button ButtonType="Primary" IsGhost="True">Primary</atom:Button>
    <atom:Button ButtonType="Default" IsGhost="True">Default</atom:Button>
    <atom:Button ButtonType="Text" IsGhost="True">Text</atom:Button>
    <atom:Button ButtonType="Link" IsGhost="True">Link</atom:Button>
    <atom:Button ButtonType="Primary" IsDanger="True" IsGhost="True">Danger</atom:Button>
</StackPanel>
```