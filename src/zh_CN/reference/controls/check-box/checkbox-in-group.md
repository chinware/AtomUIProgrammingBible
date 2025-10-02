# Group Grid

通过与WrapPanel与CheckBox数组方式实现一个横向的CheckBox组。

![AtomUI CheckBox组件](./images/group-checkbox.webp)

```axaml
<StackPanel HorizontalAlignment="Left" Spacing="10" Orientation="Vertical">
    <WrapPanel Margin="0, 0, 0, 10">
        <atom:CheckBox IsChecked="True">Apple</atom:CheckBox>
        <atom:CheckBox IsChecked="True">Pear</atom:CheckBox>
        <atom:CheckBox IsChecked="True">Orange</atom:CheckBox>
    </WrapPanel>
    <WrapPanel Margin="0, 0, 0, 10">
        <atom:CheckBox>Apple</atom:CheckBox>
        <atom:CheckBox IsChecked="True">Pear</atom:CheckBox>
        <atom:CheckBox>Orange</atom:CheckBox>
    </WrapPanel>
    <WrapPanel Margin="0, 0, 0, 10">
        <atom:CheckBox IsChecked="True" IsEnabled="False">Apple</atom:CheckBox>
        <atom:CheckBox IsEnabled="False">Pear</atom:CheckBox>
        <atom:CheckBox IsEnabled="False">Orange</atom:CheckBox>
    </WrapPanel>
</StackPanel>
```