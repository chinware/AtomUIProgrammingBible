# GroupBox API

### 类定义

```csharp
public class GroupBox : ContentControl
```

### 标题位置枚举

```csharp
public enum GroupBoxTitlePosition
{
    Left,
    Right,
    Center
}
```

### 属性

| 属性名 | 类型 | 默认值 | 说明 |
| --- | --- | --- | --- |
| HeaderTitle | `string?` | `null` | 标题文本 |
| HeaderTitleColor | `IBrush?` | `null` | 标题文本颜色 |
| HeaderIcon | `PathIcon?` | `null` | 标题图标 |
| HeaderTitlePosition | `GroupBoxTitlePosition` | `Left` | 标题位置，支持 `Left`、`Center`、`Right` |
| HeaderFontSize | `double` | - | 标题字体大小 |
| HeaderFontStyle | `FontStyle` | - | 标题字体样式，如 `Italic`、`Oblique` 等 |
| HeaderFontWeight | `FontWeight` | `Normal` | 标题字体粗细，如 `Bold`、`Medium` 等 |

### 继承属性

`GroupBox` 继承自 `ContentControl`，因此还支持以下常用属性：

| 属性名 | 类型 | 说明 |
| --- | --- | --- |
| Content | `object?` | 分组框主体内容 |
