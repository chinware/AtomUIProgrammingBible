# Rate 快速入门

### 基础配置条件

* Nuget安装Avalonia
* Nuget安装AtomUI

### 基础用法

只需一行，闪电开启。

![AtomUI Rate组件](./images/basic.webp)

```xaml
<atom:Rate />
```

### 半星起步

打分的基础步进可以设定为半星，同时通过 `DefaultValue` 属性设定默认值。

![AtomUI Rate组件](./images/half-star.webp)

```xaml
<atom:Rate DefaultValue="3.5" IsAllowHalf="True" />
```

### 只读

我只需你看，我不许你摸。

![AtomUI Rate组件](./images/readonly.png)

```xaml
<atom:Rate DefaultValue="2" IsEnabled="False" />
```

### 文案显示

打分同时通过文案给够足够的情绪价值。

![AtomUI Rate组件](./images/show-copywrite.webp)

```xaml
<StackPanel Orientation="Vertical" Spacing="10">
    <atom:Rate Name="ToolTipRate" ToolTips="{Binding Tooltips}"
               ValueChanged="HandleValueChanged"/>
    <TextBlock Text="{Binding ActiveTooltip}"/>
</StackPanel>
```

### 自定义字符

请记住 `Character` 属性！

![AtomUI Rate组件](./images/other-char.webp)

```xaml
<StackPanel Orientation="Vertical" Spacing="10">
    <atom:Rate IsAllowHalf="True" IsAllowClear="True" Character="{antdicons:AntDesignIconProvider HeartOutlined}"/>
    <atom:Rate IsAllowHalf="True" IsAllowClear="True" Character="A"/>
    <atom:Rate IsAllowHalf="True" IsAllowClear="True" Character="秦"/>
</StackPanel>
```