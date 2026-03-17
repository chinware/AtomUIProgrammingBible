# 快速入门

### 基础配置条件

* Nuget安装Avalonia
* Nuget安装AtomUI

### 基础用法

最简单的用法是将 `IsLoading` 设置为 `True`，此时界面上将展示默认的标题与段落占位符。

> 注意：`IsLoading` 仅控制占位符是否显示，并非动画效果开关。

![AtomUI Skeleton组件](./images/basic.png)

axaml文件：
```xaml
<atom:Skeleton IsLoading="True"/>
```

### 显示头像占位

通过 `IsShowAvatar` 在左侧显示一个头像占位符，结合 `ParagraphRows` 设置右侧文本占位行数，可以构建常见的列表条目骨架。

![AtomUI Skeleton组件](./images/complex.png)

axaml文件：
```xaml
<atom:Skeleton IsShowAvatar="True" ParagraphRows="4" IsLoading="True"/>
```

### 动画效果

将 `IsActive` 属性设置为 `True`，占位符区域将展示过渡动画，为用户提供加载中的视觉反馈。

![AtomUI Skeleton组件](./images/animation.webp)

axaml文件：
```xaml
<atom:Skeleton IsActive="True" IsLoading="True"/>
```

### 多组件骨架

当内置布局无法满足业务需求时，可以使用 SkeletonButton、SkeletonAvatar、SkeletonInput、SkeletonImage、SkeletonNode 等子组件自由组合，构建自定义占位布局。

![AtomUI Skeleton组件](./images/advanced.webp)

axaml文件：
```xaml
<StackPanel Orientation="Vertical" Spacing="20">
    <StackPanel Orientation="Horizontal" Spacing="10">
        <atom:SkeletonButton IsActive="{Binding IsSkeletonActive}"
                             IsBlock="{Binding IsSkeletonBlock}"
                             SizeType="{Binding SkeletonButtonAndInputSizeType}"
                             Shape="{Binding SkeletonButtonShape}"/>
        <atom:SkeletonAvatar IsActive="{Binding IsSkeletonActive}"
                             SizeType="{Binding SkeletonButtonAndInputSizeType}"
                             Shape="{Binding SkeletonAvatarShape}"/>
        <atom:SkeletonInput IsActive="{Binding IsSkeletonActive}"
                            SizeType="{Binding SkeletonButtonAndInputSizeType}"/>
    </StackPanel>
    <atom:SkeletonButton IsActive="{Binding IsSkeletonActive}"
                         IsBlock="{Binding IsSkeletonBlock}"
                         SizeType="{Binding SkeletonButtonAndInputSizeType}"
                         Shape="{Binding SkeletonButtonShape}"/>
    <atom:SkeletonInput IsActive="{Binding IsSkeletonActive}"
                        IsBlock="{Binding IsSkeletonBlock}"
                        SizeType="{Binding SkeletonButtonAndInputSizeType}"/>
    <StackPanel Orientation="Horizontal" Spacing="10">
        <atom:SkeletonImage IsActive="{Binding IsSkeletonActive}"/>
        <atom:SkeletonNode IsActive="{Binding IsSkeletonActive}" Width="160"/>
        <atom:SkeletonNode IsActive="{Binding IsSkeletonActive}">
            <atom:Icon IconInfo="{atom:IconInfoProvider Kind=DotChartOutlined}"
                       NormalFilledBrush="#bfbfbf"
                       Width="40"
                       Height="40"/>
        </atom:SkeletonNode>
    </StackPanel>
</StackPanel>
```

### 包裹动态内容

将需要异步加载的内容放置在 `Skeleton` 组件内部，通过绑定 `IsLoading` 属性控制占位符与真实内容的切换。当 `IsLoading` 为 `True` 时显示骨架，为 `False` 时显示 `Content` 中的实际内容。

![AtomUI Skeleton组件](./images/contain-sub-component.webp)

axaml文件：
```xaml
<StackPanel Orientation="Vertical" Spacing="10">
    <atom:Skeleton IsLoading="{Binding SkeletonLoading}">
        <StackPanel Orientation="Vertical" Spacing="20">
            <atom:TextBlock FontWeight="Bold">Ant Design, a design language</atom:TextBlock>
            <atom:TextBlock TextWrapping="Wrap">We supply a series of design principles, practical patterns and high quality design resources (Sketch and Axure), to help people create their product prototypes beautifully and efficiently.</atom:TextBlock>
        </StackPanel>
    </atom:Skeleton>
    <atom:Button IsEnabled="{Binding SkeletonLoading, Converter={x:Static BoolConverters.Not}}"
                 Click="HandleLoadingButtonClicked">Show Skeleton</atom:Button>
</StackPanel>
```
