# 块级按钮

按钮的块级属性由 `HorizontalAlignment` 属性决定，当值为Stretch时，按钮会占满父容器的宽度。

![AtomUI Button组件](./images/block-button.webp)

```axaml
<StackPanel>
    <atom:Button ButtonType="Primary" 
                 HorizontalAlignment="Stretch">Primary</atom:Button>
    <atom:Button ButtonType="Default" 
                 HorizontalAlignment="Stretch">Default</atom:Button>
    <atom:Button ButtonType="Text" 
                 HorizontalAlignment="Stretch">Text</atom:Button>
    <atom:Button ButtonType="Link" 
                 HorizontalAlignment="Stretch">Link</atom:Button>
</StackPanel>
```