# Segmented 分段控制器

### 简介

分段控制器，用于在多个选项之间进行切换，常用于视图切换、功能切换等场景。`Segmented` 继承自 `SelectingItemsControl`，内部由多个 `SegmentedItem` 选项组成。

![AtomUI Segmented组件](./images/basic.webp)

### 何时使用

- 需要在少量选项（2~5 个）之间进行切换时。
- 作为标签页（Tabs）的轻量替代，适合页面内局部视图的切换。
- 在筛选栏或工具栏中用作模式切换。

### 主要功能

- 基础用法：通过 `SegmentedItem` 定义各选项。
- Block 模式：设置 `IsExpanding` 使选项等分占满父容器宽度。
- 禁用状态：支持整体或单个选项禁用。
- 多种尺寸：通过 `SizeType` 设置 `Large`、`Middle`、`Small` 三种尺寸。
- 图标支持：选项可设置纯图标，也可图标与文字混合展示。
- 过渡动画：内置切换动画，可通过 `IsMotionEnabled` 控制开关。
