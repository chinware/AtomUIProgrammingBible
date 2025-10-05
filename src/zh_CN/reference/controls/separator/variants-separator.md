# 分隔符风格

通过 `Variant` 来改变分隔符的样式，共有Solid、Dotted、Dashed三个值，同时可以通过 `LineColor` 来改变分隔符的线条颜色。

![AtomUI Separator组件](./images/variants.PNG)

```axaml
<StackPanel Orientation="Vertical">
    <atom:TextBlock TextWrapping="Wrap">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed nonne merninisti licere mihi ista probare, quae sunt a te dicta? Refert tamen, quo modo.
    </atom:TextBlock>
    <atom:Separator Title="Solid" LineColor="#7cb305"/>
    <atom:TextBlock TextWrapping="Wrap">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed nonne merninisti licere mihi ista probare, quae sunt a te dicta? Refert tamen, quo modo.
    </atom:TextBlock>
    <atom:Separator Title="Dotted" LineColor="#7cb305" Variant="Dotted"/>
    <atom:TextBlock TextWrapping="Wrap">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed nonne merninisti licere mihi ista probare, quae sunt a te dicta? Refert tamen, quo modo.
    </atom:TextBlock>
    <atom:Separator Title="Dashed" LineColor="#7cb305" Variant="Dashed"/>
    <atom:TextBlock TextWrapping="Wrap">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed nonne merninisti licere mihi ista probare, quae sunt a te dicta? Refert tamen, quo modo.
    </atom:TextBlock>
</StackPanel>
```