# Slider 概述

### 简介

Slider 是一个滑动输入组件，用于在一定范围内选取数值或数值区间。继承自 `RangeBase`，支持水平与垂直方向、单值与范围双滑块模式，并提供刻度标记、工具提示格式化、吸附对齐等丰富功能。

![AtomUI Slider组件](./images/basic.webp)

### 主要功能

* 支持水平（Horizontal）和垂直（Vertical）两种方向
* 支持范围模式（IsRangeMode），通过双滑块选取数值区间
* 支持刻度标记（Marks），可自定义标签文本、颜色和字体样式
* 支持刻度吸附（IsSnapToTickEnabled），使滑块只能停在刻度点上
* 支持工具提示格式化（ValueFormatTemplate），自定义数值显示格式
* 支持标记高亮（Included），根据选中范围自动高亮对应标记
* 支持运动动画（IsMotionEnabled）和波浪动画（IsWaveAnimationEnabled）
