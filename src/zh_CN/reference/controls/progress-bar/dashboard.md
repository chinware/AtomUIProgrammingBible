# Dashboard

`DashboardProgress` 是一种模拟仪表盘的进度组件，`DashboardGapPosition` 用于设定仪表盘缺口的位置，`GapDegree` 用于设定缺口的大小。

![AtomUI ProgressBar组件](./images/dashboard.png)

```axaml
<WrapPanel Orientation="Horizontal">
    <atom:DashboardProgress Value="75" Minimum="0" Maximum="100" DashboardGapPosition="Left" />
    <atom:DashboardProgress Value="60" Minimum="0" Maximum="100" DashboardGapPosition="Top" />
    <atom:DashboardProgress Value="75" Minimum="0" Maximum="100" DashboardGapPosition="Right"
                            GapDegree="40" />
    <atom:DashboardProgress Value="100" Minimum="0" Maximum="100" DashboardGapPosition="Bottom"
                            GapDegree="40" />
</WrapPanel>
```
