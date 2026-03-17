# CheckBox 概述

### 简介

`CheckBox` 是一个常用的表单选择控件，允许用户在选中、未选中和不确定三种状态之间切换。AtomUI 的 `CheckBox` 组件继承自 `Avalonia.Controls.CheckBox`，在保留原生功能的基础上扩展了动效和波纹效果等特性。

![AtomUI CheckBox 组件](./images/grid-checkbox.webp)

### 主要功能

* 支持选中、未选中、不确定（半选）三种状态
* 支持禁用状态
* 支持动效开关（`IsMotionEnabled`）和波纹效果开关（`IsWaveSpiritEnabled`）
* 可通过 MVVM 模式绑定和控制选中状态
* 支持全选/取消全选场景
* 可与 `WrapPanel`、`Grid` 等布局容器灵活组合

### 适用场景

* 表单中需要用户进行多项选择时
* 需要实现全选/反选功能时
* 在列表或网格中嵌入勾选操作时
