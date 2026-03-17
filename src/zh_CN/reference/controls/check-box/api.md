# CheckBox API

## 类定义

```
AtomUI.Controls.CheckBox : Avalonia.Controls.CheckBox
```

`CheckBox` 继承自 Avalonia 原生的 `Avalonia.Controls.CheckBox`，在其基础上扩展了动效和波纹效果控制。

---

## AtomUI 扩展属性

以下属性由 `AtomUI.Controls.CheckBox` 新增：

| 属性名 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| `IsMotionEnabled` | `bool` | `true` | 是否启用状态切换动效 |
| `IsWaveSpiritEnabled` | `bool` | `true` | 是否启用点击时的波纹扩散效果 |

---

## 继承属性（来自 Avalonia.Controls.CheckBox）

以下为常用的继承属性：

| 属性名 | 类型 | 默认值 | 说明 |
|--------|------|--------|------|
| `IsChecked` | `bool?` | `false` | 选中状态。`true` 为选中，`false` 为未选中，`null` 为不确定（半选）状态 |
| `IsEnabled` | `bool` | `true` | 是否启用控件。设为 `false` 时控件不可交互 |
| `Content` | `object?` | `null` | 复选框旁边显示的内容，通常为文本标签 |
| `IsThreeState` | `bool` | `false` | 是否允许三态切换。启用后用户点击可在选中、未选中、不确定三种状态间循环 |

---

## 用法示例

### 基础绑定

```xaml
<atom:CheckBox IsChecked="{Binding IsAgree}">我已阅读并同意</atom:CheckBox>
```

### 关闭动效

```xaml
<atom:CheckBox IsMotionEnabled="False"
               IsWaveSpiritEnabled="False">
    无动效复选框
</atom:CheckBox>
```

### 三态模式

```xaml
<atom:CheckBox IsThreeState="True"
               IsChecked="{Binding SelectionState}">
    全选
</atom:CheckBox>
```
