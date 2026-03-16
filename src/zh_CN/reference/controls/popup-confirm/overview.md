# PopupConfirm 概述

### 简介

点击元素后弹出气泡式的确认框，用于在不打断用户操作流程的前提下进行二次确认。`PopupConfirm` 继承自 `FlyoutHost`，具备灵活的弹出位置和丰富的自定义能力。

![AtomUI PopupConfirm组件](./images/basic-locale-text.webp)

### 何时使用

* 目标元素的操作需要用户进一步确认时，例如删除、提交等不可逆操作
* 相比 `Dialog`，交互更加轻量，不会中断用户的页面操作流

### 主要功能

* 支持 12 种弹出方向，通过 `Placement` 灵活控制弹窗位置
* 支持自定义确认/取消按钮文案，可隐藏取消按钮
* 支持通过 `ConfirmStatus` 设置不同语义状态（Info、Warning、Error）
* 支持自定义图标，与 AtomUI 图标库无缝集成
* 提供 `Confirmed`、`Cancelled`、`PopupClick` 事件，方便业务逻辑处理
