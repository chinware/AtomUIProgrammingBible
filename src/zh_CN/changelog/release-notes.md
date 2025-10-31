![Changelog](./images/changelog.png)

#### v5.0.0
`2025年10月15日`

**新特性**

- **新增 Steps 控件** - 全新的步骤条组件
- **数据表格增强** - 新增操作提示器功能

**优化改进**

- **NavMenu 控件重构** - 重写底层结构，支持数据源绑定方式生成导航菜单
- **应用主题管理** - 改用 `IThemeManager` 方式，更好支持 Prism 等框架整合
- **ComboBox 优化** - Popup 支持自定义显示条目数量
- **CircleProgress 增强** - 支持自定义成功和失败图标
- **SelectableTextBlock 优化** - 功能体验提升
- **LoadingIndicator 重构** - 重命名为 `Spin` 并彻底重写

**Bug**

- 修复苹果系统下编译方法不存在的问题
- 修复点击 DataGrid 行标题报异常问题
- 修复系统字体干扰问题
- 修复 Button 设置斜体字体时部分字母显示不全
- 修复 ColorPicker 关闭后再次打开失效的问题
- 修复 `atom:Window` 的 `IsTitleBarVisible` 属性无效问题

**版本说明**

开发者可能对版本号从之前版本直接跳到 5.0.0 有所疑惑，这里进行说明：

AtomUI OSS 本质上是 **Ant Design 5.0** 设计语言的 Avalonia/.NET 实现。为了降低开发者的理解成本，从本版本开始 AtomUI OSS 将锚定 Ant Design 的主版本号。

**版本对应关系：**
- AtomUI OSS 5.0 → Ant Design 5.0
- AtomUI OSS 6.0 → Ant Design 6.0
- AtomUI OSS 7.0 → Ant Design 7.0

以此类推，未来版本将保持与 Ant Design 的版本同步。

#### v1.0.1
`2025年10月2日`

**新特性**
- 实现虚线类型的按钮类型新增
- Separator 分割线的样式和分割线跟修饰的间距

**优化**

- 优化控件的 Design Token 生成
- 还有不少不应该被公开的类被公开，需要清理

**Bug 修复**

- TabControl 动态添加标签的时候有问题
- ToggleSwitch With text and icon模式存在显示文字溢出bug
- Alert分割线的配色太淡了，视觉效果不明显

#### v1.0.0
`2025年9月25日`

`AtomUI` 第一个正式版本，包含了 `Ant Design 5.0` 大部分的控件，以及完整的主题系统，基本达到可用状态。
