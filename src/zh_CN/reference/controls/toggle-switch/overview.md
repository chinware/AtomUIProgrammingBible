# ToggleSwitch 概述

### 简介

ToggleSwitch 是一个开关切换组件，继承自 `ToggleButton`，适用于需要在两种状态之间进行切换的场景，例如功能的启用/禁用、设置项的开关等。

![AtomUI ToggleSwitch组件](./images/text-icon.webp)

### 主要功能

* 支持三种尺寸（Large、Middle、Small），满足不同场景需求
* 支持禁用状态，通过 `IsEnabled` 控制
* 支持自定义开启/关闭状态的文案和图标（`OnContent` / `OffContent`）
* 支持 loading 加载状态，适用于异步操作场景
* 支持自定义滑块大小、轨道背景色等样式
* 内置动画效果与波纹效果，可通过属性控制开关
