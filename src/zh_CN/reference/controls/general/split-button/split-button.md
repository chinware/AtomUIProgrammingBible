# SplitButton

`AtomUI` 提供了一套分裂按钮组件，即 `SplitButton` 。为按钮提供了更多的扩展性操作空间与能力。分裂按钮是基于 `Flyout` 与 `Menu` 两个基础组件构建的。

## 用例

### 基本用法

![](./images/basic-split-button.webp)

```xml
<atom:SplitButton TriggerType="Hover">
    Hover me
    <atom:SplitButton.Flyout>
        <atom:MenuFlyout>
            <atom:MenuItem Header="Cut" InputGesture="Ctrl+X"
                           Icon="{atom:IconProvider Kind=ScissorOutlined}" />
            <atom:MenuItem Header="Copy" InputGesture="Ctrl+C" Icon="{atom:IconProvider Kind=CopyOutlined}" />
            <atom:MenuItem Header="Delete" InputGesture="Ctrl+D"
                           Icon="{atom:IconProvider Kind=DeleteOutlined}" />
        </atom:MenuFlyout>
    </atom:SplitButton.Flyout>
</atom:SplitButton>
```

### 尺寸用例

![](./images/split-button-size.webp)

分裂按钮的尺寸由 `SizeType` 属性决定，一共有Large、Middle、Small三个值；默认为Middle。

```xml
<atom:SplitButton SizeType="Large">
    Large
    <atom:SplitButton.Flyout>
        <atom:MenuFlyout>
            <atom:MenuItem Header="Cut" InputGesture="Ctrl+X"
                           Icon="{atom:IconProvider Kind=ScissorOutlined}" />
            <atom:MenuItem Header="Copy" InputGesture="Ctrl+C"
                           Icon="{atom:IconProvider Kind=CopyOutlined}" />
            <atom:MenuItem Header="Delete" InputGesture="Ctrl+D"
                           Icon="{atom:IconProvider Kind=DeleteOutlined}" />
        </atom:MenuFlyout>
    </atom:SplitButton.Flyout>
</atom:SplitButton>
<atom:SplitButton SizeType="Middle">
    Middle
    <atom:SplitButton.Flyout>
        <atom:MenuFlyout>
            <atom:MenuItem Header="Cut" InputGesture="Ctrl+X"
                           Icon="{atom:IconProvider Kind=ScissorOutlined}" />
            <atom:MenuItem Header="Copy" InputGesture="Ctrl+C"
                           Icon="{atom:IconProvider Kind=CopyOutlined}" />
            <atom:MenuItem Header="Delete" InputGesture="Ctrl+D"
                           Icon="{atom:IconProvider Kind=DeleteOutlined}" />
        </atom:MenuFlyout>
    </atom:SplitButton.Flyout>
</atom:SplitButton>
<atom:SplitButton SizeType="Small">
    Small
    <atom:SplitButton.Flyout>
        <atom:MenuFlyout>
            <atom:MenuItem Header="Cut" InputGesture="Ctrl+X"
                           Icon="{atom:IconProvider Kind=ScissorOutlined}" />
            <atom:MenuItem Header="Copy" InputGesture="Ctrl+C"
                           Icon="{atom:IconProvider Kind=CopyOutlined}" />
            <atom:MenuItem Header="Delete" InputGesture="Ctrl+D"
                           Icon="{atom:IconProvider Kind=DeleteOutlined}" />
        </atom:MenuFlyout>
    </atom:SplitButton.Flyout>
</atom:SplitButton>
```

### 危险用例

![](./images/danger-split-button.webp)

分裂菜单的危险属性由 `IsDanger` 属性决定，一共有True和False两个值；默认为False。

```xml
<atom:SplitButton IsDanger="true">
    Default
    <atom:SplitButton.Flyout>
        <atom:MenuFlyout>
            <atom:MenuItem Header="Cut" InputGesture="Ctrl+X"
                           Icon="{atom:IconProvider Kind=ScissorOutlined}" />
            <atom:MenuItem Header="Copy" InputGesture="Ctrl+C"
                           Icon="{atom:IconProvider Kind=CopyOutlined}" />
            <atom:MenuItem Header="Delete" InputGesture="Ctrl+D"
                           Icon="{atom:IconProvider Kind=DeleteOutlined}" />
        </atom:MenuFlyout>
    </atom:SplitButton.Flyout>
</atom:SplitButton>

<atom:SplitButton IsDanger="true" IsPrimaryButtonType="True">
    Primary
    <atom:SplitButton.Flyout>
        <atom:MenuFlyout>
            <atom:MenuItem Header="Cut" InputGesture="Ctrl+X"
                           Icon="{atom:IconProvider Kind=ScissorOutlined}" />
            <atom:MenuItem Header="Copy" InputGesture="Ctrl+C"
                           Icon="{atom:IconProvider Kind=CopyOutlined}" />
            <atom:MenuItem Header="Delete" InputGesture="Ctrl+D"
                           Icon="{atom:IconProvider Kind=DeleteOutlined}" />
        </atom:MenuFlyout>
    </atom:SplitButton.Flyout>
</atom:SplitButton>
```

### 自定义图标用例

![](./images/custom-split-button.webp)

分裂菜单的图标由 `Icon` 属性决定，而 `Icon` 也是由 `AtomUI` 提供的基础组件，详情参考 `Icon` 章节。

