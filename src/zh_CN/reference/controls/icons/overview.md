# Icons 图标

## 简介

AtomUI 内置了完整的 AntDesign 图标库，通过 `IconProvider` 标记扩展在 XAML 中便捷地使用图标。图标可以应用于按钮、菜单、导航等多种组件，为界面提供直观的视觉提示。

![AtomUI Icons 组件](./images/icons.webp)

## 何时使用

- 需要用图形化符号辅助文字说明时
- 按钮、菜单项等组件需要搭配图标增强辨识度时
- 需要在界面中以简洁方式传达操作含义时

## 主要特性

- **AntDesign 图标库** — 内置丰富的 AntDesign 图标，涵盖方向、建议、编辑、数据、品牌等多个分类
- **标记扩展** — 通过 `IconProvider` 标记扩展在 XAML 中直接使用，无需额外代码
- **三种图标风格** — Outlined（线框风格）、Filled（实心风格）、TwoTone（双色风格）
- **灵活集成** — 可用于所有支持 `Icon` 属性的组件，如 Button、Menu、Tag 等
- **尺寸自适应** — 图标尺寸随宿主组件的 `SizeType` 自动适配
