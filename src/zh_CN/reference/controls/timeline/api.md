# Timeline API

### Timeline

`Timeline` 继承自 `ItemsControl`，用于展示时间线组件。其子项为 `TimelineItem`。

#### 属性

| 属性名 | 类型 | 默认值 | 说明 |
| --- | --- | --- | --- |
| Mode | `TimeLineMode` | `TimeLineMode.Left` | 时间线排版模式，可选 `Left`、`Right`、`Alternate` |
| Pending | `object?` | `null` | 设置加载中状态的幽灵节点内容。当该属性不为空时，会在时间线末尾（或反转后的开头）显示一个加载中的节点 |
| IsReverse | `bool` | `false` | 是否反转时间线顺序。设为 `true` 时，节点从下到上反转排列 |
| PendingIcon | `PathIcon?` | `null` | 自定义加载中节点的图标。为空时使用默认的加载动画图标 |

### TimeLineMode 枚举

| 枚举值 | 说明 |
| --- | --- |
| Left | 时间线内容显示在左侧（默认模式） |
| Right | 时间线内容显示在右侧 |
| Alternate | 时间线内容左右交替显示 |
