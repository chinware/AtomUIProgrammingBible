# 图标

`Alert` 组件可以在显示文本与描述的同时，开启 `IsShowIcon` 特性打开图标功能，提供被用户感知的能力。

![AtomUI Alert图标](./images/description-with-icon.png)

```xaml
<StackPanel Orientation="Vertical" Spacing="10">
    <atom:Alert Type="Success"
                Message="Success Tips"
                IsShowIcon="True" />
    <atom:Alert Type="Info"
                Message="Informational Notes"
                IsShowIcon="True" />
    <atom:Alert Type="Warning"
                Message="Warning"
                IsShowIcon="True"
                IsClosable="True" />
    <atom:Alert Type="Error"
                Message="Error"
                IsShowIcon="True" />

    <atom:Alert Type="Success"
                Message="Success Tips"
                IsShowIcon="True"
                Description="Detailed description and advice about successful copywriting." />
    <atom:Alert Type="Info"
                Message="Informational Notes"
                IsShowIcon="True"
                Description="Additional description and information about copywriting." />
    <atom:Alert Type="Warning"
                Message="Warning"
                IsClosable="True"
                IsShowIcon="True"
                Description="This is a warning notice about copywriting." />
    <atom:Alert Type="Error"
                Message="Error"
                IsShowIcon="True"
                Description="This is an error message about copywriting." />
</StackPanel>
```