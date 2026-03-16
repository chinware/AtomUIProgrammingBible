# Notification 概述

### 简介

全局展示通知提醒信息的 `Notification` 组件，常用于系统级通知、操作反馈等场景。支持多种通知类型、自定义图标、自动关闭与进度指示等丰富特性。

![AtomUI Notification组件](./images/basic.webp)

### 主要功能

* 支持四种内置通知类型：`Success`、`Information`、`Warning`、`Error`，每种类型配有对应的语义图标
* 支持自定义图标，可使用 `AntDesignIconPackage` 图标库中的任意图标
* 支持六种弹出位置：`TopLeft`、`TopCenter`、`TopRight`、`BottomLeft`、`BottomCenter`、`BottomRight`
* 支持自动关闭倒计时与进度指示器，鼠标悬停可暂停倒计时（Pause on Hover）
* 支持设定自动关闭时间，也可通过 `TimeSpan.Zero` 实现永不自动关闭
* 通过 `WindowNotificationManager` 管理通知的显示与生命周期，可配置 `MaxItems` 控制最大显示数量
