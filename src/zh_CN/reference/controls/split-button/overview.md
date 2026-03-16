# SplitButton 概述

### 简介

`AtomUI` 提供了分裂按钮组件 `SplitButton`，它将一个主操作按钮与一个下拉菜单按钮组合在一起，为用户提供主操作的同时，也能快速访问相关的次要操作。`SplitButton` 继承自 `ContentControl` 并实现了 `ICommandSource` 接口，底层基于 `Flyout` 与 `Menu` 两个基础组件构建。

![AtomUI SplitButton组件](./images/split-button-size.webp)

### 主要功能

* 支持多种尺寸（Large / Middle / Small）
* 支持危险状态按钮（IsDanger）
* 支持自定义图标（Icon）与展开指示器（OpenIndicator）
* 支持点击（Click）和悬停（Hover）两种触发方式
* 支持命令绑定与快捷键
* 支持弹出位置、箭头指示等弹出层配置

### 适用场景

* 需要提供一个主要操作，同时附带多个次要操作时
* 工具栏中需要节省空间但又需要提供多种相关操作时
* 对操作进行分组，突出最常用的操作
