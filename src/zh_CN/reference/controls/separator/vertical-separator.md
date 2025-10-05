# 垂直分割符

直接通过启用 `atom:VerticalSeparator` 组件即可使用垂直分隔符。

![AtomUI Separator组件](./images/vertical.PNG)

```axaml
<StackPanel Orientation="Horizontal">
    <atom:TextBlock>
        Item1
    </atom:TextBlock>
    <atom:VerticalSeparator Title="Right text" />
    <atom:TextBlock>
        Item2
    </atom:TextBlock>
    <atom:VerticalSeparator />
    <atom:TextBlock>
        Item3
    </atom:TextBlock>
</StackPanel>
```