```xml
<atom:SplitButton>
    Default
    <atom:SplitButton.Flyout>
        <atom:MenuFlyout>
            <atom:MenuItem Header="Cut" InputGesture="Ctrl+X"
                           Icon="{atom:IconProvider Kind=ScissorOutlined}" />
            <atom:MenuItem Header="Copy" InputGesture="Ctrl+C"
                           Icon="{atom:IconProvider Kind=CopyOutlined}" />
            <atom:MenuItem Header="Delete" InputGesture="Ctrl+D"
                           Icon="{atom:IconProvider Kind=DeleteOutlined}" />
        </atom:MenuFlyout>
    </atom:SplitButton.Flyout>
</atom:SplitButton>

<atom:SplitButton FlyoutButtonIcon="{atom:IconProvider Kind=UserOutlined}">
    Primary
    <atom:SplitButton.Flyout>
        <atom:MenuFlyout>
            <atom:MenuItem Header="Cut" InputGesture="Ctrl+X"
                           Icon="{atom:IconProvider Kind=ScissorOutlined}" />
            <atom:MenuItem Header="Copy" InputGesture="Ctrl+C"
                           Icon="{atom:IconProvider Kind=CopyOutlined}" />
            <atom:MenuItem Header="Delete" InputGesture="Ctrl+D"
                           Icon="{atom:IconProvider Kind=DeleteOutlined}" />
        </atom:MenuFlyout>
    </atom:SplitButton.Flyout>
</atom:SplitButton>
```

### 触发方式用例

![](./images/trigger-split-button.webp)

分裂按钮的触发方式由 `TriggerType` 确定，一共有Click和Hover两个值；默认为Click。

```xml
<atom:SplitButton TriggerType="Hover">
    Hover Me
    <atom:SplitButton.Flyout>
        <atom:MenuFlyout>
            <atom:MenuItem Header="Cut" InputGesture="Ctrl+X"
                           Icon="{atom:IconProvider Kind=ScissorOutlined}" />
            <atom:MenuItem Header="Copy" InputGesture="Ctrl+C"
                           Icon="{atom:IconProvider Kind=CopyOutlined}" />
            <atom:MenuItem Header="Delete" InputGesture="Ctrl+D"
                           Icon="{atom:IconProvider Kind=DeleteOutlined}" />
        </atom:MenuFlyout>
    </atom:SplitButton.Flyout>
</atom:SplitButton>

<atom:SplitButton FlyoutButtonIcon="{atom:IconProvider Kind=UserOutlined}" TriggerType="Click">
    Click Me
    <atom:SplitButton.Flyout>
        <atom:MenuFlyout>
            <atom:MenuItem Header="Cut" InputGesture="Ctrl+X"
                           Icon="{atom:IconProvider Kind=ScissorOutlined}" />
            <atom:MenuItem Header="Copy" InputGesture="Ctrl+C"
                           Icon="{atom:IconProvider Kind=CopyOutlined}" />
            <atom:MenuItem Header="Delete" InputGesture="Ctrl+D"
                           Icon="{atom:IconProvider Kind=DeleteOutlined}" />
        </atom:MenuFlyout>
    </atom:SplitButton.Flyout>
</atom:SplitButton>
```

## 属性

| 属性 | 说明         |                                           类型                                            |           默认值            |
|:----:|:-----------|:---------------------------------------------------------------------------------------:|:------------------------:|
| `Command` | 命令绑定       |                                       `ICommand?`                                       |          `null`          |
| `CommandParameter` | 命令参数       |                                        `object?`                                        |          `null`          |
| `Flyout` | 弹出菜单内容     |                                        `Flyout?`                                        |          `null`          |
| `HotKey` | 快捷键        |                                      `KeyGesture?`                                      |          `null`          |
| `TriggerType` | Flyout触发方式 |                            `FlyoutTriggerType : Hover,Click`                            |         `Click`          |
| `IsShowArrow` | 是否显示箭头     |                                         `bool`                                          |         `False`          |
| `IsPointAtCenter` | 弹出菜单是否居中对齐 |                                         `bool`                                          |         `false`          |
| `Placement` | 弹出菜单位置模式   |              `PlacementMode`，参考 `Avalonia.Controls` 下的 `PlacementMode` 枚举               | `BottomEdgeAlignedRight` |
| `PlacementAnchor` | 弹出锚点       |  `PopupAnchor` ，参考 `Avalonia.Controls.Primitives.PopupPositioning` 下的 `PopupAnchor` 枚举  |    `PopupAnchor.None`    |
| `PlacementGravity` | 弹出吸附方向     | `PopupGravity` ，参考 `Avalonia.Controls.Primitives.PopupPositioning` 下的 `PopupGravity` 枚举 |   `PopupGravity.None`    |
| `MarginToAnchor` | 弹出与锚点的边距   |                                        `double`                                         |          `0.0`           |
| `MouseEnterDelay` | 鼠标移入延迟     |                                          `int`                                          |          `200`           |
| `MouseLeaveDelay` | 鼠标移出延迟     |                                          `int`                                          |          `200`           |
| `IsShowIndicator` | 是否显示指示器    |                                         `bool`                                          |         `False`          |
| `SizeType` | 尺寸类型       |                             `SizeType : Large,Middle,Small`                             |         `Medium`         |
| `Icon` | 主按钮图标      |                                         `Icon?`                                         |          `null`          |
| `FlyoutButtonIcon` | 副按钮图标      |                                         `Icon?`                                         |   `EllipsisOutlined()`   |
| `IsDanger` | 是否危险样式     |                                         `bool`                                          |         `False`          |
| `IsPrimaryButtonType` | 是否主按钮样式    |                                         `bool`                                          |         `False`          |
| `IsMotionEnabled` | 是否启用动效     |                                         `bool`                                          |          `True`          |
| `IsWaveSpiritEnabled` | 是否启用水波动画   |                                         `bool`                                          |          `True`          |