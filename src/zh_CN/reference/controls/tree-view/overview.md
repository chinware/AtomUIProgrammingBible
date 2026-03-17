# TreeView 概述

### 简介

TreeView 树形控件是一种以层级结构展示信息的组件，适用于文件目录、组织结构、分类导航等场景。支持展开/收起、复选框/单选、拖拽排序、连接线、节点图标、节点过滤高亮等丰富功能。

![AtomUI TreeView组件](./images/basic.webp)

### 主要功能

* 基础树形结构，支持多层级嵌套节点
* 复选框模式（ToggleType=CheckBox）与单选模式（ToggleType=Radio）
* 默认全部展开（IsDefaultExpandAll）
* 节点悬停高亮模式（NodeHoverMode），支持 Default、Block、WholeLine 三种效果
* 拖拽排序（IsDraggable），允许用户通过拖拽重新组织树结构
* 连接线显示（IsShowLine），直观展示节点层级关系
* 节点图标（IsShowIcon）与叶节点图标（IsShowLeafIcon）
* 切换器图标自定义（SwitcherExpandIcon / CollapseIcon / RotationIcon / LoadingIcon / LeafIcon）
* 切换器旋转动画（IsSwitcherRotation）
* 自动展开父节点（IsAutoExpandParent）
* 节点过滤与高亮（Filter / FilterValue / FilterHighlightStrategy）
* 异步数据加载（DataLoader）
* 空状态指示器（EmptyIndicator / EmptyIndicatorTemplate）
* 支持 MVVM 模式，配合 ReactiveObject 进行数据绑定
