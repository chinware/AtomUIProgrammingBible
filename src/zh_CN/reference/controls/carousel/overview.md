# Carousel 走马灯

## 简介

旋转木马，一组轮播的区域。当有一组平级的内容需要依次展示时，可使用走马灯组件进行轮播展示。AtomUI 的 Carousel 组件遵循 Ant Design 设计规范，支持自动轮播、多种过渡效果、分页指示器位置自定义等丰富功能，满足图片轮播、内容卡片切换等常见场景需求。

![AtomUI Carousel组件](./images/basic.webp)

## 何时使用

- 当有一组平级的内容需要依次展示时
- 首页或活动页面的 Banner 图片轮播
- 产品展示、新闻公告等内容的循环播放
- 需要在有限空间内展示多个内容项时

## 主要特性

- **自动轮播** — 通过 IsAutoPlay 开启自动播放，AutoPlaySpeed 控制播放速度
- **无限循环** — IsInfinite 属性控制是否在最后一页后自动跳转回第一页
- **分页指示器** — 支持 Top、Bottom、Left、Right 四个方向的分页器位置
- **过渡效果** — 内置 Scroll（滚动）和 Fade（淡入淡出）两种切换效果
- **导航箭头** — IsShowNavButtons 控制是否显示左右切换箭头
- **进度展示** — IsShowTransitionProgress 展示当前页的播放进度
- **编程控制** — 提供 Next() 和 Previous() 方法，支持代码控制翻页
- **滑动支持** — IsSwipeEnabled 启用触摸/指针滑动切换
