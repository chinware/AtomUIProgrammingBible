# PopupConfirm 快速入门

### 基础配置条件

* Nuget安装Avalonia
* Nuget安装AtomUI

### 基础用法

`PopupConfirm` 弹窗在业务场景中极其常见，`AtomUI` 提供了一个非常简洁的组件来满足这种业务场景。

将需要触发弹窗的控件作为 `PopupConfirm` 的子元素，设置以下属性即可快速使用：

* `Title`: 弹窗的标题
* `ConfirmContent`: 弹窗内容
* `OkText`: 确认按钮的文字
* `CancelText`: 取消按钮的文字
* `Placement`: 弹窗出现的位置
* `IsShowArrow`: 是否显示箭头

![AtomUI PopupConfirm组件](./images/basic.webp)

axaml文件：
```xaml
<atom:PopupConfirm
    Title="Delete the task"
    ConfirmContent="Are you sure to delete this task?"
    OkText="Ok"
    CancelText="Cancel"
    Placement="Top"
    IsShowArrow="True">
    <atom:Button ButtonType="Default" IsDanger="True">Delete</atom:Button>
</atom:PopupConfirm>
```

### 默认本地语系

当不指定 `OkText` 和 `CancelText` 时，确认按钮和取消按钮将自动使用当前本地化语系的默认文案。

![AtomUI PopupConfirm组件](./images/basic-locale-text.webp)

```xaml
<atom:PopupConfirm
    Title="Delete the task"
    ConfirmContent="Are you sure to delete this task?">
    <atom:Button ButtonType="Default" IsDanger="True">Delete</atom:Button>
</atom:PopupConfirm>
```

### 弹出位置

通过 `Placement` 属性可以指定弹窗相对于触发元素的 12 种弹出位置。

![AtomUI PopupConfirm组件](./images/placement.webp)

