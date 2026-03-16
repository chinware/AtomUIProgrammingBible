# RadioButton 概述

### 简介

`RadioButton` 是一种常用的单选控件，用于在一组互斥的选项中选择一个。AtomUI 的 RadioButton 组件继承自 `Avalonia.Controls.RadioButton`，在保留原生功能的基础上提供了丰富的展示形式。

此外，AtomUI 还额外提供了 `OptionButton` 与 `OptionButtonGroup` 组件，以按钮形式呈现单选选项，支持 Solid 和 Outline 两种风格以及多种尺寸。

![AtomUI RadioButton 组件](./images/option.webp)

### 主要功能

* 支持横向和纵向两种排列方式
* 支持选中、未选中、禁用等多种状态
* 支持自定义内容，包括图标与文本组合
* 提供 `OptionButton` 按钮形式的单选组件
* `OptionButtonGroup` 支持 Solid 与 Outline 两种按钮风格
* 支持 Large、Middle、Small 三种尺寸

### 适用场景

* 表单中需要用户在多个选项中选择唯一一项时
* 需要以按钮样式呈现互斥选项时（如标签页切换、模式选择）
* 需要带图标的单选组时（如图表类型选择）
