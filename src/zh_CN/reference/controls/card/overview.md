# Card 概述

### 简介

通用卡片容器组件，用于承载文字、图片、列表、操作按钮等多种类型的信息。`Card` 继承自 `HeaderedContentControl`，支持多种尺寸、样式变体、内嵌模式、封面、操作栏等丰富功能。

![AtomUI Card组件](./images/loading.webp)

### 何时使用

- 需要将信息聚合在卡片容器中进行展示时。
- 需要一个具有标题、内容、操作区域的容器时。
- 需要网格布局、Tab 切换等多种卡片组合形式时。

### 主要功能

- 支持 Large / Middle / Small 三种尺寸（`SizeType`）。
- 支持 Outline（有边框）和 Borderless（无边框）两种样式变体（`StyleVariant`）。
- 支持内嵌卡片模式（`IsInnerMode`），便于展示层级关系。
- 支持 Tab 卡片（`CardTabsContent`），在单张卡片内切换内容。
- 支持封面（`Cover`）、头像、元数据（`CardMetaContent`）等自定义展示。
- 支持加载状态（`IsLoading`），在内容上方显示加载遮罩。
- 支持操作栏（`Actions`），在卡片底部放置操作按钮。
- 支持网格布局（`CardGridContent` / `CardGridItem`）。
- 支持悬停效果（`IsHoverable`）和阴影（`BoxShadow`）。
