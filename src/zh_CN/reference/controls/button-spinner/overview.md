# ButtonSpinner 概述

### 简介

`ButtonSpinner` 是 AtomUI 提供的带递增/递减箭头按钮的微调器组件，继承自 `Spinner` 基类。用户可以通过点击上下箭头按钮来触发 Spin 事件，常用于数值调节、列表项切换等需要步进操作的场景。

![AtomUI ButtonSpinner组件](./images/size.webp)

### 何时使用

- 需要在输入框旁提供递增/递减操作时
- 需要在有限的选项列表中逐项切换时
- 需要对数值进行步进调节时

### 主要功能

- 支持多种尺寸（Large / Middle / Small）
- 支持多种样式变体（Outline / Filled / Borderless）
- 支持 LeftAddOn / RightAddOn 前后附加内容
- 支持 InnerLeftContent / InnerRightContent 内部前后缀
- 支持状态颜色（Default / Error / Warning）
- 支持禁用状态
- 支持自定义 Spinner 按钮位置（左侧或右侧）
- 支持控制 Spinner 按钮的显示与隐藏
- 支持过渡动画
