# 危险按钮

非常简单，一眼万年。`Danger`，就是这么从容。

![AtomUI Button组件](./images/danger-button.webp)

```axaml
<WrapPanel HorizontalAlignment="Stretch" Orientation="Horizontal">
    <atom:Button ButtonType="Primary" IsDanger="True">
        Primary
    </atom:Button>
    <atom:Button ButtonType="Default" IsDanger="True">
        Default
    </atom:Button>
    <atom:Button ButtonType="Text" IsDanger="True">
        Text
    </atom:Button>
    <atom:Button ButtonType="Link" IsDanger="True">
        Link
    </atom:Button>
</WrapPanel>
```