# Watermark API 参考

## Watermark

`Watermark` 是一个密封类（`sealed class`），继承自 `Control`。它通过附加属性为目标控件渲染水印图案。

### 附加属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `Glyph` | 水印图案定义，支持文本或图片 | `WatermarkGlyph?` | `null` |

**用法示例：**

```xaml
<Border atom:Watermark.Glyph="{atom:TextGlyph 'AtomUI'}" />
```

## WatermarkGlyph

`WatermarkGlyph` 是水印图案的抽象基类，包含以下两种具体实现。

### TextGlyph

文本水印图案，用于绘制文字水印。

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `Text` | 水印文本内容，支持 `&#x000A;` 换行符实现多行文本 | `string` | `""` |
| `FontSize` | 字号 | `double` | — |
| `Foreground` | 文本颜色 | `IBrush` | — |

**用法示例：**

```xaml
<!-- 单行文本水印 -->
<Border atom:Watermark.Glyph="{atom:TextGlyph 'AtomUI'}" />

<!-- 多行文本水印，自定义字号和颜色 -->
<Border atom:Watermark.Glyph="{atom:TextGlyph 'AtomUI&#x000A;Happy Working', FontSize=18, Foreground=Gray}" />
```

### ImageGlyph

图片水印图案，用于绘制图片水印。

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `Source` | 水印图片资源路径 | `IImage` | `null` |

**用法示例：**

```xaml
<Border Height="400">
    <atom:Watermark.Glyph>
        <atom:ImageGlyph Source="/Assets/ATOMUI-LOGO.png" />
    </atom:Watermark.Glyph>
</Border>
```
