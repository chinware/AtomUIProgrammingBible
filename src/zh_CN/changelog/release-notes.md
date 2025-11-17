![Changelog](./images/changelog.png)

#### v5.0.2

`2025 年 11 月 17 日`

**新特性**

- 新增 OverlayPopupHost 弹出载体，优化某些场景下的弹窗性能
- 新增二维码扫描控件
- 新增 CSS FlexBox 布局控件
- 新增 TextArea 多行文本控件
- 新增 Gallery 探测操作系统信息页面

**优化**

- 优化 ItemsControl 系列控件的模板生成
- 优化 Carousel走马灯，增加滑动切换功能
- 优化 OptionButtonGroup 控件，实现自定义高度和增加对 Icon 的配置
- 优化 AddOnDecoratedBox 新增下划线风格
- 优化 Alert ，新增关闭事件
- 优化 Dialog 控件，提供一个静态创建 API
- 优化 Drawer，实现自定义弹出宽度
- 优化 Navmenu、Combobox 和 List 选中属性的双向绑定
- 优化 ReactiveUI 库引用问题，将 Avalonia.ReactiveUI 替换为 ReactiveUI.Avalonia

**Bug 修复**

- 修复 TabControl 数据源无法绑定 Icon
- 修复 Popup 改变位置，箭头位置不对
- 修复 DataGrid 存在显示内容不随 ItemsSource 刷新问题
- 修复 TreeView 默认选中不应该播放波浪动画的问题
- 修复 DataGrid 过滤弹出菜单，弹出的时候会动态变宽的问题
- 修复 DataGrid 数据源为空报错的问题

**特别感谢**
- 感谢 https://github.com/yaobiao131 实现二维码扫描控件
- 感谢 https://github.com/tuskermanshu 实现 CSS FlexBox 布局控件，跑马灯拖动翻页和控件焦点渲染样式

#### v5.0.1
`2025 年 11 月 3 日`

**新特性**

- 新增 Select 控件
- 实现数据表格列拖动改变列宽
- 全新的 List 控件实现

**优化**

- 优化 MenuFlyout 的数据源绑定生成模板
- 优化弹出菜单滚动条
- 优化 Design Token 系统
- 优化 Tree 控件，需要支持数据源绑定生成节点
- RadioButton 新增可以定制 label 内容
- Spin 加载器背景新增是否模糊开关
- 优化 AddOnDecoratedBox，大大降低使用难度

**Bug 修复**

- TreeView 多级树形结构中复选框父级状态异常
- Combobox 点击 arrow icon 无法弹出 popup
- NavMenu 菜单级别的选中需要单独处理，目前的处理是错误的
- 默认类型的按钮背景颜色计算有问题
- ThemeConfigProvider 修改全局 Token 的时候，组件没有正确计算
- Drawer抽屉第二次点击弹出有问题 Multi-level drawer
- AtomLayer 问题，layer 无法监控 target 控件的（包含嵌套的）父控件的(IsVisible的Changed或者是Bounds的Changed)
- Pagination 组件 CurrentPage 属性在页面导航时显示错误值

**API 变更说明**

为了保持命名跟 Ant Design 一致，我们进行了以下控件的重命名：

- ListBox -> List
- EmptyIndicator -> Empty
- LoadIndicator -> Spin

因为 API 变化给大家带来的不便，还请各位开发者朋友多多包涵。

**完整的更新日志**: https://gitee.com/chinware/atomui/compare/v5.0.1-build.4...v5.0.1


#### v5.0.0
`2025 年 10 月 15 日`

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
`2025 年 10 月 2 日`

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
`2025 年 9 月 25 日`

`AtomUI` 第一个正式版本，包含了 `Ant Design 5.0` 大部分的控件，以及完整的主题系统，基本达到可用状态。
