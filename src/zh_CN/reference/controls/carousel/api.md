# Carousel API 参考

## 属性

| 属性 | 说明 | 类型 | 默认值 |
|---|---|---|---|
| `IsShowNavButtons` | 是否显示左右导航箭头 | `bool` | `false` |
| `IsAutoPlay` | 是否开启自动轮播 | `bool` | `false` |
| `AutoPlaySpeed` | 自动轮播时每页的停留时间 | `TimeSpan` | `00:00:03`（3000ms） |
| `PaginationPosition` | 分页指示器的位置 | `CarouselPaginationPosition` | `Bottom` |
| `IsShowPagination` | 是否显示分页指示器 | `bool` | `true` |
| `IsShowTransitionProgress` | 是否在分页指示器上显示播放进度 | `bool` | `false` |
| `IsInfinite` | 是否无限循环播放 | `bool` | `true` |
| `PageTransitionDuration` | 页面切换过渡动画的持续时间 | `TimeSpan` | — |
| `PageInEasing` | 页面进入时的缓动函数 | `Easing` | — |
| `PageOutEasing` | 页面退出时的缓动函数 | `Easing` | — |
| `TransitionEffect` | 页面切换的过渡效果（Scroll / Fade） | `CarouselTransitionEffect` | — |
| `IsMotionEnabled` | 是否启用过渡动画 | `bool` | — |
| `IsSwipeEnabled` | 是否启用触摸/指针滑动切换 | `bool` | `false` |

## 方法

| 方法 | 说明 |
|---|---|
| `Next()` | 切换到下一页 |
| `Previous()` | 切换到上一页 |

## 枚举类型

### CarouselPaginationPosition

| 值 | 说明 |
|---|---|
| `Bottom` | 分页指示器位于底部（默认） |
| `Top` | 分页指示器位于顶部 |
| `Left` | 分页指示器位于左侧 |
| `Right` | 分页指示器位于右侧 |

### CarouselTransitionEffect

| 值 | 说明 |
|---|---|
| `Scroll` | 滚动切换效果 |
| `Fade` | 淡入淡出切换效果 |

## 类继承关系

```
SelectingItemsControl
  └── Carousel
```

## 相关组件

- [CarouselPage](./getting-started.md) — Carousel 的子项容器，用于包裹每一页的内容