```xaml
<Grid>
    <Grid.Styles>
        <Style Selector="atom|Button">
            <Setter Property="Margin" Value="5" />
            <Setter Property="Width" Value="80" />
        </Style>
    </Grid.Styles>
    <Grid.RowDefinitions>
        <RowDefinition Height="Auto" />
        <RowDefinition Height="Auto" />
        <RowDefinition Height="Auto" />
        <RowDefinition Height="Auto" />
        <RowDefinition Height="Auto" />
    </Grid.RowDefinitions>
    <Grid.ColumnDefinitions>
        <ColumnDefinition Width="Auto" />
        <ColumnDefinition Width="Auto" />
        <ColumnDefinition Width="Auto" />
        <ColumnDefinition Width="Auto" />
        <ColumnDefinition Width="Auto" />
    </Grid.ColumnDefinitions>

    <atom:PopupConfirm
        Grid.Row="1" Grid.Column="0" Trigger="Click" Placement="LeftEdgeAlignedTop"
        Title="Delete the task"
        ConfirmContent="Are you sure to delete this task?"
        OkText="Ok"
        CancelText="Cancel">
        <atom:Button ButtonType="Default">LT</atom:Button>
    </atom:PopupConfirm>

    <atom:PopupConfirm
        Grid.Row="2" Grid.Column="0" Trigger="Click" Placement="Left"
        Title="Delete the task"
        ConfirmContent="Are you sure to delete this task?"
        OkText="Ok"
        CancelText="Cancel">
        <atom:Button ButtonType="Default">Left</atom:Button>
    </atom:PopupConfirm>

    <atom:PopupConfirm
        Grid.Row="3" Grid.Column="0" Trigger="Click" Placement="LeftEdgeAlignedBottom"
        Title="Delete the task"
        ConfirmContent="Are you sure to delete this task?"
        OkText="Ok"
        CancelText="Cancel">
        <atom:Button ButtonType="Default">LB</atom:Button>
    </atom:PopupConfirm>

    <atom:PopupConfirm
        Grid.Row="0" Grid.Column="1" Trigger="Click" Placement="TopEdgeAlignedLeft"
        Title="Delete the task"
        ConfirmContent="Are you sure to delete this task?"
        OkText="Ok"
        CancelText="Cancel">
        <atom:Button ButtonType="Default">TL</atom:Button>
    </atom:PopupConfirm>

    <atom:PopupConfirm
        Grid.Row="0" Grid.Column="2" Trigger="Click" Placement="Top"
        Title="Delete the task"
        ConfirmContent="Are you sure to delete this task?"
        OkText="Ok"
        CancelText="Cancel">
        <atom:Button ButtonType="Default">Top</atom:Button>
    </atom:PopupConfirm>

    <atom:PopupConfirm
        Grid.Row="0" Grid.Column="3" Trigger="Click" Placement="TopEdgeAlignedRight"
        Title="Delete the task"
        ConfirmContent="Are you sure to delete this task?"
        OkText="Ok"
        CancelText="Cancel">
        <atom:Button ButtonType="Default">TR</atom:Button>
    </atom:PopupConfirm>

    <atom:PopupConfirm
        Grid.Row="1" Grid.Column="4" Trigger="Click" Placement="RightEdgeAlignedTop"
        Title="Delete the task"
        ConfirmContent="Are you sure to delete this task?"
        OkText="Ok"
        CancelText="Cancel">
        <atom:Button ButtonType="Default">RT</atom:Button>
    </atom:PopupConfirm>

    <atom:PopupConfirm
        Grid.Row="2" Grid.Column="4" Trigger="Click" Placement="Right"
        Title="Delete the task"
        ConfirmContent="Are you sure to delete this task?"
        OkText="Ok"
        CancelText="Cancel">
        <atom:Button ButtonType="Default">Right</atom:Button>
    </atom:PopupConfirm>

    <atom:PopupConfirm
        Grid.Row="3" Grid.Column="4" Trigger="Click" Placement="RightEdgeAlignedBottom"
        Title="Delete the task"
        ConfirmContent="Are you sure to delete this task?"
        OkText="Ok"
        CancelText="Cancel">
        <atom:Button ButtonType="Default">RB</atom:Button>
    </atom:PopupConfirm>

    <atom:PopupConfirm
        Grid.Row="4" Grid.Column="1" Trigger="Click" Placement="BottomEdgeAlignedLeft"
        Title="Delete the task"
        ConfirmContent="Are you sure to delete this task?"
        OkText="Ok"
        CancelText="Cancel">
        <atom:Button ButtonType="Default">BL</atom:Button>
    </atom:PopupConfirm>

    <atom:PopupConfirm
        Grid.Row="4" Grid.Column="2" Trigger="Click" Placement="Bottom"
        Title="Delete the task"
        ConfirmContent="Are you sure to delete this task?"
        OkText="Ok"
        CancelText="Cancel">
        <atom:Button ButtonType="Default">Bottom</atom:Button>
    </atom:PopupConfirm>

    <atom:PopupConfirm
        Grid.Row="4" Grid.Column="3" Trigger="Click" Placement="BottomEdgeAlignedRight"
        Title="Delete the task"
        ConfirmContent="Are you sure to delete this task?"
        OkText="Ok"
        CancelText="Cancel">
        <atom:Button ButtonType="Default">BR</atom:Button>
    </atom:PopupConfirm>

</Grid>
```

### 自定义图标

通过 `Icon` 属性可以自定义弹窗的图标（图标参考 `AtomUI` 的图标库），配合 `ConfirmStatus` 属性可以设置不同语义下的图标配色。

![AtomUI PopupConfirm组件](./images/custom-icon.webp)

```xaml
<atom:PopupConfirm
    Title="Delete the task"
    ConfirmContent="Are you sure to delete this task?"
    Icon="{atom:IconProvider Kind=QuestionCircleOutlined}"
    ConfirmStatus="Error"
    OkText="Ok"
    CancelText="Cancel">
    <atom:Button ButtonType="Default" IsDanger="True">Delete</atom:Button>
</atom:PopupConfirm>
```
