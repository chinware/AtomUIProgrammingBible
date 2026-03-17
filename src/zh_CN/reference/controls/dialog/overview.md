# Dialog 概述

### 简介

`Dialog` 是 AtomUI 提供的弹出式对话框组件，继承自 `TemplatedControl`。在一些 UI 框架中也被称为 `Modal`。`Dialog` 组件为开发者提供了功能丰富、高度可定制的模态对话框解决方案，适用于需要用户交互确认、信息展示、表单填写等业务场景。

![AtomUI Dialog组件](./images/basic.webp)

### 主要功能

* 支持 `Overlay` 和 `Window` 两种宿主模式（`DialogHostType`）
* 支持模态遮罩（`IsModal`）与轻触关闭（`IsLightDismissEnabled`）
* 支持拖拽移动（`IsDragMovable`）与窗口大小调整（`IsResizable`）
* 支持标题栏图标（`TitleIcon`）、关闭按钮、最大化和最小化按钮
* 内置标准按钮（`StandardButtons`）与自定义按钮（`CustomButtons`）
* 支持加载状态（`IsLoading`）与确认加载状态（`IsConfirmLoading`）
* 支持自定义启动位置（`HorizontalStartupLocation`、`VerticalStartupLocation`）
* 支持置顶显示（`Topmost`）
* 提供完善的事件体系：打开、关闭、接受、拒绝、按钮点击等
* 支持动画效果（`IsMotionEnabled`）

### 两种宿主模式

`Dialog` 通过 `DialogHostType` 属性支持两种不同的宿主模式：

* **Overlay**（默认）：对话框以覆盖层的形式显示在当前窗口内部，活动范围限于主 UI 窗口内。适合大多数应用内交互场景。
* **Window**：对话框以独立原生窗口的形式显示，可以脱离主窗口独立移动，活动范围为整个桌面。适合需要多窗口协作的场景。

### Dialog 与 MessageBox

AtomUI 同时提供了 `MessageBox` 组件，它是 `Dialog` 的特殊定制版本，内部组合使用了 `Dialog` 的核心功能。两者的适用场景如下：

* **Dialog**：适合业务复杂、需要高度定制的场景，给予开发者最大的自由度
* **MessageBox**：适合简单的通知提示、确认操作等场景，开箱即用
