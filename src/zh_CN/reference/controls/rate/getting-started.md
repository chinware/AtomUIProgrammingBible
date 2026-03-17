# Rate 快速入门

### 基础配置条件

* Nuget安装Avalonia
* Nuget安装AtomUI

### 基础用法

默认提供五颗星的评分组件，只需一行即可使用。

![AtomUI Rate组件](./images/basic.webp)

```xaml
<atom:Rate />
```

### 半星

将 `IsAllowHalf` 设为 `True` 即可支持半星选择，同时通过 `DefaultValue` 属性设定初始评分值。

![AtomUI Rate组件](./images/half-star.webp)

```xaml
<atom:Rate DefaultValue="3.5" IsAllowHalf="True" />
```

### 只读模式

通过将 `IsEnabled` 设为 `False`，可以将评分组件设置为只读状态，仅供展示使用。

![AtomUI Rate组件](./images/readonly.png)

```xaml
<atom:Rate DefaultValue="2" IsEnabled="False" />
```

### 提示文字

通过绑定 `ToolTips` 属性，可以在鼠标悬停时展示对应星级的提示文案，结合 `ValueChanged` 事件可以实时显示当前选中的文案。

![AtomUI Rate组件](./images/show-copywrite.webp)

```xaml
<StackPanel Orientation="Vertical" Spacing="10">
    <atom:Rate Name="ToolTipRate" ToolTips="{Binding Tooltips}"
               ValueChanged="HandleValueChanged"/>
    <TextBlock Text="{Binding ActiveTooltip}"/>
</StackPanel>
```

### 自定义字符

通过 `Character` 属性可以将默认的星形图标替换为任意字符，包括图标、字母或汉字。

![AtomUI Rate组件](./images/other-char.webp)

```xaml
<StackPanel Orientation="Vertical" Spacing="10">
    <atom:Rate IsAllowHalf="True" IsAllowClear="True" Character="{antdicons:AntDesignIconProvider HeartOutlined}"/>
    <atom:Rate IsAllowHalf="True" IsAllowClear="True" Character="A"/>
    <atom:Rate IsAllowHalf="True" IsAllowClear="True" Character="秦"/>
</StackPanel>
```
