# TabControl 概述

### 简介

TabControl 是一个选项卡容器组件，用于在有限的空间内组织和切换多个内容面板。AtomUI 提供了两种风格的选项卡组件：`TabControl`（线条风格）和 `CardTabControl`（卡片风格），满足不同的界面设计需求。

![AtomUI TabControl组件](./images/card-shape-position.webp)

### 主要功能

* 提供 `TabControl` 和 `CardTabControl` 两种风格
* 支持四个方向的标签位置（上、下、左、右）
* 支持图标与自定义尺寸
* 内置多标签横向滑动能力
* 支持动态添加和关闭标签页
* 支持居中对齐、禁用标签等常用场景

### 组件变体

| 组件 | 说明 |
|---|---|
| `TabControl` | 默认线条风格的选项卡，适用于大多数场景 |
| `CardTabControl` | 卡片风格的选项卡，提供更具层次感的视觉效果 |

### 相关组件

- `TabItem` -- 选项卡子项，用于定义每个标签页的标题和内容
- `TabStrip` / `CardTabStrip` -- 仅包含标签栏的轻量组件，不含内容面板
