# Timeline 概述

### 简介

Timeline（时间线）是一个继承自 `ItemsControl` 的数据展示组件，用于垂直方向展示一系列按时间排列的事件信息。支持多种排版模式、自定义指示器颜色、内容反转以及加载中状态。

![AtomUI Timeline组件](./images/basic.png)

### 主要功能

* 支持左侧（Left）、右侧（Right）、交替（Alternate）三种时间线排版模式
* 支持通过 `IndicatorColor` 自定义时间轴指示器颜色，内置 green、blue、red、gray 预设色，也支持自定义十六进制颜色
* 支持通过 `IsReverse` 快速反转时间线顺序
* 支持通过 `Pending` 属性展示加载中状态的幽灵节点
* 支持通过 `PendingIcon` 自定义加载中状态的图标
* 支持通过 `Label` 属性为 `TimelineItem` 添加标签文本
* 支持 XAML 声明式配置与 C# code-behind 动态控制
