# 动态调整进度条

在现实使用中，其实更多需要的是动态调整进度条，典型场景就是文件上传。实现方法也非常简单，就是动态调整 `Value` 属性的值即可。

![AtomUI ProgressBar组件](./images/dynamic-bar.webp)

```axaml
<StackPanel Orientation="Vertical" Spacing="10">
    <atom:ProgressBar Value="{Binding ProgressValue}" Minimum="0" Maximum="100" />
    <atom:CircleProgress Value="{Binding ProgressValue}" Minimum="0" Maximum="100" />
    <StackPanel Orientation="Horizontal" Spacing="10">
        <atom:Button SizeType="Small" Command="{Binding SubProgressValue}">Sub</atom:Button>
        <atom:Button SizeType="Small" Command="{Binding AddProgressValue}">Add</atom:Button>
    </StackPanel>
</StackPanel>
```
