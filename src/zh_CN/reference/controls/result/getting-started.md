# Result 快速入门

### 基础配置条件

* Nuget 安装 Avalonia
* Nuget 安装 AtomUI

在下面的文档中，以不同业务场景作为分类，介绍如何使用 `Result` 组件。

### Success 成功

一个典型的 `Result` 组件主要由以下四个属性组成：
* `Status`：结果状态，默认为 `Success`。
* `Header`：标题文本，用于展示结果的主要信息。
* `SubHeader`：副标题文本，用于展示补充说明。
* `Extra`：额外操作区域，开发者可以在其中放置按钮等交互元素。

![AtomUI Result组件](./images/success.png)

```xaml
<atom:Result Status="Success"
             Header="Successfully Purchased Cloud Server ECS!"
             SubHeader="Order number: 2017182818828182881 Cloud server configuration takes 1-5 minutes, please wait.">
    <atom:Result.Extra>
        <StackPanel Orientation="Horizontal" Spacing="10">
            <atom:Button ButtonType="Primary">Go Console</atom:Button>
            <atom:Button>Buy Again</atom:Button>
        </StackPanel>
    </atom:Result.Extra>
</atom:Result>
```

### Info 信息

将 `Status` 设置为 `Info`，展示一般性信息提示。

![AtomUI Result组件](./images/info.png)

```xaml
<atom:Result Status="Info"
             Header="Your operation has been executed.">
    <atom:Result.Extra>
        <atom:Button ButtonType="Primary">Go Console</atom:Button>
    </atom:Result.Extra>
</atom:Result>
```

### Warning 警告

将 `Status` 设置为 `Warning`，展示警告类结果。

![AtomUI Result组件](./images/warning.png)

```xaml
<atom:Result Status="Warning"
             Header="There are some problems with your operation.">
    <atom:Result.Extra>
        <atom:Button ButtonType="Primary">Go Console</atom:Button>
    </atom:Result.Extra>
</atom:Result>
```

### Error 错误

将 `Status` 设置为 `Error`，展示操作失败的结果。`Result` 继承自 `ContentControl`，其 `Content` 区域可以放置自定义的详细错误信息。

![AtomUI Result组件](./images/error.png)

```xaml
<atom:Result Status="Error"
             Header="Submission Failed"
             SubHeader="Please check and modify the following information before resubmitting.">
    <atom:Result.Extra>
        <StackPanel Orientation="Horizontal" Spacing="10">
            <atom:Button ButtonType="Primary">Go Console</atom:Button>
            <atom:Button>Buy Again</atom:Button>
        </StackPanel>
    </atom:Result.Extra>
    <StackPanel Spacing="8">
        <TextBlock FontWeight="Bold" FontSize="16">
            The content you submitted has the following error:
        </TextBlock>

        <StackPanel Orientation="Horizontal" Spacing="8">
            <antdicons:CloseCircleOutlined Foreground="{DynamicResource {x:Static atom:SharedTokenKey.ColorError}}"/>
            <TextBlock>Your account has been frozen. </TextBlock>
            <TextBlock Foreground="{DynamicResource {x:Static atom:SharedTokenKey.ColorPrimary}}">Thaw immediately ></TextBlock>
        </StackPanel>

        <StackPanel Orientation="Horizontal" Spacing="8">
            <antdicons:CloseCircleOutlined Foreground="{DynamicResource {x:Static atom:SharedTokenKey.ColorError}}"/>
            <TextBlock>Your account is not yet eligible to apply. </TextBlock>
            <TextBlock Foreground="{DynamicResource {x:Static atom:SharedTokenKey.ColorPrimary}}">Apply Unlock ></TextBlock>
        </StackPanel>
    </StackPanel>
</atom:Result>
```

### HTTP 错误码 403/404/500

`Result` 内置了常见 HTTP 错误码的展示样式，分别对应 `ErrorCode403`、`ErrorCode404` 和 `ErrorCode500` 三种状态，每种状态都配有专属的插画图标。

![AtomUI Result组件](./images/403.png)

![AtomUI Result组件](./images/404.png)

![AtomUI Result组件](./images/500.png)

```xaml
<atom:Result Status="ErrorCode403"
             Header="403"
             SubHeader="Sorry, you are not authorized to access this page.">
    <atom:Result.Extra>
        <atom:Button ButtonType="Primary">Back Home</atom:Button>
    </atom:Result.Extra>
</atom:Result>

<atom:Result Status="ErrorCode404"
             Header="404"
             SubHeader="Sorry, the page you visited does not exist.">
    <atom:Result.Extra>
        <atom:Button ButtonType="Primary">Back Home</atom:Button>
    </atom:Result.Extra>
</atom:Result>

<atom:Result Status="ErrorCode500"
             Header="500"
             SubHeader="Sorry, something went wrong.">
    <atom:Result.Extra>
        <atom:Button ButtonType="Primary">Back Home</atom:Button>
    </atom:Result.Extra>
</atom:Result>
```

### 自定义图标

通过 `Icon` 属性，开发者可以自定义结果页面的图标。图标默认使用 `antdicons` 提供的图标库。

![AtomUI Result组件](./images/custom.png)

```xaml
<atom:Result Status="Info"
             Icon="{antdicons:AntDesignIconProvider SmileOutlined}"
             Header="Great, we have done all the operations!">
    <atom:Result.Extra>
        <atom:Button ButtonType="Primary">Next</atom:Button>
    </atom:Result.Extra>
</atom:Result>
```
