# Empty 快速入门

## 前置条件

- NuGet 安装 `Avalonia`
- NuGet 安装 `AtomUI`

## 基础用法

通过 `PresetImage` 属性使用预设图片，内置 Default 和 Simple 两种样式。

![AtomUI Empty 基础用法](./images/basic.png)

```xaml
<atom:EmptyIndicator PresetImage="Default" />
```

| PresetImage | 说明 |
|---|---|
| `Default` | 默认风格图片，适合一般空状态场景 |
| `Simple` | 简洁风格图片，适合紧凑布局 |

## 尺寸类型

通过 `SizeType` 属性控制组件大小，内置 Small、Middle、Large 三种尺寸。

![AtomUI Empty 尺寸](./images/size.png)

```xaml
<StackPanel Orientation="Vertical">
    <StackPanel Orientation="Horizontal">
        <atom:EmptyIndicator PresetImage="Simple" SizeType="Small" />
        <atom:EmptyIndicator PresetImage="Simple" SizeType="Middle" />
        <atom:EmptyIndicator PresetImage="Simple" SizeType="Large" />
    </StackPanel>
</StackPanel>
```

## 自定义图片与描述

通过 `ImagePath` 属性指定自定义图片路径，通过 `Description` 属性设置描述文本。可配合其他控件构建完整的空状态引导界面。

![AtomUI Empty 自定义](./images/customize.png)

```xaml
<StackPanel Orientation="Vertical" Spacing="10">
    <atom:EmptyIndicator ImagePath="avares://AtomUIGallery/Assets/EmptyShowCase/empty.svg"
                         SizeType="Large"
                         Description="Customize Description" />
    <atom:Button HorizontalAlignment="Center" ButtonType="Primary">Create Now</atom:Button>
</StackPanel>
```

## 隐藏描述信息

通过 `IsShowDescription` 属性控制描述文本的显示与隐藏。设置为 `False` 时仅展示图片，适用于空间有限的场景。

![AtomUI Empty 无描述](./images/no-description.png)

```xaml
<atom:EmptyIndicator PresetImage="Default" IsShowDescription="False" />
```
