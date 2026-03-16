# Palette 快速入门

## 前置条件

- NuGet 安装 `Avalonia`
- NuGet 安装 `AtomUI`

## 基础用法

`ColorPicker` 是调色板的核心交互组件，用户点击后弹出颜色选择面板。

![AtomUI Palette 调色板](./images/palette.webp)

```xaml
<atom:ColorPicker />
```

## 颜色格式

通过 `Format` 属性设置颜色的显示格式，支持 HEX、RGB、HSB 等格式。

```xaml
<atom:ColorPicker Format="Hex" />
<atom:ColorPicker Format="Rgb" />
<atom:ColorPicker Format="Hsb" />
```

设置 `IsFormatEnabled="True"` 允许用户在面板中自行切换颜色格式：

```xaml
<atom:ColorPicker IsFormatEnabled="True" />
```

## 透明度

通过 `IsAlphaEnabled` 属性开启 Alpha 通道，允许用户调节颜色透明度。

```xaml
<atom:ColorPicker IsAlphaEnabled="True" />
```

## 触发方式

通过 `TriggerType` 属性控制弹出面板的触发方式，支持点击（Click）和悬停（Hover）。

```xaml
<!-- 点击触发（默认） -->
<atom:ColorPicker TriggerType="Click" />

<!-- 悬停触发 -->
<atom:ColorPicker TriggerType="Hover" />
```

## 显示颜色文本

设置 `IsShowText="True"` 在触发器上显示当前颜色值文本。

```xaml
<atom:ColorPicker IsShowText="True" />
```

## 尺寸

通过 `SizeType` 属性控制颜色选择器大小，可选值为 `Large`、`Middle`（默认）、`Small`。

```xaml
<atom:ColorPicker SizeType="Large" />
<atom:ColorPicker SizeType="Middle" />
<atom:ColorPicker SizeType="Small" />
```

## 弹出位置与箭头

通过 `Placement` 属性控制弹出面板的方向，`IsShowArrow` 控制是否显示箭头指示器，`IsPointAtCenter` 控制箭头是否指向触发器中心。

```xaml
<atom:ColorPicker Placement="Bottom" IsShowArrow="True" IsPointAtCenter="True" />
<atom:ColorPicker Placement="Top" IsShowArrow="True" />
<atom:ColorPicker Placement="Right" IsShowArrow="False" />
```

## 预设色板

通过 `IsPaletteGroupEnabled` 开启预设色板功能，并通过 `PaletteGroup` 属性提供预设颜色分组，方便用户从常用颜色中快速选取。

```xaml
<atom:ColorPicker IsPaletteGroupEnabled="True"
                  PaletteGroup="{Binding MyPaletteGroup}" />
```

Code-behind 定义预设颜色：

```csharp
public List<ColorPickerPalette> MyPaletteGroup { get; set; } = new()
{
    new ColorPickerPalette
    {
        Colors = new List<Color>
        {
            Color.Parse("#F5222D"),
            Color.Parse("#FA8C16"),
            Color.Parse("#FADB14"),
            Color.Parse("#52C41A"),
            Color.Parse("#1890FF"),
            Color.Parse("#722ED1"),
        }
    }
};
```

## 清除功能

设置 `IsClearEnabled="True"` 允许用户清除已选颜色。可通过 `EmptyColorText` 自定义空状态的提示文本。

```xaml
<atom:ColorPicker IsClearEnabled="True" EmptyColorText="未选择" />
```

## 事件处理

通过 `ValueChanged` 监听颜色变化，通过 `ValueSelected` 监听用户最终确认选择的颜色。

```xaml
<atom:ColorPicker ValueChanged="OnColorChanged"
                  ValueSelected="OnColorSelected" />
```

```csharp
private void OnColorChanged(object? sender, EventArgs e)
{
    // 颜色值发生变化时触发（包括拖动过程中）
}

private void OnColorSelected(object? sender, EventArgs e)
{
    // 用户最终确认选择颜色时触发
}
```
