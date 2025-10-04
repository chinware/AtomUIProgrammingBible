# AtomUI Timeline快速入门

### 基础配置条件

* Nuget安装Avalonia
* Nuget安装AtomUI

### 基础用法

通过 `TimeLine` 与 `TimelineItem` 组件组合成经典的左右两列布局，通过 `IndicatorColor` 可以设定时间轴的指示器颜色。

![AtomUI Timeline组件](./images/basic.png)

```axaml
<atom:Timeline>
    <atom:TimelineItem>
        2024-01-01 AtomUI Officially Initiated
    </atom:TimelineItem>
    <atom:TimelineItem IndicatorColor="green">
        2024-08-12 After more than 7 months of development, AtomUI is officially open-source.
        Welcome everyone to follow us.
    </atom:TimelineItem>
    <atom:TimelineItem IndicatorColor="red">
        2024-10-01 Release of the 0.0.1 Preview Version
    </atom:TimelineItem>
</atom:Timeline>
```

### 预设颜色

`IndicatorColor` 属性内置多种预设颜色，也可以通过指定十六进制颜色指定颜色。

![AtomUI Timeline组件](./images/color.png)

```axaml
<atom:Timeline>
    <atom:TimelineItem IndicatorColor="green">
        2024-01-01 AtomUI Officially Initiated
    </atom:TimelineItem>
    <atom:TimelineItem IndicatorColor="blue">
        2024-01-01 AtomUI Officially Initiated
    </atom:TimelineItem>
    <atom:TimelineItem IndicatorColor="Red">
        2024-01-01 AtomUI Officially Initiated
    </atom:TimelineItem>
    <atom:TimelineItem IndicatorColor="gray">
        2024-01-01 AtomUI Officially Initiated
    </atom:TimelineItem>
    <atom:TimelineItem IndicatorColor="#00CCFF">
        2024-01-01 AtomUI Officially Initiated
    </atom:TimelineItem>
</atom:Timeline>
```