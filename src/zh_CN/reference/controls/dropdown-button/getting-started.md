# 快速入门

### 基础配置条件

* Nuget 安装 Avalonia
* Nuget 安装 AtomUI

### 基础用法

通过 `DropdownFlyout` 属性为按钮指定一个 `MenuFlyout` 下拉菜单。`ButtonType` 设置按钮类型，`TriggerType` 设置菜单的触发方式，可选值有 `Click` 和 `Hover`。

需要注意的是，`atom:MenuItem` 的 `InputGesture` 属性仅用于展示快捷键文案，并不会真正绑定快捷键功能。

![AtomUI DropdownButton组件](./images/basic.webp)

```xaml
<atom:DropdownButton ButtonType="Link" TriggerType="Hover" x:Name="Test">
    Hover me
    <atom:DropdownButton.DropdownFlyout>
        <atom:MenuFlyout>
            <atom:MenuItem Header="Cut" InputGesture="Ctrl+X"
                           Icon="{atom:IconProvider Kind=ScissorOutlined}" />
            <atom:MenuItem Header="Copy" InputGesture="Ctrl+C"
                           Icon="{atom:IconProvider Kind=CopyOutlined}" />
            <atom:MenuItem Header="Delete" InputGesture="Ctrl+D"
                           Icon="{atom:IconProvider Kind=DeleteOutlined}" />
            <atom:MenuItem Header="Paste">
                <atom:MenuItem Header="Paste" InputGesture="Ctrl+P"
                               Icon="{atom:IconProvider Kind=FileDoneOutlined}" />
                <atom:MenuItem Header="Paste from History" InputGesture="Ctrl+Shift+V" />
            </atom:MenuItem>
        </atom:MenuFlyout>
    </atom:DropdownButton.DropdownFlyout>
</atom:DropdownButton>
```

### 按钮类型

`ButtonType` 提供了 `Default`、`Dashed`、`Primary`、`Link`、`Text` 五个可选值。`Shape` 属性设置按钮形状，可选值有 `Default`、`Circle`、`Round`。

![AtomUI DropdownButton组件](./images/button-type.webp)

```xaml
<StackPanel Orientation="Horizontal" Spacing="10">
    <atom:DropdownButton ButtonType="Primary" TriggerType="Click">
        Edit File
        <atom:DropdownButton.DropdownFlyout>
            <atom:MenuFlyout>
                <atom:MenuItem Header="Cut" InputGesture="Ctrl+X"
                               Icon="{atom:IconProvider Kind=ScissorOutlined}" />
                <atom:MenuItem Header="Copy" InputGesture="Ctrl+C"
                               Icon="{atom:IconProvider Kind=CopyOutlined}" />
                <atom:MenuItem Header="Delete" InputGesture="Ctrl+D"
                               Icon="{atom:IconProvider Kind=DeleteOutlined}" />
                <atom:MenuItem Header="Paste">
                    <atom:MenuItem Header="Paste" InputGesture="Ctrl+P"
                                   Icon="{atom:IconProvider Kind=FileDoneOutlined}" />
                    <atom:MenuItem Header="Paste from History" InputGesture="Ctrl+Shift+V" />
                </atom:MenuItem>
            </atom:MenuFlyout>
        </atom:DropdownButton.DropdownFlyout>
    </atom:DropdownButton>

    <atom:DropdownButton ButtonType="Primary" Shape="Round" TriggerType="Click">
        Edit File
        <atom:DropdownButton.DropdownFlyout>
            <atom:MenuFlyout>
                <atom:MenuItem Header="Cut" InputGesture="Ctrl+X"
                               Icon="{atom:IconProvider Kind=ScissorOutlined}" />
                <atom:MenuItem Header="Copy" InputGesture="Ctrl+C"
                               Icon="{atom:IconProvider Kind=CopyOutlined}" />
                <atom:MenuItem Header="Delete" InputGesture="Ctrl+D"
                               Icon="{atom:IconProvider Kind=DeleteOutlined}" />
            </atom:MenuFlyout>
        </atom:DropdownButton.DropdownFlyout>
    </atom:DropdownButton>

    <atom:DropdownButton ButtonType="Default" TriggerType="Click">
        Edit File
        <atom:DropdownButton.DropdownFlyout>
            <atom:MenuFlyout>
                <atom:MenuItem Header="Cut" InputGesture="Ctrl+X"
                               Icon="{atom:IconProvider Kind=ScissorOutlined}" />
                <atom:MenuItem Header="Copy" InputGesture="Ctrl+C"
                               Icon="{atom:IconProvider Kind=CopyOutlined}" />
                <atom:MenuItem Header="Delete" InputGesture="Ctrl+D"
                               Icon="{atom:IconProvider Kind=DeleteOutlined}" />
            </atom:MenuFlyout>
        </atom:DropdownButton.DropdownFlyout>
    </atom:DropdownButton>

    <atom:DropdownButton ButtonType="Text" TriggerType="Click">
        Edit File
        <atom:DropdownButton.DropdownFlyout>
            <atom:MenuFlyout>
                <atom:MenuItem Header="Cut" InputGesture="Ctrl+X"
                               Icon="{atom:IconProvider Kind=ScissorOutlined}" />
                <atom:MenuItem Header="Copy" InputGesture="Ctrl+C"
                               Icon="{atom:IconProvider Kind=CopyOutlined}" />
                <atom:MenuItem Header="Delete" InputGesture="Ctrl+D"
                               Icon="{atom:IconProvider Kind=DeleteOutlined}" />
            </atom:MenuFlyout>
        </atom:DropdownButton.DropdownFlyout>
    </atom:DropdownButton>
</StackPanel>
```

