# Steps 概述

### 简介

`Steps` 是一个步骤条组件，用于引导用户按照流程完成任务。它继承自 `SelectingItemsControl`，能够清晰地展示当前步骤的进度和状态，让复杂的流程变得简洁直观。

![AtomUI Steps组件](./images/with-icon.webp)

### 主要功能

* 支持水平和垂直两个方向布局（`Orientation`）
* 支持三种展示风格：默认样式（`Default`）、导航样式（`Navigation`）、内联样式（`Inline`）
* 支持两种指示器类型：默认数字（`Default`）和点状指示器（`Dot`）
* 支持四种步骤状态：等待（`Wait`）、进行中（`Process`）、完成（`Finish`）、错误（`Error`）
* 支持步骤进度展示（`ProgressValue` / `IsShowItemProgress`）
* 支持可点击步骤切换（`IsItemClickable`）
* 支持标签位置配置（`LabelPlacement`）
* 支持 Mini 尺寸（`SizeType="Small"`）
* 支持自定义图标和内容模板（`ContentTemplate`）
* 支持步骤内容区域切换

### 适用场景

* 注册、表单等多步骤流程
* 订单处理、审批等业务流程展示
* 任务进度跟踪
* 向导式操作引导
