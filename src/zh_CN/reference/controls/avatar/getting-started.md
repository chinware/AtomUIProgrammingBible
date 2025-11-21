# Avatar 快速入门

### 基础配置条件

* Nuget安装Avalonia
* Nuget安装AtomUI

### 初始化

最基础最小配置化的头像组件功能，通过 `Icon` 属性传入 `AtomUI` 内置的图标库设定图标，通过 `Shape` 属性设置头像形状，通过 `Size` 或 `SizeType` 属性设置头像大小。

```xaml
<StackPanel Orientation="Vertical" Spacing="20">
    <StackPanel Orientation="Horizontal" Spacing="10">
        <atom:Avatar Icon="{atom:IconProvider UserOutlined}" Size="64" />
        <atom:Avatar Icon="{atom:IconProvider UserOutlined}" SizeType="Large" />
        <atom:Avatar Icon="{atom:IconProvider UserOutlined}" />
        <atom:Avatar Icon="{atom:IconProvider UserOutlined}" SizeType="Small" />
        <atom:Avatar Icon="{atom:IconProvider UserOutlined}" Size="14" />
    </StackPanel>

    <StackPanel Orientation="Horizontal" Spacing="10">
        <atom:Avatar Shape="Square" Icon="{atom:IconProvider UserOutlined}" Size="64" />
        <atom:Avatar Shape="Square" Icon="{atom:IconProvider UserOutlined}" SizeType="Large" />
        <atom:Avatar Shape="Square" Icon="{atom:IconProvider UserOutlined}" />
        <atom:Avatar Shape="Square" Icon="{atom:IconProvider UserOutlined}" SizeType="Small" />
        <atom:Avatar Shape="Square" Icon="{atom:IconProvider UserOutlined}" Size="14" />
    </StackPanel>
</StackPanel>
```

![AtomUI Avatar组件](./images/basic.png)