# RadioButton API

## RadioButton

### 类定义

```
AtomUI.Controls.RadioButton : Avalonia.Controls.RadioButton
```

`RadioButton` 继承自 Avalonia 原生的 `Avalonia.Controls.RadioButton`，提供标准的单选按钮功能。

---

### AtomUI 扩展属性

| 属性名 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| `IsMotionEnabled` | `bool` | `true` | 是否启用状态切换动效 |
| `IsWaveSpiritEnabled` | `bool` | `true` | 是否启用点击时的波纹扩散效果 |

---

### 继承属性（来自 Avalonia.Controls.RadioButton）

| 属性名 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| `IsChecked` | `bool?` | `false` | 选中状态。`true` 为选中，`false` 为未选中 |
| `IsEnabled` | `bool` | `true` | 是否启用控件。设为 `false` 时控件不可交互，呈现禁用样式 |
| `Content` | `object?` | `null` | 单选按钮旁边显示的内容，通常为文本标签，也可放置图标等自定义内容 |
| `GroupName` | `string?` | `null` | 单选按钮的分组名称。同一组内的单选按钮互斥 |

---

## OptionButton

### 类定义

```
AtomUI.Controls.OptionButton : Avalonia.Controls.RadioButton
```

`OptionButton` 继承自 `Avalonia.Controls.RadioButton`，以按钮形式呈现单选选项。通常与 `OptionButtonGroup` 搭配使用。

---

### 继承属性（来自 Avalonia.Controls.RadioButton）

| 属性名 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| `IsChecked` | `bool?` | `false` | 选中状态 |
| `IsEnabled` | `bool` | `true` | 是否启用控件 |
| `Content` | `object?` | `null` | 按钮显示的内容 |

---

## OptionButtonGroup

### 类定义

```
AtomUI.Controls.OptionButtonGroup
```

`OptionButtonGroup` 用于包裹一组 `OptionButton`，提供统一的样式和尺寸控制。

---

### 属性

| 属性名 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| `ButtonStyle` | `OptionButtonStyle` | `Outline` | 按钮风格。可选值：`Solid`（填充风格）、`Outline`（描边风格） |
| `SizeType` | `SizeType` | `Middle` | 按钮尺寸。可选值：`Large`、`Middle`、`Small` |

---

## 用法示例

### 基础单选

```xaml
<atom:RadioButton IsChecked="{Binding IsSelected}">选项文本</atom:RadioButton>
```

### 关闭动效

```xaml
<atom:RadioButton IsMotionEnabled="False"
                   IsWaveSpiritEnabled="False">
    无动效单选按钮
</atom:RadioButton>
```

### OptionButton 按钮组

```xaml
<atom:OptionButtonGroup ButtonStyle="Solid" SizeType="Large">
    <atom:OptionButton IsChecked="True">选项一</atom:OptionButton>
    <atom:OptionButton>选项二</atom:OptionButton>
    <atom:OptionButton>选项三</atom:OptionButton>
</atom:OptionButtonGroup>
```
