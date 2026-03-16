# NumericUpDown 概述

### 简介

NumericUpDown 是一个功能丰富的数字输入控件，支持通过键盘、鼠标滚轮或点击上下箭头按钮来调整数值。它继承自 Avalonia 原生的 `NumericUpDown`，并在此基础上扩展了丰富的自定义能力，包括多种样式变体、尺寸、状态色、前后标签、前后缀、清除按钮等功能。

![AtomUI NumericUpDown组件](./images/basic.webp)

### 主要功能

* 支持三种样式变体（Outline、Filled、Borderless），可设定禁用状态
* 支持三种尺寸（Large、Middle、Small）
* 支持状态色（Error、Warning、Normal）
* 支持水印占位文本
* 支持前后标签（LeftAddOn / RightAddOn）与前后缀（InnerLeftContent / InnerRightContent）
* 支持一键清除按钮与自定义清除图标
* 支持字符串模式（StringMode），适用于高精度数值场景
* 支持键盘与鼠标滚轮操作开关
