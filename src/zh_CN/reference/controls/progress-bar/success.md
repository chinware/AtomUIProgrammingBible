# 成功标志段

这个示例名字不好起，大概就是有一些业务场景中需要一段用来标识成功。比如拢共100分，一旦实际值超过0-60分段，那么0-60段标识为成功色。

在 `ProgressBar` 中，使用这个特性一般需要两个常用属性：
* `SuccessThresholds` 属性用来设定成功阈值
* `SuccessStrokeBrush` 属性用来设定成功段的颜色，如果不单独设定，默认成功色是常见的浅绿色

![AtomUI ProgressBar组件](./images/bar-with-success-segment.png)

```xaml
<StackPanel Orientation="Vertical" Spacing="10">
    <atom:ProgressBar Value="60" Minimum="0" Maximum="100" SuccessThreshold="30" />
    <WrapPanel Orientation="Horizontal">
        <atom:CircleProgress Value="60" Minimum="0" Maximum="100" SuccessThreshold="30" />
        <atom:DashboardProgress Value="60" Minimum="0" Maximum="100" SuccessThreshold="30"
                                SuccessStrokeBrush="Chocolate" />
    </WrapPanel>
</StackPanel>
```
