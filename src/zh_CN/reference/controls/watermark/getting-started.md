# Watermark 快速入门

## 基础配置条件

* Nuget 安装 Avalonia
* Nuget 安装 AtomUI

## 基础用法

`atom:Watermark.Glyph` 是一个附加属性，用于在目标控件上设置水印内容。通过 `atom:TextGlyph` 定义文字水印，通过 `atom:ImageGlyph` 定义图片水印。

为一个 `Border` 区域添加文本水印，内容为 "AtomUI"：

![AtomUI Watermark 组件](./images/basic.png)

```xaml
<Border Height="300"
        HorizontalAlignment="Stretch"
        atom:Watermark.Glyph="{atom:TextGlyph 'AtomUI'}" />
```

## 多行文本水印

在 `TextGlyph` 的文本内容中使用 `&#x000A;` 换行符可实现多行水印。同时可自定义 `FontSize`、`Foreground` 等属性。

![AtomUI Watermark 多行文本水印](./images/inline-watermark.png)

```xaml
<Border Height="200"
        HorizontalAlignment="Stretch"
        atom:Watermark.Glyph="{atom:TextGlyph 'AtomUI&#x000A;Happy Working', FontSize=18, Foreground=Gray}" />
```

## 图片水印

通过 `ImageGlyph` 的 `Source` 属性指定图片路径，即可创建图片水印。

![AtomUI Watermark 图片水印](./images/image-watermark.png)

```xaml
<Border Height="400">
    <atom:Watermark.Glyph>
        <atom:ImageGlyph Source="/Assets/ATOMUI-LOGO.png" />
    </atom:Watermark.Glyph>
</Border>
```

## 自定义水印预览

水印可应用于包含复杂内容的容器控件（如 `StackPanel`），水印图案会覆盖在所有子内容之上。

![AtomUI Watermark 自定义水印预览](./images/custom-watermark.png)

```xaml
<StackPanel atom:Watermark.Glyph="{atom:TextGlyph 'AtomUI'}">
    <atom:TextBlock TextWrapping="Wrap">
        The light-speed iteration of the digital world makes products more complex. However, human
        consciousness and attention resources are limited. Facing this design contradiction, the
        pursuit of natural interaction will be the consistent direction of Ant Design.
        <LineBreak /><LineBreak />
        Natural user cognition: According to cognitive psychology, about 80% of external information
        is obtained through visual channels. The most important visual elements in the interface
        design, including layout, colors, illustrations, icons, etc., should fully absorb the laws
        of nature, thereby reducing the user's cognitive cost and bringing authentic and smooth
        feelings. In some scenarios, opportunely adding other sensory channels such as hearing, touch
        can create a richer and more natural product experience.
        <LineBreak /><LineBreak />
        Natural user behavior: In the interaction with the system, the designer should fully
        understand the relationship between users, system roles, and task objectives, and also
        contextually organize system functions and services. At the same time, a series of methods
        such as behavior analysis, artificial intelligence and sensors could be applied to assist
        users to make effective decisions and reduce extra operations of users, to save users' mental
        and physical resources and make human-computer interaction more natural.
    </atom:TextBlock>
    <Image Source="/Assets/watermark-sample.png" />
</StackPanel>
```
