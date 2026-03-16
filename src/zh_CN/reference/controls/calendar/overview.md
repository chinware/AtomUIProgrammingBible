# Calendar 日历

## 简介

日历组件用于按照日历形式展示数据或进行日期选择。AtomUI 的 Calendar 组件遵循 Ant Design 设计规范，支持月、年、十年三种视图模式，并提供单选、范围选择、多范围选择等多种选择模式，满足各类日期交互场景需求。

一般来说直接使用 `Calendar` 的场景较少，大多数业务场景中更常使用基于 `Calendar` 封装的日期选择器（`DatePicker`）。但为了满足灵活自定义的需求，AtomUI 同时提供了最基础原始的 `Calendar` 组件。

![AtomUI Calendar组件](./images/basic.webp)

## 何时使用

- 需要以日历面板形式直接展示日期信息时
- 需要内联的日期选择交互（非弹出式）时
- 作为自定义日期选择器的基础构建模块时
- 需要同时选择多个日期或日期范围时

## 主要特性

- **三种显示模式** — Month（月视图）、Year（年视图）、Decade（十年视图），支持在不同粒度间自由切换
- **四种选择模式** — SingleDate（单选）、SingleRange（单范围）、MultipleRange（多范围）、None（禁止选择）
- **今日高亮** — 默认高亮显示当天日期，便于用户快速定位
- **日期范围约束** — 通过 DisplayDateStart / DisplayDateEnd 限制可选的日期范围
- **首日定制** — 支持自定义每周的起始日（周一、周日等）
- **过渡动画** — 内置平滑的视图切换动画效果
- **双向绑定** — SelectedDate、DisplayDate 等核心属性均支持 TwoWay 绑定，便于与 ViewModel 集成
