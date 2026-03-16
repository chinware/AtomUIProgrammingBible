# API 参考

### 类定义

```
BoxPanel : Panel
```

`BoxPanel` 继承自 Avalonia 的 `Panel` 类，提供基于 Flexbox 模型的弹性布局能力。

---

### 属性

| 属性 | 类型 | 默认值 | 说明 |
| --- | --- | --- | --- |
| `Orientation` | `Orientation` | `Vertical` | 子元素的排列方向。`Vertical` 为垂直排列，`Horizontal` 为水平排列。 |
| `Spacing` | `double` | `0.0` | 子元素之间的统一间距。当设置了 `ColumnSpacing` 或 `RowSpacing` 时，对应方向的间距将被覆盖。 |
| `JustifyContent` | `JustifyContent` | `FlexStart` | 子元素在主轴方向上的分布方式。可选值：`FlexStart`、`FlexEnd`、`Center`、`SpaceBetween`、`SpaceAround`、`SpaceEvenly`。 |
| `AlignItems` | `AlignItems` | `Stretch` | 子元素在交叉轴方向上的默认对齐方式。可选值：`Stretch`、`FlexStart`、`FlexEnd`、`Center`。 |
| `AlignContent` | `AlignContent` | `FlexStart` | 多行内容在交叉轴方向上的分布方式（仅在 `Wrap` 启用时生效）。可选值：`FlexStart`、`FlexEnd`、`Center`、`SpaceBetween`、`SpaceAround`、`Stretch`。 |
| `Wrap` | `FlexWrap` | `NoWrap` | 子元素是否在空间不足时自动换行。可选值：`NoWrap`、`Wrap`、`WrapReverse`。 |
| `ColumnSpacing` | `double` | `NaN` | 列间距（水平方向的元素间距）。设置后覆盖 `Spacing` 在水平方向的值。`NaN` 表示使用 `Spacing` 的值。 |
| `RowSpacing` | `double` | `NaN` | 行间距（垂直方向的元素间距）。设置后覆盖 `Spacing` 在垂直方向的值。`NaN` 表示使用 `Spacing` 的值。 |

---

### 附加属性

以下属性通过 `atom:BoxPanel.PropertyName` 的方式设置在子元素上。

| 附加属性 | 类型 | 默认值 | 说明 |
| --- | --- | --- | --- |
| `Flex` | `int` | `0` | 子元素的弹性比例。值为 `0` 时元素不参与弹性分配，使用自身尺寸；值大于 `0` 时按比例分配剩余空间。 |
| `Order` | `int` | `0` | 子元素的显示顺序。数值越小排列越靠前，默认按 XAML 中的声明顺序排列。 |
| `AlignSelf` | `AlignItems?` | `null` | 覆盖父容器 `AlignItems` 的对齐方式，为单个子元素指定独立的交叉轴对齐。值为 `null` 时使用父容器的 `AlignItems` 设置。 |

---

### 用法示例

```xaml
<!-- 基础水平布局，子元素按 1:2 比例分配空间 -->
<atom:BoxPanel Orientation="Horizontal" Spacing="10">
    <Panel atom:BoxPanel.Flex="1" Background="Blue" />
    <Panel atom:BoxPanel.Flex="2" Background="Green" />
</atom:BoxPanel>

<!-- 垂直布局，居中对齐，启用换行 -->
<atom:BoxPanel
    Orientation="Vertical"
    JustifyContent="Center"
    AlignItems="Center"
    Wrap="Wrap"
    RowSpacing="8"
    ColumnSpacing="12">
    <Panel atom:BoxPanel.Flex="1" atom:BoxPanel.Order="2" />
    <Panel atom:BoxPanel.Flex="1" atom:BoxPanel.Order="1" />
    <Panel atom:BoxPanel.AlignSelf="FlexEnd" Width="100" Height="50" />
</atom:BoxPanel>
```

---

### 便捷子类

| 类名 | 说明 |
| --- | --- |
| `HBoxPanel` | 预设 `Orientation="Horizontal"` 的 BoxPanel 便捷用法 |
| `VBoxPanel` | 预设 `Orientation="Vertical"` 的 BoxPanel 便捷用法 |

---

### 实例方法

| 方法 | 说明 |
| --- | --- |
| `AddSpacing(double size)` | 向面板中动态添加一个指定大小的固定间距元素 |
| `AddFlex(int flex)` | 向面板中动态添加一个指定弹性比例的占位元素 |

---

### 静态方法

| 方法 | 说明 |
| --- | --- |
| `SetFlex(Control control, int value)` | 设置指定子元素的 Flex 附加属性值 |
| `GetFlex(Control control)` | 获取指定子元素的 Flex 附加属性值 |
| `SetOrder(Control control, int value)` | 设置指定子元素的 Order 附加属性值 |
| `GetOrder(Control control)` | 获取指定子元素的 Order 附加属性值 |
| `SetAlignSelf(Control control, AlignItems? value)` | 设置指定子元素的 AlignSelf 附加属性值 |
| `GetAlignSelf(Control control)` | 获取指定子元素的 AlignSelf 附加属性值 |
