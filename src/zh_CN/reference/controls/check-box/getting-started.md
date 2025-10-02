# AtomUI CheckBox快速入门

### 基础配置条件

* Nuget安装Avalonia
* Nuget安装AtomUI

### 基础用法

最基础最小配置化的CheckBox组件。

![AtomUI CheckBox组件](./images/basic.webp)

```axaml
<StackPanel HorizontalAlignment="Left">
    <atom:CheckBox>Checkbox</atom:CheckBox>
</StackPanel>
```

### 禁用状态

`IsEnabled` 属性用来控制组件是否可用，`IsChecked` 状态属性用来控制组件是否选中，其中{x:Null}表示半选状态（不确定状态）。

![AtomUI CheckBox组件](./images/disabled.png)

```axaml
<StackPanel HorizontalAlignment="Left" Spacing="10" Orientation="Vertical">
    <atom:CheckBox IsChecked="False" IsEnabled="False">UnChecked</atom:CheckBox>
    <atom:CheckBox IsChecked="{x:Null}" IsEnabled="False">Indeterminate</atom:CheckBox>
    <atom:CheckBox IsChecked="True" IsEnabled="False">Checked</atom:CheckBox>
</StackPanel>
```