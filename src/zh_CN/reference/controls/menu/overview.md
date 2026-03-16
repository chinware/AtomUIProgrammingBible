# Menu 概述

### 简介

Menu 是为页面和功能提供导航的菜单组件，支持水平菜单、垂直菜单、多级子菜单、右键菜单等多种形态。

![AtomUI Menu组件](./images/with-icon.webp)

### 何时使用

- 需要在页面顶部或侧边提供导航菜单时。
- 需要对功能操作进行分组和层级展示时。
- 需要右键弹出上下文操作菜单时。

### 主要功能

- **水平菜单**：常规顶部横向导航菜单，适用于顶部导航栏场景。
- **垂直菜单**：侧边栏垂直展示的导航菜单，支持 Vertical 弹出和 Inline 内嵌两种模式。
- **多级子菜单**：支持任意层级的子菜单嵌套。
- **右键菜单**：通过 ContextMenu、ContextFlyout 或 MenuFlyout 实现右键弹出菜单。
- **图标菜单**：菜单项支持配置 Icon 图标。
- **Radio / CheckBox 菜单项**：通过 ToggleType 属性实现单选和多选菜单项。
- **可滚动菜单**：当菜单项过多时自动支持滚动显示。
- **暗色样式**：NavMenu 支持通过 IsDarkStyle 切换暗色主题。
- **默认展开与选中**：NavMenu 支持通过 DefaultOpenPaths 和 DefaultSelectedPath 设置初始展开和选中状态。
- **动态数据生成**：支持通过 ItemsSource 结合 TreeDataTemplate 动态生成菜单结构。

### 组件体系

| 组件 | 说明 |
|---|---|
| `Menu` | 水平菜单容器，继承自 Avalonia.Controls.Menu |
| `MenuItem` | 菜单项，继承自 Avalonia.Controls.MenuItem |
| `MenuSeparator` | 菜单分隔线 |
| `ContextMenu` | 右键上下文菜单 |
| `MenuFlyout` | 浮出菜单，通过 ContextFlyout 使用 |
| `NavMenu` | 导航菜单，支持水平、垂直、内嵌等多种模式 |
| `NavMenuItem` | 导航菜单项 |
