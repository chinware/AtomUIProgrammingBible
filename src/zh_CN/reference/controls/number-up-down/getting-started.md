# AtomUI NumberUpDown快速入门

### 基础配置条件

* Nuget安装Avalonia
* Nuget安装AtomUI

### 基础用法

`Value` 属性用于设定控件初始化值。

![AtomUI NumberUpDown组件](./images/basic.webp)

axaml文件：
```axaml
<atom:NumericUpDown Value="3" />
```

### 大小尺寸

`SizeType` 属性用于设定控件大小，目前预设值有三种：Large, Middle, Small。

![AtomUI NumberUpDown组件](./images/size.webp)

axaml文件：
```axaml
<StackPanel Orientation="Vertical" Spacing="10" Margin="0, 0, 20, 0">
    <atom:NumericUpDown SizeType="Large" Value="3" />
    <atom:NumericUpDown SizeType="Middle" Value="3" />
    <atom:NumericUpDown SizeType="Small" Value="3" />
</StackPanel>
```

### 禁用状态

`IsEnabled` 属性用于设定控件是否可用。

![AtomUI NumberUpDown组件](./images/disabled.png)

```axaml
<StackPanel Orientation="Vertical" Spacing="10">
    <atom:NumericUpDown Value="3" StyleVariant="Outline" IsEnabled="False"/>
    <atom:NumericUpDown Value="3" StyleVariant="Filled" IsEnabled="False"/>
    <atom:NumericUpDown Value="3" StyleVariant="Borderless" IsEnabled="False"/>
</StackPanel>
```

### 状态色

* `Watermark` 属性用于设定控件水印，类似于网页表单中的 `placeholder`，可以说明控件的用途。
* `Status` 状态色属性用于设定控件状态色，目前预设值有三种：Error, Warning, Normal（默认项）。
* `InnerLeftContent` 属性用于设定控件前缀图标，图标参考 `atom:IconProvider` 组件。

![AtomUI NumberUpDown组件](./images/status.webp)

```axaml
<StackPanel Orientation="Vertical" Spacing="10" Margin="0, 0, 20, 0">
    <atom:NumericUpDown Watermark="Error" Status="Error" />
    <atom:NumericUpDown Watermark="Warning" Status="Warning" />
    <atom:NumericUpDown Watermark="Error with prefix"
                        InnerLeftContent="{atom:IconProvider Kind=ClockCircleOutlined}" Status="Error" />
    <atom:NumericUpDown Watermark="Warning with prefix"
                        InnerLeftContent="{atom:IconProvider Kind=ClockCircleOutlined}" Status="Warning" />

    <atom:NumericUpDown Watermark="Error" Status="Error"
                        InnerLeftContent="{atom:IconProvider Kind=ClockCircleOutlined}"
                        StyleVariant="Filled" />
    <atom:NumericUpDown Watermark="Warning" Status="Warning"
                        InnerLeftContent="{atom:IconProvider Kind=ClockCircleOutlined}"
                        StyleVariant="Filled" />

    <atom:NumericUpDown Watermark="Error" Status="Error"
                        InnerLeftContent="{atom:IconProvider Kind=ClockCircleOutlined}"
                        StyleVariant="Borderless" />
    <atom:NumericUpDown Watermark="Warning" Status="Warning"
                        InnerLeftContent="{atom:IconProvider Kind=ClockCircleOutlined}"
                        StyleVariant="Borderless" />
</StackPanel>
```