### 箭头设定

通过 `IsShowArrow` 属性控制下拉菜单是否显示箭头指示。设置 `IsPointAtCenter` 可以让箭头指向锚点的中心位置。

![AtomUI DropdownButton组件](./images/arrow.webp)

```xaml
<WrapPanel>
    <atom:DropdownButton ButtonType="Default" TriggerType="Hover"
                         IsShowArrow="True" Placement="BottomEdgeAlignedLeft">
        BottomLeft
        <atom:DropdownButton.DropdownFlyout>
            <atom:MenuFlyout>
                <atom:MenuItem Header="Cut" InputGesture="Ctrl+X"
                               Icon="{atom:IconProvider Kind=ScissorOutlined}" />
                <atom:MenuItem Header="Copy" InputGesture="Ctrl+C"
                               Icon="{atom:IconProvider Kind=CopyOutlined}" />
                <atom:MenuItem Header="Delete" InputGesture="Ctrl+D"
                               Icon="{atom:IconProvider Kind=DeleteOutlined}" />
            </atom:MenuFlyout>
        </atom:DropdownButton.DropdownFlyout>
    </atom:DropdownButton>

    <atom:DropdownButton ButtonType="Default" TriggerType="Hover"
                         IsShowArrow="True" Placement="Bottom">
        Bottom
        <atom:DropdownButton.DropdownFlyout>
            <atom:MenuFlyout>
                <atom:MenuItem Header="Cut" InputGesture="Ctrl+X"
                               Icon="{atom:IconProvider Kind=ScissorOutlined}" />
                <atom:MenuItem Header="Copy" InputGesture="Ctrl+C"
                               Icon="{atom:IconProvider Kind=CopyOutlined}" />
                <atom:MenuItem Header="Delete" InputGesture="Ctrl+D"
                               Icon="{atom:IconProvider Kind=DeleteOutlined}" />
            </atom:MenuFlyout>
        </atom:DropdownButton.DropdownFlyout>
    </atom:DropdownButton>

    <atom:DropdownButton ButtonType="Default" TriggerType="Hover"
                         IsShowArrow="True" Placement="BottomEdgeAlignedRight">
        BottomRight
        <atom:DropdownButton.DropdownFlyout>
            <atom:MenuFlyout>
                <atom:MenuItem Header="Cut" InputGesture="Ctrl+X"
                               Icon="{atom:IconProvider Kind=ScissorOutlined}" />
                <atom:MenuItem Header="Copy" InputGesture="Ctrl+C"
                               Icon="{atom:IconProvider Kind=CopyOutlined}" />
                <atom:MenuItem Header="Delete" InputGesture="Ctrl+D"
                               Icon="{atom:IconProvider Kind=DeleteOutlined}" />
            </atom:MenuFlyout>
        </atom:DropdownButton.DropdownFlyout>
    </atom:DropdownButton>

    <atom:DropdownButton ButtonType="Default" TriggerType="Hover"
                         IsShowArrow="True" Placement="TopEdgeAlignedLeft">
        TopLeft
        <atom:DropdownButton.DropdownFlyout>
            <atom:MenuFlyout>
                <atom:MenuItem Header="Cut" InputGesture="Ctrl+X"
                               Icon="{atom:IconProvider Kind=ScissorOutlined}" />
                <atom:MenuItem Header="Copy" InputGesture="Ctrl+C"
                               Icon="{atom:IconProvider Kind=CopyOutlined}" />
                <atom:MenuItem Header="Delete" InputGesture="Ctrl+D"
                               Icon="{atom:IconProvider Kind=DeleteOutlined}" />
            </atom:MenuFlyout>
        </atom:DropdownButton.DropdownFlyout>
    </atom:DropdownButton>

    <atom:DropdownButton ButtonType="Default" TriggerType="Hover"
                         IsShowArrow="True" Placement="Top">
        Top
        <atom:DropdownButton.DropdownFlyout>
            <atom:MenuFlyout>
                <atom:MenuItem Header="Cut" InputGesture="Ctrl+X"
                               Icon="{atom:IconProvider Kind=ScissorOutlined}" />
                <atom:MenuItem Header="Copy" InputGesture="Ctrl+C"
                               Icon="{atom:IconProvider Kind=CopyOutlined}" />
                <atom:MenuItem Header="Delete" InputGesture="Ctrl+D"
                               Icon="{atom:IconProvider Kind=DeleteOutlined}" />
            </atom:MenuFlyout>
        </atom:DropdownButton.DropdownFlyout>
    </atom:DropdownButton>

    <atom:DropdownButton ButtonType="Default" TriggerType="Hover"
                         IsShowArrow="True" Placement="TopEdgeAlignedRight">
        TopRight
        <atom:DropdownButton.DropdownFlyout>
            <atom:MenuFlyout>
                <atom:MenuItem Header="Cut" InputGesture="Ctrl+X"
                               Icon="{atom:IconProvider Kind=ScissorOutlined}" />
                <atom:MenuItem Header="Copy" InputGesture="Ctrl+C"
                               Icon="{atom:IconProvider Kind=CopyOutlined}" />
                <atom:MenuItem Header="Delete" InputGesture="Ctrl+D"
                               Icon="{atom:IconProvider Kind=DeleteOutlined}" />
            </atom:MenuFlyout>
        </atom:DropdownButton.DropdownFlyout>
    </atom:DropdownButton>
</WrapPanel>
```

