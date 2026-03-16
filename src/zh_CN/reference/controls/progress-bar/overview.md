# ProgressBar 概述

### 简介

进度条组件用于展示操作的当前进度，为用户提供直观的进度反馈。AtomUI 提供了多种进度条变体，满足不同业务场景的需求。

![AtomUI ProgressBar组件](./images/basic.png)

### 组件类型

| 组件 | 说明 |
|------|------|
| `ProgressBar` | 基础线性进度条，继承自 `AbstractLineProgress`，支持水平和垂直方向 |
| `CircleProgress` | 环形进度条，继承自 `AbstractCircleProgress`，以圆环形式展示进度 |
| `DashboardProgress` | 仪表盘进度条，继承自 `AbstractCircleProgress`，带缺口的圆环 |
| `StepsProgressBar` | 步骤进度条，将进度条分割为若干段，以分段方式展示进度 |

### 主要功能

* 支持多种形状：线性、环形、仪表盘、分段步骤
* 支持横向和竖向两个方向（`Orientation`）
* 支持百分比位置自定义（`PercentPosition`），可设置内/外显示及对齐方式
* 支持三种尺寸：Large、Middle、Small
* 支持四种状态：Normal、Success、Exception、Active
* 支持成功阈值标识（`SuccessThreshold`）和自定义成功色（`SuccessStrokeBrush`）
* 支持线条端点形状（`StrokeLineCap`）和渐变色（`StrokeBrush`）
* 支持禁用状态（`IsEnabled`）
* 支持动态动画更新进度
