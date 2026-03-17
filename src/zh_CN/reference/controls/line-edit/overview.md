# LineEdit 输入框

## 简介

输入框是最常见的数据录入组件，用于接收用户的文本输入。AtomUI 的 LineEdit 组件继承自 Avalonia 的 TextBox，在此基础上遵循 Ant Design 设计规范进行了全面增强，提供了丰富的样式变体、状态反馈和扩展能力，满足各类表单输入场景的需求。

![AtomUI LineEdit 组件](./images/basic.webp)

## 何时使用

- 需要用户输入单行文本时，如用户名、邮箱、搜索关键词等
- 表单中需要采集各类文本信息时
- 需要密码输入并提供隐私保护时
- 需要带有前后缀装饰或附加内容的输入场景

## 主要特性

- **三种尺寸** — Large、Middle、Small，适配不同密度的布局
- **三种样式变体** — Outline（描边）、Filled（填充）、Borderless（无边框），满足不同的视觉层级需求
- **状态反馈** — 支持 Error、Warning 状态色，直观展示校验结果
- **禁用状态** — 所有变体均支持禁用态
- **一键清除** — 内置清除按钮，快速清空输入内容
- **密码模式** — 支持密码字符遮蔽及明文切换
- **前后标签** — 通过 LeftAddOn / RightAddOn 在输入框外部附加标签内容
- **前后缀** — 通过 InnerLeftContent / InnerRightContent 在输入框内部嵌入图标或文字
- **搜索框** — 提供专用的 SearchEdit 组件，内置搜索按钮
