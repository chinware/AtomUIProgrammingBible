# AtomUI ListBox快速入门

### 基础配置条件

* Nuget安装Avalonia
* Nuget安装AtomUI

### 基础用法

![AtomUI ListBox组件](./images/basic.webp)

axaml文件：
```axaml
<atom:ListBox>
    <atom:ListBoxItem>Blue</atom:ListBoxItem>
    <atom:ListBoxItem>Green</atom:ListBoxItem>
    <atom:ListBoxItem>Red</atom:ListBoxItem>
    <atom:ListBoxItem>Yellow</atom:ListBoxItem>
</atom:ListBox>
```

### 禁用Hover样式

![AtomUI ListBox组件](./images/disable-hover-effect.webp)

```axaml
<atom:ListBox DisabledItemHoverEffect="True">
    <atom:ListBoxItem>Blue</atom:ListBoxItem>
    <atom:ListBoxItem>Green</atom:ListBoxItem>
    <atom:ListBoxItem>Red</atom:ListBoxItem>
    <atom:ListBoxItem>Yellow</atom:ListBoxItem>
</atom:ListBox>
```

### 禁用条目

![AtomUI ListBox组件](./images/disabled.png)

```axaml
<atom:ListBox>
    <atom:ListBoxItem>Blue</atom:ListBoxItem>
    <atom:ListBoxItem>Green</atom:ListBoxItem>
    <atom:ListBoxItem IsEnabled="False">Red</atom:ListBoxItem>
    <atom:ListBoxItem>Yellow</atom:ListBoxItem>
</atom:ListBox>
```