### 触发位置

`Placement` 属性设置下拉菜单的弹出位置。常用可选值包括 `BottomEdgeAlignedLeft`、`Bottom`、`BottomEdgeAlignedRight`、`TopEdgeAlignedLeft`、`Top`、`TopEdgeAlignedRight`。还可以通过 `PlacementAnchor` 和 `PlacementGravity` 进行更精细的定位控制。

![AtomUI DropdownButton组件](./images/placement.webp)

```xaml
<WrapPanel>
    <atom:DropdownButton ButtonType="Default" TriggerType="Hover"
                         Placement="BottomEdgeAlignedLeft">
        BottomLeft
        <atom:DropdownButton.DropdownFlyout>
            <atom:MenuFlyout>
                <atom:MenuItem Header="Cut" InputGesture="Ctrl+X"
                               Icon="{atom:IconProvider Kind=ScissorOutlined}" />
                <atom:MenuItem Header="Copy" InputGesture="Ctrl+C"
                               Icon="{atom:IconProvider Kind=CopyOutlined}" />
                <atom:MenuItem Header="Delete" InputGesture="Ctrl+D"
                               Icon="{atom:IconProvider Kind=DeleteOutlined}" />
            </atom:MenuFlyout>
        </atom:DropdownButton.DropdownFlyout>
    </atom:DropdownButton>

    <atom:DropdownButton ButtonType="Default" TriggerType="Hover"
                         Placement="Bottom">
        Bottom
        <atom:DropdownButton.DropdownFlyout>
            <atom:MenuFlyout>
                <atom:MenuItem Header="Cut" InputGesture="Ctrl+X"
                               Icon="{atom:IconProvider Kind=ScissorOutlined}" />
                <atom:MenuItem Header="Copy" InputGesture="Ctrl+C"
                               Icon="{atom:IconProvider Kind=CopyOutlined}" />
                <atom:MenuItem Header="Delete" InputGesture="Ctrl+D"
                               Icon="{atom:IconProvider Kind=DeleteOutlined}" />
            </atom:MenuFlyout>
        </atom:DropdownButton.DropdownFlyout>
    </atom:DropdownButton>

    <atom:DropdownButton ButtonType="Default" TriggerType="Hover"
                         Placement="BottomEdgeAlignedRight">
        BottomRight
        <atom:DropdownButton.DropdownFlyout>
            <atom:MenuFlyout>
                <atom:MenuItem Header="Cut" InputGesture="Ctrl+X"
                               Icon="{atom:IconProvider Kind=ScissorOutlined}" />
                <atom:MenuItem Header="Copy" InputGesture="Ctrl+C"
                               Icon="{atom:IconProvider Kind=CopyOutlined}" />
                <atom:MenuItem Header="Delete" InputGesture="Ctrl+D"
                               Icon="{atom:IconProvider Kind=DeleteOutlined}" />
            </atom:MenuFlyout>
        </atom:DropdownButton.DropdownFlyout>
    </atom:DropdownButton>

    <atom:DropdownButton ButtonType="Default" TriggerType="Hover"
                         Placement="TopEdgeAlignedLeft">
        TopLeft
        <atom:DropdownButton.DropdownFlyout>
            <atom:MenuFlyout>
                <atom:MenuItem Header="Cut" InputGesture="Ctrl+X"
                               Icon="{atom:IconProvider Kind=ScissorOutlined}" />
                <atom:MenuItem Header="Copy" InputGesture="Ctrl+C"
                               Icon="{atom:IconProvider Kind=CopyOutlined}" />
                <atom:MenuItem Header="Delete" InputGesture="Ctrl+D"
                               Icon="{atom:IconProvider Kind=DeleteOutlined}" />
            </atom:MenuFlyout>
        </atom:DropdownButton.DropdownFlyout>
    </atom:DropdownButton>

    <atom:DropdownButton ButtonType="Default" TriggerType="Hover"
                         Placement="Top">
        Top
        <atom:DropdownButton.DropdownFlyout>
            <atom:MenuFlyout>
                <atom:MenuItem Header="Cut" InputGesture="Ctrl+X"
                               Icon="{atom:IconProvider Kind=ScissorOutlined}" />
                <atom:MenuItem Header="Copy" InputGesture="Ctrl+C"
                               Icon="{atom:IconProvider Kind=CopyOutlined}" />
                <atom:MenuItem Header="Delete" InputGesture="Ctrl+D"
                               Icon="{atom:IconProvider Kind=DeleteOutlined}" />
            </atom:MenuFlyout>
        </atom:DropdownButton.DropdownFlyout>
    </atom:DropdownButton>

    <atom:DropdownButton ButtonType="Default" TriggerType="Hover"
                         Placement="TopEdgeAlignedRight">
        TopRight
        <atom:DropdownButton.DropdownFlyout>
            <atom:MenuFlyout>
                <atom:MenuItem Header="Cut" InputGesture="Ctrl+X"
                               Icon="{atom:IconProvider Kind=ScissorOutlined}" />
                <atom:MenuItem Header="Copy" InputGesture="Ctrl+C"
                               Icon="{atom:IconProvider Kind=CopyOutlined}" />
                <atom:MenuItem Header="Delete" InputGesture="Ctrl+D"
                               Icon="{atom:IconProvider Kind=DeleteOutlined}" />
            </atom:MenuFlyout>
        </atom:DropdownButton.DropdownFlyout>
    </atom:DropdownButton>
</WrapPanel>
```
