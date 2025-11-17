# 块状按钮

定长的按钮，有些业务场景中相对来说更适合用这种类型的按钮。

![AtomUI Button组件](./images/block-button.webp)

```axaml
<StackPanel HorizontalAlignment="Stretch" Orientation="Vertical" Margin="10">
    <atom:Button ButtonType="Primary" HorizontalAlignment="Stretch">
        Primary
    </atom:Button>
    <atom:Button ButtonType="Default" HorizontalAlignment="Stretch">
        Default
    </atom:Button>
    <atom:Button ButtonType="Text" HorizontalAlignment="Stretch">
        Text
    </atom:Button>
    <atom:Button ButtonType="Link" HorizontalAlignment="Stretch">
        Link
    </atom:Button>
</StackPanel>
```