# 自定义行为

`Alert` 组件允许自定义行为，通过提供 `ExtraAction` 属性，可以开启更多适合场景的自定义行为。

![AtomUI Alert自定义行为](./images/custom-action.png)

```xaml
<StackPanel Orientation="Vertical" Spacing="10">
    <atom:Alert Type="Success"
                IsShowIcon="True"
                IsClosable="true">
        <atom:Alert.ExtraAction>
            <atom:Button ButtonType="Text" SizeType="Small">UNDO</atom:Button>
        </atom:Alert.ExtraAction>
        Success Tips
    </atom:Alert>

    <atom:Alert Type="Error"
                IsShowIcon="True"
                Description="Error Description Error Description Error Description Error Description">
        <atom:Alert.ExtraAction>
            <atom:Button ButtonType="Default" SizeType="Small" IsDanger="True">Detail</atom:Button>
        </atom:Alert.ExtraAction>
        Error Text
    </atom:Alert>

    <atom:Alert Type="Warning"
                IsClosable="true">
        <atom:Alert.ExtraAction>
            <atom:Button ButtonType="Text" SizeType="Small">Done</atom:Button>
        </atom:Alert.ExtraAction>
        Warning Text
    </atom:Alert>

    <atom:Alert Type="Info"
                IsShowIcon="False"
                IsClosable="true"
                Description="Info Description Info Description Info Description Info Description">
        <atom:Alert.ExtraAction>
            <StackPanel Orientation="Vertical" Spacing="5">
                <atom:Button ButtonType="Primary" SizeType="Small">Accept</atom:Button>
                <atom:Button SizeType="Small" IsDanger="True" IsGhost="True">Decline</atom:Button>
            </StackPanel>
        </atom:Alert.ExtraAction>
        Info Text
    </atom:Alert>
</StackPanel>
```

